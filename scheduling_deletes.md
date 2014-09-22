# Scheduling Deletes

In this recipe, we're going to set things up so that any item or list tagged as `delete` gets deleted. This is great for groups that need to collaborate on various information, as it allows for business rules and review processes to take place first.

This recipe assumes that you simply tag lists and items as `delete` when you want to delete them. It also will make sure they haven't recently been updated, and aren't tagged as `important`.


## Saved Search Fields

Add the following to the `query` field:

    tagged:delete -tagged:important updated:<now-1d ;; !delete

To have this run every weekday at midnight, you could define the schedule like so:

    Minute: 0
    Hour: 0
    day: blank
    month: blank
    days: 1-5


If you want to make sure that items marked for delete get reviewed first, you could setup another saved search to email someone everyday the things that are due to be deleted. Anything they want to keep they can untag as `delete` and the rest will get automatically purged.