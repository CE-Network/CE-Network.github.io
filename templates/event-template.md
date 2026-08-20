---
# ============================================================
# HOW TO ADD A NEW EVENT
#
# 1. Copy this whole file into the _events folder.
# 2. Rename it to the event's date and a short name, e.g.:
#      _events/2027-03-12-spring-networking-drinks.md
#    The filename doesn't matter to the website — only the "date:" field
#    below does — but dating the filename keeps the folder easy to scan.
# 3. Fill in the fields below. Keep the quotes around any text that has
#    a colon, apostrophe, or "&" in it.
# 4. Replace the paragraph at the very bottom (after the second "---")
#    with your event's description.
# 5. Save, commit, and push. The site rebuilds automatically within a
#    minute or two. Whether it lands in "Future Events" or "Past Events"
#    is worked out automatically from the date field below.
# 6. You can leave these "#" lines in place if you like — they are
#    comments, invisible on the actual website either way.
# ============================================================

title: "Your Event Title Here"
event_type: "One short line describing the format, e.g. Full-day symposium for PhD candidates and postdocs"

# Date format is YYYY-MM-DD, no quotes.
date: 2027-01-01

# Optional — leave out entirely if you don't want a time shown. Free text,
# write it however reads best: "14:00", "09:00–17:00", "Doors at 18:30".
time: "09:00–17:00"

location_name: "Venue name, building"
location_address: "Street and number, postcode City"
location_url: "https://www.google.com/maps/place/..."

# Leave the next two lines out entirely if registration isn't announced yet.
registration_opens: 2026-12-01
registration_note: "The registration form will be shared here and in our [LinkedIn group](https://www.linkedin.com/groups/12075890/)."

# Optional — leave out entirely if there's no funder/supporter line to add.
credit: "Supported by ..."

# Optional — leave out entirely (delete these lines) for an event with no
# programme. "Programme" is the default heading; set programme_title to
# override it, e.g. to "Preliminary Programme" before it's finalised.
# To add a step, copy one "- title: ..." block including both of its lines.
programme_title: "Preliminary Programme"
programme:
  - title: "First programme item"
    description: "What happens in this part of the day."
  - title: "Second programme item"
    description: "What happens in this part. You can link things like this: [Community Sense](https://www.communitysense.nl/)."
---
Write one or two paragraphs describing the event here, below the second
"---" line above. This part uses plain writing, not the field: value
format above — just write normal sentences. You can still **bold** words
or add [a link](https://example.com) if you want to.
