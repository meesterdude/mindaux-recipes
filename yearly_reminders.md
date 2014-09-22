# Yearly Reminders

In this recipe, we'll setup assorted yearly reminders and create a saved search to send them to us.

Lets create some items via the search actions.

    ;; candy sale after valentines/holloween
    %(+: @ February 15th; +: @ November 1st) #yearly #reminder
    ;; winter is coming, do I have the right snow gear and clothing?
    %(+: @ October 31st) #yearly #reminder
    ;; Taxes are due to file soon #yearly #reminder
    %(+: @ april 15th; +: @ June 15; +: @ September 15; +: @ December 15)
    #yearly #reminder
     ;; Schedule doctors checkup #yearly #reminder
    %(+: @ July 20th;)
    ;; I should probably start working off this holiday weight
    %(+:  @ December 26th) #yearly #reminder

You'll note they all have been tagged as `yearly` and `reminder` and contain `occurrence` metadata for the relevant dates.

## Saved Search Fields

Add the following to the `query` field:

    tagged:(yearly reminder) *.occurrence.yday:now.yday(14) -*.acknowledged.date:<now-1M


To have this run every 3 days at 7AM, you could define the schedule like so:

    Minute: 0
    Hour: 7
    day: */3
    month: blank
    days: blank

With this in place, you'll get a 2 week heads-up for anything coming up soon that you need to take care of. It also allows you to indicate something as `acknowledged` with the appropriate metadata, to take them off your radar (but still allow them to appear again when relevant).


