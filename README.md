# The Seshat Writing Framework

A framework and workflow methodology designed for writers that leverages the capabilities of version control systems and combines it with the search functionality of Elastic Search and renders interactive analytics for innovative ways to examine and explore content and structure within a written corpus of work.

## Technological Approach

- Setup a vanilla git repository to track versioning of text documents.
- Assemble the individual text documents in any defined order and retain as many versions as desired.
- Automate the indexing of source documents with Elastic Search and expose capacity to query against the results.
- Visualize the results of the ES query on the corpus of work.
- Generate statistical summary data for corpus of works and individual documents.

## Workflow Description

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

However, while there are defined paradigms for how parts of something like a codebase interoperate that inherently describe the structure of the parts in relation to the whole, the written word at large has no such inherent paradigm (beyond basic syntax and grammar - which are also flexible). Instead, a best-practice must be implemented, with the single critical tenant of persistent adherence to the practice being the requirement for a succesful result.
