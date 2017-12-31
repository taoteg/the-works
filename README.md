# The Seshat Writing Framework

## Description

A framework and workflow methodology designed for writers that leverages the capabilities of version control systems and combines it with the search functionality of Elastic Search and renders interactive analytics for innovative ways to examine and explore content and structure within a written corpus of work.

## Conceptual Goals

When writing, inspiration can strike at any moment for any part of a creative work. You may have a single title, a turn of phrase, a short piece fo dialog, a description, a name or location - *anything* - and it all needs a way to be recorded, tagged and organized for later use immediately and with ease.

Traditionally writers used pen and paper to capture ideas and thoughts, but this technique required always having materials on hand, manual tracking, reassembly and sequencing of the notes into a coherent narrative followed by the still more difficult task of synthesizing the structured notes into a cogent work (yet another document that also needs tracking). This can become a monumental task for prolific writers or for writers who tend towards assembling their works from many tiny pieces of individual inspiration.

__But what if there were a better way to leverage every idea without having to manage an endlessly interbreeding set of documents?__

The ability to immediately capture any idea, no matter how small, and commit it back into the body of work becomes very powerful when combined with modern web and mobile technology and a version control system that facilitate managing a large number of text based documents from anywhere at anytime (even providing mechanisms for controlled collaboration, review, feedback, and publication).

What if these piece parts could then be aggregated into a single manuscript with a simple command, in as many variations as the author desires?

By dynamically generating a version of the work that contains only specific parts (using a build file), the author could evaluate the work in unique ways like including only one (or a specific subset) of characters, locations, events, date ranges, etc. and check for consistency of voice or over-leveraging of certain plot elements (eg. mcguffin abuse) or locations.

By further integrating modern web-technology like Elastic Search, which can index (inventory) and expose the content of your documents as an endlessly searchable tree of keywords, you could visualize the results across any number of conceptual boundaries.

Some examples:

  - Number of pages/lines in the entire assembled work.
  - Number of pages/lines in the individual parts of the work.
  - Number of pages/lines of the story that contain a specific:
    - Character
    - Location
    - Event
    - Time or Date
  - Statistical summary data:
    - Number of pages, lines, words, characters in work.
    - Number of characters, locations, date range, significant events, etc. in work.
    - Number of iterations per part of the work.

Using statistical analysis can help identify the major characters and locations used in the work, as well as any other emergent trends in the content. The content of the manuscript could be visualized based on specific search terms or keywords, locations (in the story on in the manuscript text), events, dates, characters, etc. and the relationships between those elements could also be visualized using timelines, tree graphs, histograms, etc. These new technical insights into the creatve process can give authors immediate feedback on their tendencies, workflow and progress.

Eventually the manuscript generation and the Elastic Search capability could be combined so that a new manuscript could be generated from the results of any search query or filters being applied.

## Technological Approach

__Requirements:__

- Requires Python 3.
- Recommends an active virtual environment.
- Requires MarkdownTools.
- Recommends Atom.io with Markdown Preview Plus rendering plugin.

__Workflow:__

- Write the source copy using basic __[markdown syntax](https://guides.github.com/features/mastering-markdown/)__. [ *status* :: __complete__ ]
- Setup a vanilla __[github](https://github.com/)__ repository to track versioning of text documents. [ *status* :: __complete__ ]
- Assemble the individual text documents in any defined order and retain as many versions as desired using __[MarkdownTools](https://github.com/taoteg/MarkdownTools)__. [ *status* :: __complete__ ]
- Render output manuscript drafts for distribution (review, submission, publication) using __[Markdown Preview Plus](https://github.com/taoteg/markdown-preview-enhanced)__. [ *status* :: __complete__ ]
  - Note: Eventually I will migrate this to a more mature LaTex based workflow.
- Use __[Elastic Search](https://www.elastic.co/products/elasticsearch)__ and automate the indexing of source documents with a bash script. [ __status__ :: *pending* ]
- Expose a capacity to query against the __[Elastic Search](https://www.elastic.co/products/elasticsearch)__ results. [ __status__ :: *pending* ]
- Visualize the results of the __[Elastic Search](https://www.elastic.co/products/elasticsearch)__ query on the corpus of work. [ __status__ :: *pending* ]
- Generate statistical summary data for corpus of works and individual documents. [ __status__ :: *pending* ]

## Installing Requirements

TBD.

## Forking the Repository

You've cloned this repo from github, but now you want to fork it and (maybe) contribute back.
When you fork, "origin" should be your fork and "upstream" should be the project you forked from.
To follow convention:

1. Clone the repo on Github:
  ```$ git clone git@git.repo.git```
2. In your local clone, rename the origin remote to upstream:
  ```$ git remote rename origin upstream```
3. Create a new repo on github to commit your work into via the web interface.
4. Add the new repo origin to the local clone of the repo:
  - ```$ git remote add origin git@github.com:USERNAME/my-fork-repo.git```
  - ```$ git remote add origin https://github.com/USERNAME/my-fork-repo.git```
5. Git fetch ```$ git fetch origin```
6. Git push ```$ git push -u origin master```
7. Use as normal (git fetch/pull/branch/add/commit/push/etc.)

## Workflow Description

While there are defined paradigms for how parts of something like a codebase interoperate that inherently describe the structure of the parts in relation to the whole, the written word at large has no such inherent paradigm (beyond basic syntax and grammar - which are also flexible).

Instead, a best-practice must be implemented, with the single critical tenant of persistent adherence to the practice being the requirement for a succesful result.

Each creative contribution to the work comes in the form of either:

  - a new document added to the repo (and a subsequent entry for the new document in one of the index files used to generate an aggregated version of the work)
  - an update to an existing document.

*NOTE: It is not expected at this point that individual versions of individual documents will be accessible for assembly into a generated version, but that could potentially be added in the future. Technically this capability already exists as part of git, users can access and leverage that functionality at anytime but do so at their own risk.*

This allows for the writer to generate content at as large or small a scale as fits their creative impulse in the moment of inspiration. This document can be tagged with whatever information is relevant to the contribution and placed into the index file in whatever order makes sense to the author. Once the new document is added to an index file, a new aggregate of the story can be assembled for review on demand.

This new aggregate should also be generated with a logical naming methodology such that versions of the output can be saved for reference. A good practice would be creating a unique naming or numbering convention for various kinds of aggregations (dailies, working drafts, master drafts, final copies, submissions, etc.).

## Project Structure

The structuring of a project will also come to bear in this case. While any structure can be supported by the framework (with some adaptation), I recommend a project structure similar to this:

```
.
├── authors_notes/
|   ├── characters/
|   |   ├── hero.protagonist.md
|   |   └── villain.antagonist.md
|   ├── locations/
|   |   └── homebase.md
|   ├── events/
|   |   └── genesis.md
|   ├── dates_times/
|   |   └── important.periods.md
|   ├── items/
|   |   └── the.mcguffin.md
|   ├── other/
|   |   └── philosophy.narrative.md
|   └── authors.notes.md
├── drafts/
|   ├── general/
|   |   ├── author.md
|   |   ├── collaborators.md
|   |   ├── copyright.md
|   |   ├── dedication.md
|   |   ├── legal.boilerplate.md
|   |   ├── preface.md
|   |   └── title.md
|   ├── chapter_01/
|   |   └── ch.01.md
|   └── ... (more copy files)
├── manuscripts/
|   ├── build.authors.notes.md
|   ├── build.project.structure.md
|   ├── build.working.md
|   ├── ... (more build files)
|   ├── draft.authors.notes.md
|   ├── draft.project.structure.md
|   ├── draft.working.md
|   ├── ... (more draft files)
|   └── manuscripts.md
├── publications/
|   └── publications.md (list of annotated tags)
├── resources/
|   ├── 5.keys.md
|   ├── 5.step.manuscript.md
|   └── submission.formats.md
├── reviews/
|   └── reviews.md (list of annotated tags)
├── submissions/
|   └── submissions.md (list of annotated tags)
└── README.md
```

## Aggregating Markdown Files: Building Drafts

### Best Practice

It is recommended that a logical naming convention be used for keeping content clearly identified. The workflow I am advocating here is to create a unique ```build.IDENTIFIER.md``` file for each draft you want to generate and to correspondingly name the draft generated by the build script ```draft.IDENTIFIER.md```.

The __IDENTIFIER__ can be anything, but some good suggestions are:

- ```Role``` (A prefix to track the build and draft correlations)
- ```Codename``` (A private reference to the manuscript)
- ```Title``` (The working title of the manuscript)
- ```Status``` (The current state of the draft from an ordinal list of states [Incomplete, Working, Complete])
- ```YYYYMMDD``` (Date in Year Month Day values - best to use with all options)
- Ideally a combination of the previous:
  - ```build.codename.YYYYMMDD```
  - ```build.title.YYYYMMDD```
  - ```build.incomplete.YYYYMMDD```
  - ```build.codename.working.YYYYMMDD```
  - ```build.title.complete.YYYYMMDD```

Using ```build``` for the build file prefix (command input) and ```draft``` for the manuscript file prefix (command output) creates a 1:1 correlation between build files and the drafts they produce that can be easilly linked to tags.

Later, we will use tags and releases to manage identifying specific drafts used in submissions, reviews, publications and archiving.

Additionally I recommend using all lowercase letters whenever possible in naming ```build``` and ```draft``` files.

*Basic Command:*

```
$ mdmerge -o OUTPUT.FILE.NAME.EXT INPUT.FILE.NAME.EXT
```

*Example: (run this python command from the root of the project)*

```
$ mdmerge -o manuscripts/draft.project.structure.md manuscripts/build.project.structure.md
```

This command generates a file named ```draft.project.structure.md``` comprised of all the source files listed in the input file ```build.project.structure.md``` and aggregated in the order they are listed.

## Publishing, Reviews and Submission Tracking

I recommend using a naming strategy for manuscripts based on a combination of what the manuscript role is, the target entity and the date.

I advocate here for using:

- prefixes to better identify the manuscript role in the name (ex. ```rev``` for revision, ```sub``` for submission, ```pub``` for publication)
- an ```IDENTIFIER``` specific to the manuscript draft target entity the manuscript is generated for (ex. ```REV_ENTITY_NAME```)
- the date (in ```YYYYMMDD``` format)

All together it looks something like this:

- ```rev.REV_ENTITY_NAME.YYYYMMDD``` *(ex. ```rev.SlenGypsum.20171123```)*
- ```sub.SUB_ENTITY_NAME.YYYYMMDD``` *(ex. ```sub.BalantineBooks.20171125```)*
- ```pub.PUB_ENTITY_NAME.YYYYMMDD``` *(ex. ```pub.BalantineBooks.20171124```)*

NOTE: Syntax is a very personal thing to me. You can use periods, underscores or hyphens if it suits your style better when naming things. Just stick to a combination of these three characters and you will be fine. I personally prefer the following:
  - underscores in folder names and placeholder variable names (ex. ```PUB_ENTITY_NAME```)
  - periods in file names (ex. ```pub.Magazine.20171124```)
  - camelCase syntax when combining terms (ex. ```rev.SlenGypsum.20171123```)
  - all lowercase letters in naming ```build``` and ```draft``` files

TBD.

## Elastic Search Indexing, Analytics & Visualization

__*(still under development)*__

In practice what this means is that you need to maintain a consistent set of terms that are embedded into your documents to allow for proper tagging and structuring of your Elastic Search queries.

## References

- [Git Repo](https://github.com/taoteg/seshat-writing-framework)
- [Mastering Markdown](https://guides.github.com/features/mastering-markdown/)
- [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
- [Markdown Tools](https://github.com/taoteg/MarkdownTools)
- [Working With Multi-File Markdown Documents](https://www.develves.net/blogs/jnspd-closed/2014-03-16-working-with-multi-file-markdown-documents/)
- [Markdown Preview Enhanced/Plus](https://github.com/taoteg/markdown-preview-enhanced)
- [Markdown 2 PDF](https://atom.io/packages/markdown-pdf)
- [Markdown PDF for NPM](https://github.com/alanshaw/markdown-pdf)
- [Typsesetting AUtomation with LaTex](http://mrzool.cc/writing/typesetting-automation/)
- [Git Tagging Basics](https://git-scm.com/book/en/v2/Git-Basics-Tagging)
- [Git Tag](https://git-scm.com/docs/git-tag)
- [Elastic Search](https://www.elastic.co/products/elasticsearch)
- [Seshat Wikipedia](https://en.wikipedia.org/wiki/Seshat)


### TODO:

- Break README.md into subdocuments and create build file.
