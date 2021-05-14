# Table of Contents
* [Introduction](#introduction)
* [Prerequisites](#perquisites)
* Translation Process
	* [Step 1: Setup](#step-1-setup)
        * GitHub
        * Poedit
        * DevilutionX preview
	* [Step 2: Translation Mindset](#step-2-translation-mindset)
	* [Step 3: Testing](#step-3-testing)
	* [Step 4: Publishing](#step-4-publishing)
* Questions

# Introduction

_DevilutionX_ allows for easily translate the game to new languages and make it more accessible for new players. As an open source project the translations are, however, made and maintained by the community. Unlike the development part of _DevilutionX_ this doesn't require technical skill.

This document aims to be a comprehensive and easy to use entry point to get started adding additional translations for non-tech persons. If you know your way around feel free to skip the further introduction and start with **Translation Mindset**.

This Wiki focuses on the setup process on Windows and Mac. Feel free to reach out to the official [Discord Channel](https://discord.gg/YQKCAYQ) if you need assistance setting it up in Linux.

# Prerequisite

Programs:
* Git Client (recommended for inexperienced users: [GitHub Desktop](https://desktop.github.com/))
* [Poedit](https://poedit.net/)
* Latest DevilutionX [preview Version](https://github.com/diasurgical/devilutionX/actions?query=branch%3Amaster+is%3Asuccess) for testing

# Translation Process

### Step 1: Setup

Download all three above mentioned Programs from their respective websites. We will begin with setting up GitHub Desktop.

**GitHub Desktop**:
- Windows: Use the .exe installer to install the program as usual; Mac users: Extract the .dmg from the .zip file and install the program as usual. 
- Start GitHub Desktop and create an account or login if you already have one.
- Click on "File -> Clone Repository"
- Change to the URL Tab and add `https://github.com/diasurgical/devilutionX`
- Chose a local path and click "OK"

GitHub Desktop will now copy all development files from the GitHub repository of _DevilutionX_ to your drive. Even if you do not plan to program or compile the software yourself this is a necessary step.

It is heavily suggested that you update the development files before you start a new translation session. To do that open GitHub Desktop and click on "Fetch origin". 

**Poedit**
- Windows: Use the .exe installer to install the program as usual; Mac users: Extract the dmg from the .zip file and install the program as usual. 
- Start Poedit 
- Click on `Open` in the upper left corner. Browse to your local copy of the GitHub repository as created in the first step.
- In the folder structure open `../devilutionx/Translations/devilutionx.pot` if there is no translation to your language currently available. Otherwise please select an `.po` file corresponding to the two letter language code from the same folder. (e.g. `dk.po` for danish)
- If you want to start translating into a new language click on `Create new translation` button within Poedit and select the language you want to translate into. 

**DevilutionX preview**

Since the localization feature is not yet implemented in the latest release we will have to create a local preview copy of the game. 

- Grab the latest stable release from [here](https://github.com/diasurgical/devilutionX/releases)
- Extract the release and copy the corresponding mpq files (Hellfire is suggested) into the folder. If you need more information about that process please refer to the [installation guide](https://github.com/diasurgical/devilutionX/blob/master/docs/installing.md)
- Download one of the latest successful artifact builds from [here](https://github.com/diasurgical/devilutionX/actions?query=branch%3Amaster+is%3Asuccess)
- Select your operation system on the left and then select the newest build on the right. Download the `.zip` file and extract the new devilutionx.exe to the above created installation.
- Modify your diablo.ini Depending on your system you can find your `diablo.ini` in the following locations:

	- macOS `~/Library/Application Support/diasurgical/devolution`
	- Linux `~/.local/share/diasurgical/devilution/`
	- Windows `%AppData%\diasurgical\devilution`

- Make sure to create a backup of your current `diablo.ini` and then delete the original file; then start the `DevilutionX` preview version. This will generate a new `diablo.ini` which includes a setting named `Code=en`. Change the `en` to your language.

### Step 2: Translation Mindset

Translating a video game is not simply done by changing words into your language but requires quite some thought. To ease your first steps with translating in this medium here are some general notes to get your started. The most important rule, however: 

**You are not translating for yourself.**

This might sound obvious but never forget that your text will seem to be easily comprehensible to yourself, yet might be less obvious for others. To ensure it works for others as well here are some really basic rules:

* Try to be as explicit as possible. If you have to use abbreviations make sure they are well known (e.g. "Level" to "LVL" is likely understandable but if you have enough room please stick with "Level". Try to avoid making things up, e.g. "vel" would be a bad idea).
* Test early, test often. To ensure that everything looks right and is readable try to test as much as possible. Try to limit things that have to be tested to a few, maybe a dozens, translated keys. - See Step 3 for a guide.
* Ask for help if you don't know something. Either if you are trying to test for errors which you don't know how to cause or if the context of a string isn't clear. The people on Discord are welcoming and friendly and there are no "stupid questions". However: Contributors also have a live outside of developing DevilutionX, please leave them time to reply and just continue with the next string instead.
* Grammar and orthography should be correct however you can and should take your liberties to keep the atmosphere alive. (E.g.: Griswold has a heavy dialect in the game, you can reflect that. A good approach might, for example, be translating it into a local dialect.)
* Building up on the previous point: Work to create atmosphere. Your texts should aim to keep peoples fun alive.
* If you know somebody who'd is native in the language let them play and play test!
* If somebody changes something you translated they will have the same good intentions as you do. If you are unsatisfied with something you should reach out to the person. Stay friendly. :) 
* Keep track of things. E.g. Make sure that names are always translated the same way.

**Important**: Currently DevilutionX doesn't show international symbols correctly. Please feel free to use them anyway; they might not be displayed or not correctly displayed at the moment bu that will be fixed by the final release.

### Step 3: Testing

After you translated a few strings it's advisable to save and test your changes. To do so simply press the "Save" button in Poedit and save your translation. If you create a new file save it with the two letter language code and the file ending `.po`. In the standard settings Poedit will also create a second file with an `.mo` file extension. Copy the `.mo` file to your DevilutionX preview folder.

Now start the DevilutionX preview we created in Step 1. Play the game to see your changes. 

It is generally advisable to keep Poedit open and directly apply changes if needed. Unfortunately you will have to restart the game to see new changes.

### Step 4: Publishing

After you tested your translation you can now upload it back to GitHub where it will then be merged into the main repository and made available for others to use or add to your work.

To do so we have to follow a few steps:

- Open GitHub Desktop
- It will show you the files you've created or changed (a so called `diff`, short for differences)
- Add a summary in the lower left corner(e.g. `added translation to Latin`) and a fitting description (suggested: Number of translated strings so far, which can be seen in the lower left corner of Poedit and percent).
- If you changed an existing translation you should also add what and why you changed it. You don't have to go into detail more like "Fixed typos in quest texts."
- Since you won't be able to directly write to the main repository you can create a `fork`. Just click on the link and the application will guide you through the steps.
- Select `To contribute to the parent project` and click continue.
- Now you can click on "Commit to **master**"
- Now press the blue button in the main Window labeled `Push origin`.
- If an error message shows up click on `Fetch`, then `Pull origin`, then `Push origin` again.
    - If there was an update make sure to click on `Update from code` to ensure your translation database is up-to-date.
- Your changes are now uploaded to GitHub! :) 
- To send your translation to the main repository go to [Pull requests](https://github.com/diasurgical/devilutionX/pulls)
- Click on `New Pull Request` in the upper right corner.
- Under Click on the Link `Compare across forks.`
- In the right drop down select your repository (`YourUsername/devilutionX`) and then finally click "Create pull request". 

Thats it! Your translation will now be checked for technical errors and then be published. You can now officially call yourself an open source contributor. :) 

## Questions

If you have any questions please reach out on [Discord](https://discord.gg/YQKCAYQ)