## Omnifocus2Reminders.md

Accompaying Script to Omnifocus2Reminders

I based this script on someone else's script, and who that is, I have lost to time, and I apologize, if you're that person, please drop me a line so I can credit you.

Action: Highlight the tasks in Omnifocus you want to copy, and then run script.  If the tag in the Omnifocus task matches the thing in `tagList` then it will drop the task in Reminders in the list named whatever is in `tagList`, otherwise, it will just drop the Reminder in the Inbox.  (I originally copied all tasks over and had the script create a bunch of project in Reminders, but it got big quick.)

Why: I wrote this to move from Omnifocus to Reminders when Apple released tags in Reminders, so I can have my apps be native.  You can't access the `tags` function in the new Reminders.app with the AppleScript Dictionary.  (I hope that Apple fixes that.)