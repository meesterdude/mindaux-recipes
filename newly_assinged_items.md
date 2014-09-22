# Newly Assigned Items

In this recipe, we'll setup a saved search that will email us any items that have been assigned to us that we haven't seen yet.

This recipe assumes that you have an `assigned_to` metadata attribute on your items. This field can either contain one persons name (or ID) or multiple separated by space. Or, you can define multiple `assigned_to` attributes.

## Saved Search Fields

Add the following to the `query` field:

    -last_viewed_for.user(frank):* assigned_to:frank


To have this run every weekday morning at 7AM, you could define the schedule like so:

    Minute: 0
    Hour: 7
    day: blank
    month: blank
    days: 1-5







