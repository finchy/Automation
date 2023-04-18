Current Email to Reminders.md

Link: https://www.icloud.com/shortcuts/ff61e617f1f64a61b6c4e28c4f2d4801

About: This is a services menu script for `Mail.app` that creates a task in `Reminders.app` with a link back to the email.  It's a universal link, so it'll work across devices like iPhone and iPad OS.  It only works on macOS though, as an origin, because it has to run this applescript (that is in the shortcut).

```
tell application "Mail"
	set msgs to selected messages of front message viewer
	if (count of msgs) is 1 then
		set selMsg to item 1 of msgs
		set msgID to message id of selMsg
		set msgURL to "message:%3C" & msgID & "%3E"
		set msgTitle to subject of selMsg
		return "📧 " & msgTitle & "^" & msgURL & ""
	else
		activate
		display alert "Selection" message "Please select a single Mail message." buttons {"OK"}
		error number -128
	end if
end tell
```

/That script is in the Shortcut already, I am just copying and pasting here for ease of use./

I find this easier than highlighting the subject of an email and clicking share to create the link back to an email in reminders.  

*Apple, you really need to just create a native integration from Mail.app to Reminders that allows you to select some text in an email, and it creates a reminder that links back to the email, and you can see your reminders checked off in an email*