# Todo List Reminders

With this recipe, any open todo item you have that is either due soon, or that you haven't seen in a few days, will be emailed to you.


## Saved Search Fields

Add the following to the `query` field:

    tagged:todo type:item status:open (*.due.date:>now-1d || last_viewed_for.user(frank):<now-5d)

if it's just you, or you want to see things nobody on your team has seen, you can use the shorter `last_viewed` like so:

    tagged:todo type:item status:open (*.due.date:>now-1d || last_viewed:<now-5d)


To have this sent to us before and after every day of work (8:30/5:30), we would fill out the fields as follows:

    Minute: 30
    Hour: 8,17
    day: blank
    month: blank
    days: 1-5