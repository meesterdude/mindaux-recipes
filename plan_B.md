# Plan B

In this recipe, We'll setup an email that will go out to someone if we haven't been active recently, so someone can check in on our cats for us.

## Important Disclaimer
You understand and agree that MindAUX is not liable for any direct, indirect, incidental, special, or consequential damages such as loss of profits, data, or life.
 MindAUX is not designed or intended for uses that involve risk to life or injury or other critical uses. MindAUX is subject to failure and makes only a best effort at uptime, availability and functionality. Per the Terms of Service, Your agree to use and accept MindAUX "as-is" and absolve it of any liability.

## Saved Search Fields

### Name

Something attention grabbing, like "IMPORTANT: Please check on my cats"

### Query

Add the following to the `query` field:

    updated:>now-2d

### Fail Text

Put whatever message you want the person to receive, such as where to get the key, pet allergies, and diet.

    Hey, I need you to check on my cats. You can get the key from the landlord.

Lets have this attempt to run two times a day at 6AM and 6PM:

    Minute: 0
    Hour: 6,18
    day: blank
    month: blank
    days: blank
