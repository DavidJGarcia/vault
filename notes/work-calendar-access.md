# Hooking the agent up to my work Outlook calendar, read-only

Asked October 21, 2026: "How would I hook you up to my work Outlook calendar in a
read-only way that my work IT would approve of so that I can see what's going on
there?" Assumes the work tenant is Microsoft 365 / Exchange Online, which is what
"work Outlook" nearly always means now.

Three paths. The second is the one a security-minded IT department actually
approves; the first is the one to try first because it may already be switched on.

## 1. Publish the calendar as an ICS link (no ticket, if the tenant allows it)

Outlook on the web -> Calendar -> Settings -> Shared calendars -> **Publish a
calendar**. Pick the calendar, pick the detail level, and it gives an HTML link
and an **.ics** link. The agent (or any calendar app) subscribes to the .ics and
sees the calendar refresh on its own.

- Read-only by construction. No app, no token, no password.
- **The catch:** the link is unauthenticated. Anyone who has the URL sees the
  calendar, and that is exactly why many tenants turn it off. Expect a security
  team to say no if asked, and expect them to be right to.
- If **Publish a calendar** is missing from the settings page, the tenant has
  already disabled it: the assigned Exchange sharing policy has no `Anonymous`
  domain entry. That is an admin change, not something to work around.

## 2. An Entra ID app registration, Graph Calendars.Read, scoped to one mailbox

This is the ask to put in the ticket. It is read-only, it is one mailbox, it is
logged in the tenant, and IT can revoke it in a click.

1. IT registers an app in Entra ID (Azure AD) in the work tenant.
2. It is granted the Microsoft Graph **application** permission `Calendars.Read`
   and nothing else. No `Mail.*`, no `Files.*`.
3. IT then scopes it with **RBAC for Applications** in Exchange Online: the
   `Application Calendars.Read` role, assigned to the app, with a custom
   management scope that resolves to my mailbox alone. Without that scope the app
   permission reaches every mailbox in the company, which is the objection IT will
   raise first — naming the scope in the request answers it before it is asked.
   (RBAC for Applications is Microsoft's replacement for the older
   `New-ApplicationAccessPolicy`; an older admin may still reach for that cmdlet
   and it works.)
4. The app's certificate or client secret lives on the machine that does the
   fetching. **This is the second real objection:** a credential that reads
   company calendar data sitting on a personal PC. Offer a certificate rather than
   a secret, short expiry, and say where the file sits.

Ticket wording, roughly: "Requesting an Entra app registration with Microsoft
Graph application permission Calendars.Read, restricted by an Exchange Online RBAC
for Applications scope to my mailbox only, so a personal scheduling tool can read
my own calendar. Read-only. No mail or file permissions. Certificate credential,
revocable at any time."

## 3. Delegated Calendars.Read, signing in as myself

Same app registration, but the **delegated** `Calendars.Read` scope and my own
interactive sign-in — no client secret, the token is mine and expires. Cleaner in
principle, and `Calendars.ReadBasic` reads even less (times and subjects, not
bodies and attendees) if availability is all that is wanted.

This used to need no admin at all. As of **June 2026** Microsoft's managed default
user-consent policy requires admin consent for `Calendars.Read`, so it is a ticket
now either way. If the tenant also enforces conditional access on compliant or
managed devices, a sign-in from a personal machine will fail no matter what is
consented.

## 4. Free/busy only

If the real need is just "am I booked", Outlook's external calendar sharing can
share **availability only** to a personal address. Lowest-risk option by far, and
it is governed by the tenant's external sharing policy rather than an app.
Downside: no subjects, so it does not answer "what's going on there".

## What is still missing on this side

Nothing in Index reads a Graph calendar yet. Any of the above needs a job here
that pulls `/me/calendarView` (or the .ics) and turns the day's events into
something the morning briefing can read. That is a build, not a setting.

## Sources

- Microsoft Graph permissions reference — https://learn.microsoft.com/en-us/graph/permissions-reference
- RBAC for Applications in Exchange Online — https://learn.microsoft.com/en-us/exchange/permissions-exo/application-rbac
- Publish Calendar option missing from Calendar settings — https://learn.microsoft.com/en-us/troubleshoot/exchange/outlook-on-the-web-issues/publish-calendar-option-missing-from-calendar-settings
- Default app consent policy to block more permissions (June 2026) — https://blog-en.topedia.com/2026/05/microsoft-managed-default-app-consent-policy-will-block-8-additional-permissions/
- Calendar permissions in Exchange Online and Outlook — https://www.sikich.com/insight/calendar-permissions-in-exchange-online-and-outlook/
