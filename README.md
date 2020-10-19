<h1 align="center">
    Progression at Interact
</h1>

Welcome to the Progression at Interact repository.

This is where all of Interact's progression frameworks live.

This is a fork of the epic [Monzo Progression Framework](https://github.com/monzo/progression-framework), customised for Interact.

## ❔ How does this work?

This is the structure of our repo
```
progression-framework/
    frameworks/
    src/
    CODEOWNERS
    [a bunch of config files]
```

`site` contains our website files, `frameworks` contains our progression framework files, and `CODEOWNERS` is the file that defines who owns or manages a framework, file or folder.
All the other files are configuration, which you should totally ignore 👌

**The `frameworks` folder is what you want to pay attention to!**


This is where all of our progression frameworks live. Head inside, and you'll see folders associated to headlines (like design and engineering).

Inside these folders, you'll see files representing a job (like `designer.md`). 

---

Files that end in `.md` are called Markdown files. We display these files on the site in the same way they are written, so you can put whatever you want  (within reason) in these.

All of these file contain some YAML, which a data format that is similar to a bullet point list. Some of this YAML data is compulsory, as it helps the site build 🛠️

Some files contain the compulsory YAML and the rest is Markdown, however some of these files *only* contain YAML.
The files containing only YAML are more structured, and so look a bit different to the Markdown files.

The following YAML data can be found in every file:

``` yaml
path:         ~~ a path goes here, eg "/frameworks/operations/ops-leadership" ~~
title:        ~~ the page title goes here, eg "🎯 Ops Leadership Framework" ~~
sidebarTitle: ~~ this is the title in the sidebar "🎯 Leadership" ~~
sidebarGroup: ~~ this is the subheading/group. eg "operations" or nothing ~~
yaml:         ~~ indicates if the framework is mainly yaml (true) or markdown (false) ~~
levels:       ~~ the amount of levels you want to be shown if the file is yaml, eg 6 or nothing ~~
homepage:     ~~ card-based frameworks only! whether you want a homepage to be shown, eg true, false, or nothing if irrelevant ~~
```

If the framework is in YAML format, underneath the compulsory data, you will find something like this:

``` yaml
homepage: true
topics:
  - name: "communication and teamwork"
    title: "💬 Communication and Teamwork"
    content:
      - level: 1
        criteria:
          - "Clearly articulates what they’re working on and why."
          - "Gives clear concise updates in team meeting and stand ups on material which is relevant for the team"
      - level: 2
        criteria:
          - "Proactively communicates with stakeholders and tailors communication to audience. Keeps stakeholders like COps, legal, marketing, finance updated on progress and ensures they have what they need."
          - "Gives clear concise updates in cross-team meetings on material which is relevant for the teams"
  - name: "conduct"
    title:
    content:
      - level: 1
        criteria:
          - "Follows policies and procedures applicable to role. Completes training."
          - "Accepts feedback graciously and acts on it. Gives feedback when requested"
          - "Builds relationships within monzo and contributes to building a supportive, knowledgable and engaged peer group"
        exampleCriteria:
          -  criteria: "A criteria with an example point goes here"
             examples:
               - "The example goes here"
               - "Another example may go here"
---
### 🏠 Welcome to the Backend engineering home page
```

If a topic's name matches the name of a topic in the generic framework, the generic framework criteria will be loaded as well as your framework criteria, and the title + description will be loaded from the generic framework.
If you have a custom topic, you must define a title and description.
You can see this in the example above, with both the custom "communication and teamwork" topic and the generic "conduct" topic.

For each topic, you must define its contents. This is made up of an object (starts with a bullet point) which contains the criteria, and the level it is associated with.
You can also add examples, by putting them in the `exampleCriteria` object, defining the actual criteria point, and any examples it links to.

---

## ✏️ How do I edit a framework?

Firstly, go to the framework file on this site. Click on the ✏️ icon in the top bar, and make your edits in the text editor that appears.

To save or 'commit' your changes, add an overview title and a basic description of what you've changed. You'll see that the option "Create a new branch for this commit and start a pull request" is pre-selected for you.

This will automatically save your changes and open a pull request, allowing the person who manages that framework to comment on your suggestion, decline the suggestion, or approve and merge it to make it live.

### 🤓 Looking for technical documentation?
Take a look at the readme in the `src/` directory.
