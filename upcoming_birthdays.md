# Upcoming Birthdays

In this recipe, We'll look at how easy it is to get birthday reminders 2 weeks before they happen.

This assumes that you have items with a name of "birthday" and a date that is their actual birthday. This could be your friends, family, or a long since passed historical figure.

## Saved Search Fields

Add the following to the `query` field:

    *.birthday.yday:now.yday(14)


To have this sent 3 times a week at 7AM, we would fill out the fields as follows:

    Minute: 0
    Hour: 7
    day: blank
    month: blank
    days: 1,3,5