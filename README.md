# What is Obsidian?

[Obsidian](https://obsidian.md/) is really cool and free note-taking app that wants to be your second brain. To learn more about it, check out my [Obsidian overview](https://medium.com/swlh/take-better-notes-with-this-free-note-taking-app-that-wants-to-be-your-second-brain-1a97909a677b) and [how I use it to take notes](https://medium.com/swlh/how-to-take-notes-insights-from-ai-neuroscience-a-sociologist-and-a-free-app-34b4be63080a) (and [why we take notes](https://medium.com/swlh/why-take-notes-3-common-misconceptions-and-3-better-mindsets-447ef6853aa9)).

# Alfred workflow for Obsidian

This simple [Alfred](https://www.alfredapp.com/) workflow uses [Obsidian](https://obsidian.md/)'s [URI scheme](https://publish.obsidian.md/help/Advanced+use/Using+obsidian+URI) (available in version 0.8.15 and above) and JXA actions/scripts (thanks to [@hjklapp](https://github.com/hjklapp)) to open notes in their vaults. This workflow has been tested in Obsidian 0.9.16.

Available Alfred features/keywords (contributors in parentheses)
- Open a vault: `ov`,`oo` ([@hjklapp](https://github.com/hjklapp))
- Search in vault(s): `os`, `or`, `ot`
- Open a daily note in a vault: `od` ([@technicalpickles](https://github.com/technicalpickles), [@luckman212](https://github.com/luckman212))
  - You can also use a Hotkey to open your daily note.
- Fallback search when there are no results ([@technicalpickles](https://github.com/technicalpickles))
- Get help by opening [help vault](https://publish.obsidian.md/help/Index) and [forum](https://forum.obsidian.md/): `o?` 

## Installation

Download the [Obsidian.alfredworkflow](https://github.com/hauselin/obsidian-alfred/raw/master/Obsidian.alfredworkflow) file. Add to Alfred and enjoy the workflow! Only tested in Alfred 4.

## Features that require no set-up

### Open a vault: `ov`

To open one of your many Obsidian vaults, type `ov your_vault_name`. If you vault name is `my notes`, you type `ov my notes`. You can change the keyword input subtext to remind yourself of the names of your vaults. Double-click **ov Keyword** to change the Subtext field.

All other features require a one-time set-up.

## Set up

- Add your vaults, one at a time: `oaddvault`
  - Note that Obsidian's help vault has been added by default.
- To clear all vaults other than Obsidian's help vault: `oclearvaults`

If you use Obsidian's Daily notes plugin, you'll also need to set it up.

- Specify daily vault: `odailyvault`
- Specify daily note format: `odailyvault`
- Specify daily note directory/path: `odailypath`
  - Example: The date is 1st March 1990. 
    - If your date format is 1990-3-1, enter `yyyy-m-d`
    - If your date format is 900301, enter `yymmdd`
    - If your date format is 1_3-90, enter `d_m-yy`
- Specify daily note template: `odailytemplate`
  - Required only if you have a template for daily notes.

## Features available after set-up

### Open a vault with autocomplete: `oo`

- To autofill and autocomplete Obsidian vaults (suggested by [@hjklapp](https://github.com/hjklapp)): `oo your_vault_name`

![](img/oo.gif)


### Open daily note: `od`

- The Daily notes Obsidian plugin must be enabled.
- `od` will open your daily note, assuming you've set up your workflow environment variable correctly (instructions above). Alternatively, you can use a hotkey.

### Search Obsidian vaults with Alfred File Filters; `os`, `or`, `ot`

- Search for all files with the term `xyz`: `os xyz`
- Search for recent files (last 3 days) with the term `xyz`: `or xyz`
- Search for files modified today, `xyz`: `ot xyz`

### Alfred fallback search

New in v0.1.5. Supports Alfred [fallback searches](https://www.alfredapp.com/help/features/default-results/fallback-searches/) (i.e., "Fallback searches are the list of search options you see when you search for a keyword that doesn't match a result on your local Mac."; see screenshot below). Thanks [@technicalpickles](https://github.com/technicalpickles) for suggesting this feature.

![](img/fallback.png)

When a fallback search is invoked, the workflow will ask which vault you want to search in. To set it up, follow these steps: 

- Go to Alfred's **Features** pane, click **Default Results pane**, click **Setup fallback results** at the bottom, click the **+** icon, add a **Workflow Trigger**, add **Search Obsidian for {query}**, reorder the fallback searches however you prefer, and click **Save**.


![](img/fallback2.gif)

## Known bugs

If the Obsidian app isn't already opened, this workflow will always open the last recently opened vault. This bug is a known issue with Electron apps on MacOS. See [discussion on Obsidian's Discord](https://discordapp.com/channels/686053708261228577/716028884885307432/755203478413902036).

## Contributors

Alphabetical order

- [@hjklapp](https://github.com/hjklapp)
- [@ldebritto](https://github.com/ldebritto)
- [@luckman212](https://github.com/luckman212)
- [@technicalpickles](https://github.com/technicalpickles)

