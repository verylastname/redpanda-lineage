# Red Panda Lineage

## How to Contribute to the Red Panda Lineage

[![Get Ready, Lychee](https://raw.githubusercontent.com/wwoast/redpanda-lineage/master/docs/images/instructions/lychee-get-ready.jpg)](https://raw.githubusercontent.com/wwoast/redpanda-lineage/master/pandas/0001_ichikawa/0004_lychee.txt)
 
To make contributions to this dataset, you'll be using tools similar to what software developers use. Don't be afraid -- we'll teach you how, even if you don't know how to write code at all!

## Getting Started: Windows and Mac Users

To work with the Red Panda lineage dataset, you only need two things:

 * [Visual Studio Code, a/k/a *VS Code*](https://code.visualstudio.com): a free, professional-grade text editor
   * It includes a simple-to-navigate sidebar, crucial for checking references across the dataset
   * It fully supports UTF-8 and CJK (Chinese, Japanese, and Korean characters) in the dataset records
   * It also has first-class support for the *Git* source-control tooling
 * A free [*GitHub* account](https://github.com/join)
   * GitHub hosts source-code for software, as well as things like this red panda lineage project
   * It provides central management and workflows to help manage sprawling code or data projects
   * Contributions to this dataset are attributed to your GitHub account

In GitHub, search for `wwoast/redpanda-lineage`, and click Clone. Copy the GitHub _Clone with HTTPS_ URI that appears. 

TODOC: Show the GitHub clone URI discovery and the *VS Code* command prompt usage in a short video

Next, open Visual Studio Code. Type `Ctrl+Shift+P` (`Cmd+Shift+P` on Mac) to bring up the _Command Palette_. In the _Command Palette_ prompt, type _Clone_ and press *Enter*. Paste the Clone URI into the follow-up prompt. Now you have a local _working copy_ of the entire Red Panda dataset downloaded to your computer.

<img src="https://raw.githubusercontent.com/wwoast/redpanda-lineage/master/docs/images/instructions/windows-default-folders.png" />

TODOC: what are the default locations that files appear? Show Mac, Windows, Linux

## Preparing VSCode for Editing

All panda and zoo editing starts in your _working copy_ of the `redpanda-lineage` repository. Assuming you are a Windows user, this is in your `TOWRITE` folder inside your user's home directory.

Launch *VS Code*, and select _Open_ from the _File_ menu. Navigate to your `TOWRITE/redpanda-lineage` folder, and click _OK_. The `TOWRITE/redpanda-lineage` folder has become your _workspace_, and you'll see the sidebar populate with the list of files and subdirectories in your _working copy_ repository. If you close and re-open *VS Code*, notice that it  will automatically re-open your `redpanda-lineage` folder and any files you had been editing. 

In the _sidebar_, you'll see the `/pandas` and `/zoos` folders. Underneath those you'll see subfolders for every zoo we've recorded pandas for. It's critical to keep the _sidebar_ of your files in view as you edit this dataset, **so you know what pandas or zoos already exist in the dataset**. In particular:

 * When adding a new panda file, you cannot re-use the ID number of an existing panda
 * When adding a panda to an existing zoo, you want to quickly determine if your panda already exists in the dataset

A typical workflow for updating the database is to have three applications open: a web browser for data retrieval, the GitHub Desktop app for managing changes to your branch, and your text editor inset in the GitHub Desktop window's dead space.

<img src="https://raw.githubusercontent.com/wwoast/redpanda-lineage/master/docs/images/instructions/explorer-example.png" />

## Creating A Branch to Work From

[![Time to Work, Lychee](https://raw.githubusercontent.com/wwoast/redpanda-lineage/master/docs/images/instructions/lychee-start-working-now.jpg)](https://raw.githubusercontent.com/wwoast/redpanda-lineage/master/pandas/0001_ichikawa/0004_lychee.txt)

GitHub repositories are managed in a very open-ended way. Any guest or contributor can clone the repository, giving them a full _working copy_ on their own computer. However, to contribute the changes from your _working copy_ back into the upstream `master` branch hosted on GitHub, you'll need to follow some guidelines.

TOWRITE: new images for creating branches
TOWRITE: new images for creating branches

The GitHub `wwoast/redpanda-lineage` repository has any number of secondary branches being worked on. Branches typically represent the collected work of a single contributor towards a single goal. Their branch might add a new zoo to the dataset, and a handful of pandas that live at that zoo. Bundling those changes into a branch makes it easier to organize and review changes to the dataset, so that eventually that branch can be merged into the upstream `master` branch.

To contribute to the Red Panda Lineage dataset, start by using *VS Code* to create a branch of your own. The new branch is created in the _working copy_ repository on your computer, from its local `master` branch.

TOWRITE: how to create and select a branch

NOTE: by convention, people try and keep local and upstream branches with the same name synchronized, but your _working copy_'s branches are totally distinct from upstream. Any changes you make must be manually synchronized to the upstream branch.

Now that your branch is made and selected, we're ready to do the important work of documenting new red pandas and zoos!

## Adding Pandas to the Dataset

Each panda is a single `.txt` file in the `/pandas` folder, with a unique Panda ID number. Each zoo is a single `.txt` file in the `/zoos` folder, with a unique Zoo ID number. **Adding to the Red Panda Lineage dataset is just a matter of copying an existing panda or zoo file, changing the contents inside of it, and submitting your new files as a branch to GitHub for review.**

Let's take a look at one of our panda files, [`pandas/0001_ichikawa/0004_lychee.txt`](https://github.com/wwoast/redpanda-lineage/blob/master/pandas/0001_ichikawa/0004_lychee.txt). This is the information we have on file for Lychee, a male red panda at Ichikawa Zoo. Fields are arranged alphabetically, and while some are obvious, let's discuss what each field means. 

### `_id`: Red Panda ID Numbers

The `_id` is a unique identification number, starting at `1` and going up. The `_id` is represented both in the file as well as in the filename of the panda. So that filenames sort cleanly, the filename ID is padded to four digits (Examples: `0004`, `1215`, `0036`). 

When adding a new red panda, take the next highest number that's not used. To see the next available Red Panda number, check the [red panda JSON data](https://wwoast.github.io/redpanda-lineage/export/redpanda.json) for the `_totals` at the top of the file. The [shields](http://shields.io/#your-badge) below also show the latest version of this `_totals` data:

[![Red Pandas](https://img.shields.io/badge/dynamic/json.svg?query=$._totals.pandas&label=red%20pandas&uri=https%3A%2F%2Fwwoast.github.io%2Fredpanda-lineage%2Fexport%2Fredpanda.json)](https://wwoast.github.io/redpanda-lineage/export/redpanda.json)
[![Zoos](https://img.shields.io/badge/dynamic/json.svg?query=$._totals.zoos&label=zoos&uri=https%3A%2F%2Fwwoast.github.io%2Fredpanda-lineage%2Fexport%2Fredpanda.json)](https://wwoast.github.io/redpanda-lineage/export/redpanda.json)


### `children`: ID Numbers for Children of a Red Panda

The `children` field is a list of this red panda's immediate family. Rather than names, which are not unique, these children values are `_id` numbers in other Red Panda files.

We don't track parent relationships, because the family tree can be fully constructed just with children and sibling relationships.

### `litter`: ID Numbers for fraternal siblings

The `litter` field is a list of panda `_id` numbers for pandas in the same immediate litter.

Red Panda families are typically based around a single mother, and her children, born during a single season. Prior to the mom having more cubs, the children generally leave to take care of themselves. We track `litter` relationships specially, because panda litters are typically closer than other brothers and sisters which may have never been colocated together. `litter` relationships also allow us to automatically fact-check details like birthdays and parents prior to merging incorrect data.

### `birthplace` and `zoo`: ID Numbers for Zoos

Pandas in our dataset have a birthplace and zoo/home recorded in their datasets. These are ID numbers as well, but for files in the `zoos/` folder. You'll notice that the subfolders of the `pandas/` directory reference both zoo names, as well as the zoo ID numbers.

### `birthday` and `death`: Dates

Dates in the Red Panda Lineage dataset are always in `YYYY`/`MM`/`DD` form. The `death` section can be omitted for pandas that are still alive, or be listed as `death: unknown` or `death: YYYY/MM/1` for a panda that passed away at an undetermined or partially-determined date.

### Unknowns are Not Published

Aside from `birthday` and `death` values, any item in a zoo or red panda entry that is marked as `none` or `unknown` is not transferred into the output JSON database. This keeps the output dataset slightly smaller.

## Preparing Your Branch for Review

You make changes to the files, save your changes, and call your work done for the day.

Before you finish, _commit_ your changes to the branch. _Commits_ work like doing a "save" for an entire set of changes in a branch, with the additional step of providing a _commit message_ that offers brief context on the purpose of the work completed.

<img src="https://raw.githubusercontent.com/wwoast/redpanda-lineage/master/docs/images/instructions/commit-to-branch-short.png" /> 

While you can make any number of commits as you do your work, we also recommend _pushing_ your branch to GitHub often. A _push_ makes a remote copy of your branch in the upstream repository. This upstream copy tells other Red Panda Dataset collaborators what changes you intend on contributing, so duplicate work can be avoided. Plus, now your data is backed up to the Internet, in case your own computer stops working.

Once you've pushed your branch up to GitHub, you can submit your changes for inclusion into the `master` branch that builds the final databse. When you're ready for us to review your changes, you visit [our repository on GitHub](https://github.com/wwoast/redpanda-lineage) and open a _Pull Request_ or _PR_. This workflow formalizes the process of you asking us to "please adopt the changes from my branch into the upstream `master` branch".

<img src="https://raw.githubusercontent.com/wwoast/redpanda-lineage/master/docs/images/instructions/pull-request.png" /> 

When you push a new branch to GitHub, the website helpfully indicates that you might want a _PR_ for that new branch you just pushed with a big *_notice_* bar and a green _Pull Request_ button. Click that bar and fill out the subsequent form, and you'll have started the _Pull Request_ process.

<img src="https://raw.githubusercontent.com/wwoast/redpanda-lineage/master/docs/images/instructions/pull-request-message.png" /> 

Be aware that we may need to ask you follow-up questions or recommend changes, so keep refreshing your PR or maybe even bookmark it in your browser.

## Automated and Manual Peer Review Processes

We use a _Continuous Integration_ tool called *Travis CI* to run automated checks against every single piece of data pushed to the Red Panda Lineage dataset. If there are problems with your commit, the software will see the problem automatically and suggest what changes are necessary. This tool runs the `build.py` program at the top-level of our repository.

Occasionally your commit will have a problem with your commits after you try and submit your PR, with a red "X" near the *Travis CI* status. If you navigate through to see the details in *Travis CI*, you'll get to a screen where the text output of `build.py` describes what went wrong. 

<img src="https://raw.githubusercontent.com/wwoast/redpanda-lineage/master/docs/images/instructions/commit-problem.png" /> 
<img src="https://raw.githubusercontent.com/wwoast/redpanda-lineage/master/docs/images/instructions/failed-ci.png" /> 

If you have a Mac or Linux system, you can run this tool yourself to validate your data prior to submitting changes upstream, or even making commits. Otherwise, just keep pushing your branches to GitHub, and *Travis CI* will happily run the `build.py` checks for you.

Once the automated checks are done, you still need one of the dataset administrators to approve and merge your changes. If we don't merge your PR quickly, there is the chance your red panda ID numbers may get used by someone else and need to be updated! Feel free to comment on your PR if you want attention. If we still fail to respond, reach out to _wumpwoast_ [via Instagram](https://instagram.com/wumpwoast).

## Troubleshooting

[![Harumaki, the Troublemaker](https://raw.githubusercontent.com/wwoast/redpanda-lineage/master/docs/images/instructions/harumaki-troubleshooter.jpg)](https://raw.githubusercontent.com/wwoast/redpanda-lineage/master/pandas/0001_ichikawa/0001_harumaki.txt)

 * If you forget to make a branch...
 * If you need to refactor from the master branch
 * Other things that people could mess up!

## Appendix: Technical / Terminal Users

If you're a command-line user, and you have Git, here's a quick sample of what a typical dataset session might look like:

```
git clone https://github.com/wwoast/redpanda-lineage.git
git checkout -b maruyama-changes
vim pandas/0001_ichikawa/0021_seita.txt
git commit -a -m "changed seita's birthday"
git push origin maruyama-changes
```
