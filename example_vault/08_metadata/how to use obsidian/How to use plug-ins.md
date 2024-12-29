Here I will list all the plug-in's that come with my personalized vault,  what each does, and how you can use it.
sorted by complexity (least-most):
- `calendar`: simple plug-in
	- enables a side-panel view of a calendar
	- you can browse through daily notes using it
	- [no changes from default]
- `homepage`: a file that opens when you start obsidian
	- I also use it in this vault to open today's daily note and prompt for the templater's command (which is different than the native template)
	- [changes from default:]
		- open homepage file on start up
		- pin
		- 2 commands: 1 to open today's daily, and another to insert templater modal
- `tracker`: not using currently but it can get complex
	- [no changes from default]
- `tasks`: create tasks
	- tasks can be created and filtered using tags
	- natively it's configured to display tasks using `#tracker/task`
	- you create a task simply by creating a checklist item `- [ ]`.
	- I also plan on using it to implement the habits feature
	- [no changes from default]
- `templater`: create powerful templates
	- I am using it to create a drop-down menu that prompts the period tracker
	- very powerful, but very difficult to use
	- [no changes from default]
- `dataview`: big-data
	- used to query notes, create tables, personalized codes, etc..
	- I use it with the `templater` for simple logic (ex. if no period, don't prompt flow, etc.)
	- I use it on my main vault to:
		- create tables for all my: indexes; resources. Using tags
		- create graphs of which days I worked/studied: using tags
		- can be used with properties for anything
			- properties can be anything you create, I use properties for the period tracker by using the in-line property feature of dataview -> `::`.
	- [changes from default:]
		- enable dataviewjs queries
		- enable everything you can

There are so many plug-ins in obsidian, you can customize it however you would like to. Some require a bit more coding than others, but chat GPT comes through 98% of the time.