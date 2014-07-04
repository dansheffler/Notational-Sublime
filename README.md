
# Notational Sublime #

I'm leaving this up in case some other people find it useful or want to fork it. I have switched over to using Vim, however, so I don't plan on maintaining this or developing it further.


## Settings ##

There are two settings which Notational-Sublime looks for. `notational_directory` is the directory where you keep your Notational Velocity (or my preferred version, nvAlt) notes. It defaults to `~/Dropbox/Notes/`. `notational_extension` is the extension which you prefer for your files. It defaults to `.md`.

## Wiki-style Links ##

In Notational Velocity text surrounded by square brackets [[like so]] becomes a link to a note with that title (actually it places the text between the brackets in the search field, but we won't be doing that here).

Notational-Sublime replicates the way that Notational Velocity will auto-suggest already existing note titles when you begin to type a link. It does this with the `insert_note_link` test command which will pull up a quick-input-panel with a list of all the note files in your notes directory. A default key-binding is supplied so that typing the left-bracket twice will call this command.

You can open these links using the `follow_note_link` command. This command will take selected text and open up a note with that title if it exists and create it if it doesn't. I also created a macro which will first expand the selection to the matching brackets around the cursor then run the `follow_note_link` command which can be usefully assigned to a key-binding.

The default key-bindings involve the `.extendedmarkdown` scope selectors which is what I use, but they can be switched to whatever you want.

## Search-and-Create ##

A slightly more experimental feature is an emulation of the search and create at the same time functionality of Notational velocity. This is accessed through the `note_search` text command. When this command is invoked a small view is brought up in a new group to the left of the main group and an input panel is invoked. As you type text into the input panel Notational-Sublime will run a Spotlight search in your notes directory and return the results in the new search results group.

If the text you have typed so far matches the beginning of a note title Notational Sublime will outline that note in the search results and it will load a transient view into that note in the main group (i.e. the note will not open a new tab unless you modify it). Notational-Sublime will also attempt to auto-complete the rest of the note title in the input panel. If the suggestion isn't what you want you can simply enter delete to clear it.

At any point, hitting enter will close the search results and take you to a note with the title of the text in the input panel. If this note already exists it will simply open it, if it does not it will be created.


