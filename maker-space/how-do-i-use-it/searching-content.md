---
description: >-
  Searching for specific content within the Makerspace and learning the advanced
  search syntax
---

# Searching Content

The ability to search your content is vital to day-to-day use. There are a few locations within the Makerspace where you can search for your content. Below is a list of search functions within the Makerspace:

* **Header Search Bar** - The search bar/link in the header of every page allows you to search from anywhere. This search is a global search which will look across all books, chapters and pages in your system. After performing a search in this box you'll be led to a search page that includes options and features that can help you build a more advanced search.
* **Book/Chapter Search Bar** - When viewing a book or chapter a search bar can be found in the top of the left sidebar. These searches will look across all child items.
* **Move & Link Selection** - When choosing to move a page/chapter or when selecting a page/chapter/book to link to within the editor the most popular items are shown but you also have the ability to search.

### Advanced Search Syntax

All of the above search locations within the Makerspace share the ability to use advanced search syntax. An easy way to see this syntax in action is to use the global search in the Makerspace then play with the search filters which will update the search term with the below syntax. Below are details of the different types of syntax that can be used:

| Search Type | Syntax | Examples | Description |
| :--- | :--- | :--- | :--- |
| Normal Searches | &lt;term\_a&gt; &lt;term\_b&gt; | london meeting | Normal word searches across the name and description or body of your content. When multiple terms are searched only one term has to match your content but content containing both terms will be higher in the results. |
| Exact Searches | "&lt;term&gt;" | "london meeting" | Exact matches will require that the whole string within quotes exists in your content in exactly the same format. Use this if you're looking for an exact phrase containing or if you need to search for a term with spaces in. |
| Tag Searches |  \[&lt;name&gt;\]  \[&lt;operator&gt;&lt;value&gt;\]  \[&lt;name&gt;&lt;operator&gt;&lt;value&gt;\] |  \[location\]  \[=london\]  \[location=london\]  \[attendees&gt;5\] | Tag searches allow you to find pages which have specific tags applied. You can search by tag name, by tag value or by both name and value. When searching by tag value an operator must be used to define the match type. You can use `=`, `!=`, `<`, `>`,`<=`, `>=` or `like` as operators. When using the `like` operator you can use `%` symbols to represent wildcards in your search. |
| Filter Searches |  {&lt;filter\_name&gt;}  {&lt;filter\_name&gt;:&lt;filter\_value&gt;} | See below | Filters perform additional advanced functionality to make your searches even more powerful. Some filters take values but some don't need to. See below for a full list of filters available. |

### Available Filters

Filters are set advanced search features that can be used in your search term. The below table shows all the filters available in the Makerspace and how they can be used.

| Syntax | Examples | Description |
| :--- | :--- | :--- |
| Date Filters |  |  |
| {updated\_after:&lt;date&gt;} | {updated\_after:2016-12-30} | Adds the condition that the content must have been last updated after the given date.  The date should be in the format YYYY-MM-DD |
| {updated\_before:&lt;date&gt;} | {updated\_before:2016-12-30} | Adds the condition that the content must have been last updated before the given date.  The date should be in the format YYYY-MM-DD |
| {created\_after:&lt;date&gt;} | {created\_after:2016-12-30} | Adds the condition that the content must have been created after the given date.  The date should be in the format YYYY-MM-DD |
| {created\_before:&lt;date&gt;} | {created\_before:2016-12-30} | Adds the condition that the content must have been created before the given date.  The date should be in the format YYYY-MM-DD |
| User Filters |  |  |
| {updated\_by:&lt;user\_id\|me&gt;} |  {updated\_by:10}  {updated\_by:me}  | Adds the condition that the content must have been last updated by the user of the given numeric ID. If 'me' is used in place of a numeric ID then it will find content that was last updated by the current logged-in user. |
| {created\_by:&lt;user\_id\|me&gt;} |  {created\_by:10}  {created\_by:me}  | Adds the condition that the content must have been created by the user of the given numeric ID. If 'me' is used in place of a numeric ID then it will find content that was created by the current logged-in user. |
| Content Filters |  |  |
| {in\_name:&lt;search&gt;} |  {in\_name:London Meetings}  {in\_name:Meetings} | Will require the content to have the given `<search>` term in the name rather than the name **or** content body. |
| {in\_body:&lt;search&gt;} |  {in\_body:London Meetings}  {in\_body:Meetings} | Will require the content to have the given `<search>` term in the body rather than both the name **or** content body. |
| Option Filters |  |  |
| {is\_restricted} |  {is\_restricted} | Will require the content to have content-level permissions active. Does not return items with only inherited asset permissions. |
| {viewed\_by\_me} |  {viewed\_by\_me} | Will require the content to have been viewed by the current user at least once. |
| {not\_viewed\_by\_me} |  {not\_viewed\_by\_me} | Will not return any content that has been viewed by the current user. |
| {type:&lt;content\_types&gt;} |  {type:page\|chapter\|book}  {type:page\|chapter}  {type:book}  | Restricts the types of content that will be in the search results.  Use of this will depend on the type of search. For example, in a chapter search only pages are shown so this has no effect. |

### Search Examples

Below are some examples of using the above syntax and filters with descriptions:

* `"my cat" {viewed_by_me} {updated_after:2017-01-24}`
  * `"my cat"` - Search for content containing the exact phrase 'my cat'
  * `{viewed_by_me}` - that has been viewed by me
  * `{updated_after:2017-01-24}` - and was last updated after the 24th of Jan 2017.
* `textbook discussion [meeting] {type:page} {created_by:me}`
  * `textbook discussion` - Search content for the words `textbook` or `discussion`
  * `[meeting]` - only show content that has a `meeting` tag applied
  * `{type:page}` - only show pages, hide chapters and books
  * `{created_by:me}` - that was created by me.
* `{type:book|chapter} {created_by:me} {created_after:2016-08-12} {created_before:2017-02-18}`
  * `{type:book|chapter}` - Search all books and chapters
  * `{created_by:me}` - that were created by me
  * `{created_after:2016-08-12}` - after the 12th of Aug 2016
  * `{created_before:2017-02-18}` - but before the 18th of Feb 2017

