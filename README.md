# The Seshat Writing Framework

## Description

A framework and workflow methodology designed for writers that leverages the capabilities of version control systems and combines it with the search functionality of Elastic Search and renders interactive analytics for innovative ways to examine and explore content and structure within a written corpus of work.

## Conceptual Goals

When writing, inspiration can strike at any moment for any part of a creative work. You may have a single title, a turn of phrase, a short piece fo dialog, a description, a name or location - anything - and it all needs a way to be recorded, tagged and organized for later use.

Traditionally writers used pen and paper to capture ideas and thoughts, but this technique then required manual tracking, reassembly and sequencing into a coherent narrative with the more difficult task of synthesizing the structured notes into a more robust work (yet another document that also needs tracking).

This can become a monumental task for prolific writers or for writers who tend towards assembling their works from many tiny pieces of individual inspiration. But what if there were a better way to leverage every idea without having to manage an endlessly interbreeding set of documents? The ability to immediately capture any idea, no matter how small, and commit it back into the body of work becomes very powerful when combined with modern web-based mobile technology and version control systems that facilitate managing a large number of text based documents from anywhere at anytime (even providing mechanisms for controlled collaboration, reviews, feedback, and publication).

By further integrating modern web-technology like Elastic Search, which can index (inventory) and expose the content of your documents as an endlessly searchable tree of keywords, you could visualize the results across any number of conceptual boundaries. Some examples being:

  - Number of pages/lines in the complete assembled work.
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

Using statistical analysis can help identify the major characters and locations used in the work, as well as any other emergent trends in the content. Additionally, by dynamically generating a version of the work that contains only specific parts related to the search filter, the author could evaluate the work in unique ways like including only one (or a specific subset) of characters, locations, events, date ranges, etc. and check for consistency of voice or over-leveraging of certain plot elements (eg. mcguffin abuse) or locations.

## Technological Approach

- Write the source copy using basic __[markdown syntax](https://guides.github.com/features/mastering-markdown/)__.
- Setup a vanilla __[github](https://github.com/)__ repository to track versioning of text documents.
- Assemble the individual text documents in any defined order and retain as many versions as desired using __[MarkdownTools](https://github.com/taoteg/MarkdownTools)__.
- Use __[Elastic Search](https://www.elastic.co/products/elasticsearch)__ and automate the indexing of source documents with a bash script.
- Expose a capacity to query against the __[Elastic Search](https://www.elastic.co/products/elasticsearch)__ results.
- Visualize the results of the __[Elastic Search](https://www.elastic.co/products/elasticsearch)__ query on the corpus of work.
- Generate statistical summary data for corpus of works and individual documents.

## Workflow Description

While there are defined paradigms for how parts of something like a codebase interoperate that inherently describe the structure of the parts in relation to the whole, the written word at large has no such inherent paradigm (beyond basic syntax and grammar - which are also flexible).

Instead, a best-practice must be implemented, with the single critical tenant of persistent adherence to the practice being the requirement for a succesful result.

Each creative contribution to the work comes in the form of either:

  - a new document added to the repo (and a subsequent entry for the new document in one of the index files used to generate an aggregated version of the work)
  - an update to an existing document.

*NOTE: It is not expected at this point that individual versions of individual documents will be accessible for assembly into a generated version, but that could potentially be added in the future.*

This allows for the writer to generate content at as large or small a scale as fits their creative impulse in the moment of inspiration. This document can be tagged with whatever information is relevant to the contribution and placed into the index file in whatever order makes sense to the author. Once the new document is added to an index file, a new aggregate of the story can be assembled for review on demand.

This new aggregate should also be generated with a logical naming methodology such that versions of the output can be saved for reference. A good practice would be creating a unique naming or numbering convention for various kinds of aggregations (dailies, working drafts, master drafts, final copies, submissions, etc.).

*NOTE: The structuring of a project will also come to bear in this case. While any structure can be supported by the framework, I recommend a project structure similar to this:*

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
├── copy/
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
|   └── etc.
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

- Requires Python 3.
- Requires an active virtual environment.
- Requires MarkdownTools.

*Basic Command:*
```
> mdmerge -o OUTPUT.FILE.NAME.EXT INPUT.FILE.NAME.EXT
```

*Example: (run this python command from inside the drafts directory)*
```
> mdmerge -o draft.project.structure.md build.project.structure.md
```

Results in a file named ```draft.test.md``` comprised of all the source files listed in the input file ```build.test.md``` aggregated in the order they are listed.

### Best Practice

It is recommended that a logical naming convention be used for keeping content clearly identified. The workflow I am advocating here is to create a unique ```build.YYYYMMDD.md``` file for each draft you want to generate and to correspondingly name the draft generated by the build script ```draft.YYYYMMDD.md```.

This creates a 1:1 correlation between build files and the drafts they produce that can be tracked by date.

Later, we will use tags and releases to manage identifying specific drafts used in submissions, reviews and publications.

## Publishing, Reviews and Submission Tracking with Git Tags

Thankfully git has tags. You create one on any commit. Annotated tags are better than lightweight ones.

I recommend using a naming strategy for tags based on what the target role is:

- rev.REV_ENTITY_NAME *(ex. rev.Stephen.King)*
- sub.SUB_ENTITY_NAME *(ex. sub.BalantineBooks)*
- pub.PUB_ENTITY_NAME *(ex. pub.BalantineBooks)*

*Create anannotated tag:*
```
$ git tag -a TARGET -m "Published by XYZ for ABC on EFG date." COMMIT_CHECKSUM_VALUE
```

*List tags:*
```
$ git tag
TARGET
```

*See detailed tag info:*
```
$ git show TARGET
TAG_INFO...
```

*Full example:*
```
$ git tag -a sub.DelRayPublishing -m "Submitted to Del Ray Publishing." 9fceb02

$ git tag
sub.DelRayPublishing

$ git show sub.DelRayPublishing
tag sub.DelRayPublishing
Tagger: John Gentle <taoteg@gmail.com>
Date:   Mon Feb 9 15:32:16 2009 -0800

version 1.2
commit 9fceb02d0ae598e95dc970b74767f19372d61af8
Author: John Gentle <taoteg@gmail.com>
Date:   Sun Apr 27 20:43:35 2008 -0700

    updated README
...
```

Once the tag is generated for the commit, be sure and enter it into the project.structure.md files under the correct project module (reviews/reviews.md, submissions/submissions.md, publications/publications.md).

## Analytics

In practice what this means is that you need to maintain a consistent set of terms that are embedded into your documents to allow for proper tagging and structuring of your Elastic Search queries.

TBD.
