# refablab-calendars-shopify
Two custom Shopify section components built with Liquid + JavaScript for Refab Lab, a wood workshop in Malmö, Sweden.
Both sections are fully configurable from the Shopify theme editor without touching code.


## 1. Event Calendar with Images
Displays workshop and class bookings in a monthly calendar grid,
pulling all event data dynamically from product metafields.

**Features**
- Reads event dates, start times, and durations from custom product
  metafields across multiple product templates
- Supports per-event special end times via a secondary metafield list,
  with automatic duration fallback
- Displays product featured images inline in each calendar cell
- Click-to-modal: shows full event image, time range, description,
  and direct product link
- Mobile responsive: compact grid on small screens,
  tap-to-modal replaces hover behaviour
- Bilingual (EN/SV) via Liquid i18n — language switches automatically
  based on storefront locale

**Tech**
- Liquid (data layer, i18n, metafield resolution)
- Vanilla JavaScript (calendar rendering, modal, navigation)
- No third-party dependencies


## 2. Lab Access Calendar
Displays recurring lab access slots with availability logic, 
cross-referenced against live workshop schedules.

**Features**
- Weekly recurring schedule (daytime / evening slots) configurable 
  entirely via Shopify section blocks — no code changes needed
- Exception dates manageable from theme editor: 
  mark specific slots as closed, or add one-off extra slots
- Automatic workshop conflict detection: reads all upcoming workshop 
  dates and durations from product metafields, computes time overlap, 
  and marks conflicting lab slots as unavailable
- Three-state modal logic based on customer tag:
  - No purchase → shows product page link to buy access
  - Active package → redirects to orders page to book a session
  - Unavailable slot → shows unavailability message, no CTA
- Color-coded slots: green (daytime), amber (evening), grey (unavailable)
- Bilingual (EN/SV) via Liquid i18n

**Tech**
- Liquid (customer tag detection, product lookup, 
  metafield resolution, section blocks schema)
- Vanilla JavaScript (calendar rendering, conflict detection, 
  modal state management)
- No third-party dependencies
