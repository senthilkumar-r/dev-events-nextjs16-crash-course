# PostHog post-wizard report

The wizard has completed a deep integration of your DevEvent Next.js project. PostHog has been configured with client-side analytics using the modern `instrumentation-client.ts` approach recommended for Next.js 15.3+. The integration includes automatic pageview tracking, error tracking via `capture_exceptions`, and custom event tracking for key user interactions across the application.

## Files Created/Modified

| File | Change Type | Description |
|------|-------------|-------------|
| `.env` | Created | Environment variables for PostHog API key and host |
| `instrumentation-client.ts` | Created | Client-side PostHog initialization with error tracking enabled |
| `components/ExploreBtn.tsx` | Modified | Added `explore_events_clicked` event capture |
| `components/EventCard.tsx` | Modified | Added `event_card_clicked` event capture with event properties |
| `components/Navbar.tsx` | Modified | Added `nav_link_clicked` event capture for navigation tracking |

## Events Instrumented

| Event Name | Description | File |
|------------|-------------|------|
| `explore_events_clicked` | User clicked the 'Explore More' button to scroll down to the events section | `components/ExploreBtn.tsx` |
| `event_card_clicked` | User clicked on an event card to view event details | `components/EventCard.tsx` |
| `nav_link_clicked` | User clicked a navigation link in the navbar | `components/Navbar.tsx` |

## Event Properties

### `explore_events_clicked`
- `button_location`: Location of the button (hero_section)
- `target_section`: Target section the button scrolls to (events)

### `event_card_clicked`
- `event_title`: Title of the clicked event
- `event_slug`: URL slug of the event
- `event_location`: Location of the event
- `event_date`: Date of the event
- `event_time`: Time of the event

### `nav_link_clicked`
- `link_name`: Name of the clicked navigation link
- `link_location`: Location of the link (navbar)

## Next steps

We've built some insights and a dashboard for you to keep an eye on user behavior, based on the events we just instrumented:

### Dashboard
- [Analytics basics](https://us.posthog.com/project/275472/dashboard/959496) - Core analytics dashboard with key user engagement and conversion metrics

### Insights
- [Event Card Clicks Over Time](https://us.posthog.com/project/275472/insights/viCQNwCF) - Track daily event card click trends
- [Explore Button Clicks](https://us.posthog.com/project/275472/insights/PvbU1ftM) - Monitor explore button engagement
- [Navigation Link Clicks](https://us.posthog.com/project/275472/insights/QI8UDEfX) - Understand navigation patterns by link name
- [Event Discovery Funnel](https://us.posthog.com/project/275472/insights/tLh2LOUj) - Conversion funnel from pageview to event exploration to event click
- [Most Clicked Events](https://us.posthog.com/project/275472/insights/RXrod21j) - Identify which events are most popular

## Additional Features Enabled

- **Automatic Pageview Tracking**: PostHog will automatically capture pageviews via the `defaults: '2025-05-24'` configuration
- **Error Tracking**: Unhandled exceptions are automatically captured via `capture_exceptions: true`
- **Debug Mode**: Debug logging is enabled in development mode for easier troubleshooting
