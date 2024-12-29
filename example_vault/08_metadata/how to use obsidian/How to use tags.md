Tags in obsidian are a great way to keep stuff organized. This is because you can see tags as folders (with the plug-in already installed) and therefore, organization can be kept on a need-basis instead of creating folders without a clear direction.

tags work by starting with `#` followed by whatever you want. You can nest tags using `/`, and there is no limit (that I am aware) of how nested it can get.

With tags you can track time (together with the dataview plug-in), as you can filter out files by their tags, and extract information by using dataview's built in `::` in-line format.

With tags you can classify subject notes without having the folder structure.

With tags you can organize files of the same 'feature'. For example I keep all things related to `changelog` with the `#changelog` tag, so that I can even query and create a table of all notes of a specific feature. 
I do this by creating `Index` tables where I filter using the `#index`, and so forth.

Tags can be placed in-line "#example", or by adding to the file's property.

>[!Tip] Tags Best Practices
>Keep the parent tag for a specific feature
>Nest tags if you need to organize files (tracking time does need, but changelog doesn't)
>Keep it simple to start (I know I am keeping it sooo simple)

How tags are done in this example vault:
*includes excerpts from different files*
**Subject Note Tags:**
`#note/subject/optional`
normally I try to keep subject as a big thing: `certification` and each certification I am currently working on as the optional. ex: `#note/certification/NetworkPlus`
**Index Tags:**
`#index/subject`
or could be simple `#index`.
**Changelog Tags:**
`#changelog` = How I plan to use, rules to myself
`#changelog/update` = each subsequent entry
**Other Tags:**
- `#idea` 
	- non-organized note about those late night ideas that you do not want to lose
- `#project` 
	- everything related to a project, could be adapted to be `#book` for example
- `#things`
	- how I kept track of ideas of gifts for x-mas
	- organizing things I want, for example new computer parts
- *endless* opportunities of tags
	- it really is up on how you want to classify/organize your second brain!
**Tracking Tags:**
*tracking includes: tracking time, tracking tasks, tracking habits*
- `#tracker/task`
	- I use together with the Tasks plug-in in order to create a task anywhere in the vault and be able to query it inside a daily note
	- should be the primary way of creating tasks
- `#tracker/habit`
	- is for tracking whether or not I have done something on the day of
	- still not working at the time of writing
	- tracks things like: flossed, smoked, etc...
- `#tracker/time/[type of event]`
	- logs an estimate of time spent on each thing
	- `#tracker/time/breakfast` Hours:: 1
		- the `Hours:: #` is essential
		- it's how I will be able to query the daily notes and be able to know how much time was spent on each thing
	- can be as wide or narrow as you want