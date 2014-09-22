# Chore Reminders

This recipe will show you how to get reminders for various chores you may have.

This recipe assumes you have items acting as tasks that you want to perform, that are tagged with `chore` and a particular schedule tag. Here's what we'll be using in this example:

    3xday
    2xday
    daily
    every2days
    every3days


## Saved Search Fields

### Query

Add the following to the `query` field:

    tagged:chore (
    (tagged:3xday *.occurrence.date:<now-8h) ||
    (tagged:2xday *.occurrence.date:<now-12h) ||
    (tagged:daily *.occurrence.date:<now-24h) ||
    (tagged:every2days *.occurrence.date:<now-48h) ||
    (tagged:every3days *.occurrence.date:<now-72h) ||
    (tagged:everyweek *.occurrence.date:<now-1w)
    )

and lets set the schedule to be every 2 hours starting from 6AM and stopping at 10PM:


    Minute: 0
    Hour: 6,8,10,12,14,16,18,20,22
    day: blank
    month: blank
    days: blank

## Putting It In Action

With this setup, you'll be reminded of chores that you haven't done, until you do them. To indicate that you've done something, you can update the occurrence value for the item.

If you want to track every occurrence of when you did something, you'll need to modify the query like so:

    *.occurrence.date:<now-72h tagged:every3days -*.occurrence.date:>now-72h

with this change, only things that have an occurrence value older than 72 hours, and not one newer than that, will be valid.

You can also set an occurrence of your chores to sometime in the future, if you don't want to receive anything for that particular item for a few days but don't want to stop the Saved Search from running.

