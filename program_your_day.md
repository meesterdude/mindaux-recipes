# Program Your Day

With this recipe, you'll be able to schedule reminders for yourself throughout the day, relative to when you woke up. This is great if you have a sleep schedule that changes but still want to setup reminders for yourself, and can't rely on specific times and a regualr reminder system.

## Creating The Shortcut

Let's create a new shortcut, and give it a description like `Program my day's schedulee`

for the key, lets simply put `awake`

for the expansion, we'll want to create each reminder that we want to have created.

    Eat breakfast %(+: @ in 20 minutes) #schedule
    ;; Exercise %(+: @ in 1 hour) #schedule
    ;; Shower %(+: @ 1 hour 30 minutes from now ) #schedule
    ;; Work %(+: @ in 2 hours ) #schedule
    ;; Take a break %(+: @  4 hours 30 minutes from now ) #schedule
    ;; break for lunch %(+: @  6 hours 30 minutes from now ) #schedule
    ;; Take another break %(+: @ 7 hours 30 minutes from now ) #schedule
    ;; you should get to bed soon %(+: @ 15 hours from now ) #schedule

Note that we sometimes used `in` and other times used `from now`. `in` only supports one type of time, while `from now` supports two (such as hours and minutes). In general, your best bet is to stick with `from now` to avoid any problems.


## Creating the Saved Search

The Saved search for this will have a query like this:

   *.occurrence.date:[now-30m TO now+30m] tagged:schedule

And we'll set it to run every half hour, between 7AM and 11PM on weekdays:

    Minute: 0,30
    Hour: 7-23
    day: blank
    month: blank
    days: 1-5

## Putting It In Action

Anytime we want to trigger our program, we can just send in an email containing `:awake`, or submit a search query like `;; :awake`.

Note that if you start your first line in the shortcut with a `;;` and use the shortcut in an email, you may get a blank item created.

It's also probably a good idea to create another Saved Search that deletes anything tagged `schedule` that was created more than 20 hours ago, and have it run once a week.