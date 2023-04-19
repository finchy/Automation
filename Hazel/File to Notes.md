File to Notes.md

As indicated by other scripts in this repo, I am a heavy user of "Notes.app" for all note taking on my devices.  For a lot of reasons, mostly because it's a native app, which means any additional features that Apple adds in the future, all my notes will be able to grab.  So, one of the things I do is I add a bunch of documents to Notes.app.  I wanted a way to do this automatically, for things like Scans.  I have a Fujitsu ScanSnap iX1500 scanner that is tied to the ScanScap Cloud, so when I scan a document, I have an integration setup through Dropbox (and several other apps) to move files into my Notes.app.

This Hazel script:

<img width="884" alt="File To Notes" src="https://user-images.githubusercontent.com/2027717/232879065-13e6fb05-ce5e-4b81-9769-d11f19223502.png">


Executes the following "Documents.scpt" script:

```
on hazelProcessFile(theFile, dummmy)
	tell application "Finder"
		set extension hidden of theFile to true
		set theName to displayed name of (theFile)
		set extension hidden of theFile to false
	end tell
	
	set incomingFile to the POSIX path of theFile
	set noteBody to "<html><head>" & theName & "</head><body></body></html>"
	tell application "Notes"
		set newNote to make new note at folder "Scans" with properties {name:theName, body:noteBody}
		make new attachment at newNote with data theFile
	end tell
	
end hazelProcessFile
```

Which will take a file that I have in the "Scans" folder (when a new file is placed there) and creates a Note in Notes.app and attaches the file to it.

The original thread that gave me this idea is [here](https://www.noodlesoft.com/forums/viewtopic.php?f=3&t=7373)
