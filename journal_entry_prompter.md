# Upcoming Birthdays

In this recipe, We'll setup an email that will be sent to us every nigh if we haven't created a journal entry recently.

This assumes that you have items tagged as "journal"

## Saved Search Fields

### Name

Lets call this "It's time for a journal entry"

### Query

Add the following to the `query` field:

    type:item tagged:journal created_at:>now-1d

### Fail Text

Add the following to the fail text field:


    %(
      mood:  happy/normal/sad/excited/angry ;
      sleep_quality: good/ok/bad/none
    )


    #journal

    !stop

When we receive the email, it will already contain the right tag and have some metadata we can make sure we capture. The only thing we need to do is reply, delete the header, (optionally) decrease the quote level (if you don't want it showing up in your item) and then fill in the message with your journal entry, and pick one of the options from each of the predefined metadata. The `!stop` means that anything after it will be ignored, so you don't have to delete trailing content.

To have this sent every night at 8PM, we would fill out the fields as follows:

    Minute: 0
    Hour: 20
    day: blank
    month: blank
    days: blank

