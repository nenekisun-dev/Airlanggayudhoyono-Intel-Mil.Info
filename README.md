
Skip to content
Navigation Menu
Sign in
github
/
docs
Public
Code
Issues
41
docs/content/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github
/basic-writing-and-formatting-syntax.md

amitse
3 months ago
473 lines (299 loc) · 23.6 KB

Preview

Code

Blame
title intro product redirect_from versions shortTitle
Basic writing and formatting syntax
Create sophisticated formatting for your prose and code on GitHub with simple syntax.
{% data reusables.gated-features.markdown-ui %}
/articles/basic-writing-and-formatting-syntax
/github/writing-on-github/basic-writing-and-formatting-syntax
/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax
fpt ghes ghec
*
*
*
Basic formatting syntax
Headings
To create a heading, add one to six # symbols before your heading text. The number of # you use will determine the hierarchy level and typeface size of the heading.

# A first-level heading
## A second-level heading
### A third-level heading


When you use two or more headings, GitHub automatically generates a table of contents that you can access by clicking {% octicon "list-unordered" aria-label="The unordered list icon" %} within the file header. Each heading title is listed in the table of contents and you can click a title to navigate to the selected section.



Styling text
You can indicate emphasis with bold, italic, strikethrough, subscript, or superscript text in comment fields and .md files.

Style Syntax Keyboard shortcut Example Output
Bold ** ** or __ __ Command+B (Mac) or Ctrl+B (Windows/Linux) **This is bold text** This is bold text
Italic * * or _ _      Command+I (Mac) or Ctrl+I (Windows/Linux) _This text is italicized_ This text is italicized
Strikethrough ~~ ~~ or ~ ~ None ~~This was mistaken text~~ This was mistaken text
Bold and nested italic ** ** and _ _ None **This text is _extremely_ important** This text is extremely important
All bold and italic *** *** None ***All this text is important*** All this text is important
Subscript <sub> </sub> None This is a <sub>subscript</sub> text This is a subscript text
Superscript <sup> </sup> None This is a <sup>superscript</sup> text This is a superscript text
Underline <ins> </ins> None This is an <ins>underlined</ins> text This is an underlined text
Quoting text
You can quote text with a >.

Text that is not a quote

> Text that is a quote
Quoted text is indented with a vertical line on the left and displayed using gray type.



Note

When viewing a conversation, you can automatically quote text in a comment by highlighting the text, then typing R. You can quote an entire comment by clicking {% octicon "kebab-horizontal" aria-label="The horizontal kebab icon" %}, then Quote reply. For more information about keyboard shortcuts, see AUTOTITLE.

Quoting code
You can call out code or a command within a sentence with single backticks. The text within the backticks will not be formatted. You can also press the Command+E (Mac) or Ctrl+E (Windows/Linux) keyboard shortcut to insert the backticks for a code block within a line of Markdown.

Use `git status` to list all new or modified files that haven't yet been committed.


To format code or text into its own distinct block, use triple backticks.

Some basic Git commands are:
```
git status
git add
git commit
```


For more information, see AUTOTITLE.

{% data reusables.user-settings.enabling-fixed-width-fonts %}

Supported color models
In issues, pull requests, and discussions, you can call out colors within a sentence by using backticks. A supported color model within backticks will display a visualization of the color.

The background color is `#ffffff` for light mode and `#000000` for dark mode.


Here are the currently supported color models.

Color Syntax Example Output
HEX `#RRGGBB` `#0969DA`
RGB `rgb(R,G,B)` `rgb(9, 105, 218)`
HSL `hsl(H,S,L)` `hsl(212, 92%, 45%)`
Note

A supported color model cannot have any leading or trailing spaces within the backticks.
The visualization of the color is only supported in issues, pull requests, and discussions.
Links
You can create an inline link by wrapping link text in brackets [ ], and then wrapping the URL in parentheses ( ). You can also use the keyboard shortcut Command+K to create a link. When you have text selected, you can paste a URL from your clipboard to automatically create a link from the selection.

You can also create a Markdown hyperlink by highlighting the text and using the keyboard shortcut Command+V. If you'd like to replace the text with the link, use the keyboard shortcut Command+Shift+V.

This site was built using [GitHub Pages](https://pages.github.com/).



Note

{% data variables.product.github %} automatically creates links when valid URLs are written in a comment. For more information, see AUTOTITLE.

Section links
{% data reusables.repositories.section-links %}

If you need to determine the anchor for a heading in a file you are editing, you can use the following basic rules:

Letters are converted to lower-case.
Spaces are replaced by hyphens (-). Any other whitespace or punctuation characters are removed.
Leading and trailing whitespace are removed.
Markup formatting is removed, leaving only the contents (for example, _italics_ becomes italics).
If the automatically generated anchor for a heading is identical to an earlier anchor in the same document, a unique identifier is generated by appending a hyphen and an auto-incrementing integer.
For more detailed information on the requirements of URI fragments, see RFC 3986: Uniform Resource Identifier (URI): Generic Syntax, Section 3.5.

The code block below demonstrates the basic rules used to generate anchors from headings in rendered content.

# Example headings

## Sample Section

## This'll be a _Helpful_ Section About the Greek Letter Θ!
A heading containing characters not allowed in fragments, UTF-8 characters, two consecutive spaces between the first and second words, and formatting.

## This heading is not unique in the file

TEXT 1

## This heading is not unique in the file

TEXT 2

# Links to the example headings above

Link to the sample section: [Link Text](#sample-section).

Link to the helpful section: [Link Text](#thisll-be-a-helpful-section-about-the-greek-letter-Θ).

Link to the first non-unique section: [Link Text](#this-heading-is-not-unique-in-the-file).

Link to the second non-unique section: [Link Text](#this-heading-is-not-unique-in-the-file-1).
Note

If you edit a heading, or if you change the order of headings with "identical" anchors, you will also need to update any links to those headings as the anchors will change.

Relative links
{% data reusables.repositories.relative-links %}

Custom anchors
You can use standard HTML anchor tags (<a name="unique-anchor-name"></a>) to create navigation anchor points for any location in the document. To avoid ambiguous references, use a unique naming scheme for anchor tags, such as adding a prefix to the name attribute value.

Note

Custom anchors will not be included in the document outline/Table of Contents.

You can link to a custom anchor using the value of the name attribute you gave the anchor. The syntax is exactly the same as when you link to an anchor that is automatically generated for a heading.

For example:

# Section Heading

Some body text of this section.

<a name="my-custom-anchor-point"></a>
Some text I want to provide a direct link to, but which doesn't have its own heading.

(… more content…)

[A link to that custom anchor](#my-custom-anchor-point)
Tip

Custom anchors are not considered by the automatic naming and numbering behavior of automatic heading links.

Line breaks
If you're writing in issues, pull requests, or discussions in a repository, {% data variables.product.github %} will render a line break automatically:

This example
Will span two lines
However, if you are writing in an .md file, the example above would render on one line without a line break. To create a line break in an .md file, you will need to include one of the following:

Include two spaces at the end of the first line.

This example  
Will span two lines
Include a backslash at the end of the first line.

This example\
Will span two lines
Include an HTML single line break tag at the end of the first line.

This example<br/>
Will span two lines
If you leave a blank line between two lines, both .md files and Markdown in issues, pull requests, and discussions will render the two lines separated by the blank line:

This example

Will have a blank line separating both lines
Images
You can display an image by adding ! and wrapping the alt text in [ ]. Alt text is a short text equivalent of the information in the image. Then, wrap the link for the image in parentheses ().

![Screenshot of a comment on a GitHub issue showing an image, added in the Markdown, of an Octocat smiling and raising a tentacle.](https://myoctocat.com/assets/images/base-octocat.svg)



{% data variables.product.github %} supports embedding images into your issues, pull requests{% ifversion fpt or ghec %}, discussions{% endif %}, comments and .md files. You can display an image from your repository, add a link to an online image, or upload an image. For more information, see Uploading assets.

Note

When you want to display an image that is in your repository, use relative links instead of absolute links.

Here are some examples for using relative links to display an image.

Context Relative Link
In a .md file on the same branch /assets/images/electrocat.png
In a .md file on another branch /../main/assets/images/electrocat.png
In issues, pull requests and comments of the repository ../blob/main/assets/images/electrocat.png?raw=true
In a .md file in another repository /../../../../github/docs/blob/main/assets/images/electrocat.png
In issues, pull requests and comments of another repository ../../../github/docs/blob/main/assets/images/electrocat.png?raw=true
Note

The last two relative links in the table above will work for images in a private repository only if the viewer has at least read access to the private repository that contains these images.

For more information, see Relative Links.

The Picture element
The <picture> HTML element is supported.

Lists
You can make an unordered list by preceding one or more lines of text with -, *, or +.

- George Washington
* John Adams
+ Thomas Jefferson


To order your list, precede each line with a number.

1. James Madison
2. James Monroe
3. John Quincy Adams


Nested Lists
You can create a nested list by indenting one or more list items below another item.

To create a nested list using the web editor on {% data variables.product.github %} or a text editor that uses a monospaced font, like {% data variables.product.prodname_vscode %}, you can align your list visually. Type space characters in front of your nested list item until the list marker character (- or *) lies directly below the first character of the text in the item above it.

1. First list item
   - First nested list item
     - Second nested list item
Note

In the web-based editor, you can indent or dedent one or more lines of text by first highlighting the desired lines and then using Tab or Shift+Tab respectively.





To create a nested list in the comment editor on {% data variables.product.github %}, which doesn't use a monospaced font, you can look at the list item immediately above the nested list and count the number of characters that appear before the content of the item. Then type that number of space characters in front of the nested list item.

In this example, you could add a nested list item under the list item 100. First list item by indenting the nested list item a minimum of five spaces, since there are five characters (100. ) before First list item.

100. First list item
     - First nested list item


You can create multiple levels of nested lists using the same method. For example, because the first nested list item has seven characters (␣␣␣␣␣-␣) before the nested list content First nested list item, you would need to indent the second nested list item by at least two more characters (nine spaces minimum).

100. First list item
     - First nested list item
       - Second nested list item


For more examples, see the GitHub Flavored Markdown Spec.

Task lists
{% data reusables.repositories.task-list-markdown %}

If a task list item description begins with a parenthesis, you'll need to escape it with \:

- [ ] \(Optional) Open a followup issue

For more information, see AUTOTITLE.

Mentioning people and teams
You can mention a person or team on {% data variables.product.github %} by typing @ plus their username or team name. This will trigger a notification and bring their attention to the conversation. People will also receive a notification if you edit a comment to mention their username or team name. For more information about notifications, see AUTOTITLE.

Note

A person will only be notified about a mention if the person has read access to the repository and, if the repository is owned by an organization, the person is a member of the organization.

@github/support What do you think about these updates?



When you mention a parent team, members of its child teams also receive notifications, simplifying communication with multiple groups of people. For more information, see AUTOTITLE.

Typing an @ symbol will bring up a list of people or teams on a project. The list filters as you type, so once you find the name of the person or team you are looking for, you can use the arrow keys to select it and press either tab or enter to complete the name. For teams, enter the @organization/team-name and all members of that team will get subscribed to the conversation.

The autocomplete results are restricted to repository collaborators and any other participants on the thread.

Referencing issues and pull requests
You can bring up a list of suggested issues and pull requests within the repository by typing #. Type the issue or pull request number or title to filter the list, and then press either tab or enter to complete the highlighted result.

For more information, see AUTOTITLE.

Referencing external resources
{% data reusables.repositories.autolink-references %}

Uploading assets
You can upload assets like images by dragging and dropping, selecting from a file browser, or pasting. You can upload assets to issues, pull requests, comments, and .md files in your repository.

Using emojis
You can add emoji to your writing by typing :EMOJICODE:, a colon followed by the name of the emoji.

@octocat :+1: This PR looks great - it's ready to merge! :shipit:



Typing : will bring up a list of suggested emoji. The list will filter as you type, so once you find the emoji you're looking for, press Tab or Enter to complete the highlighted result.

For a full list of available emoji and codes, see the Emoji-Cheat-Sheet.

Paragraphs
You can create a new paragraph by leaving a blank line between lines of text.

Footnotes
You can add footnotes to your content by using this bracket syntax:

Here is a simple footnote[^1].

A footnote can also have multiple lines[^2].

[^1]: My reference.
[^2]: To add line breaks within a footnote, prefix new lines with 2 spaces.
  This is a second line.
The footnote will render like this:



Note

The position of a footnote in your Markdown does not influence where the footnote will be rendered. You can write a footnote right after your reference to the footnote, and the footnote will still render at the bottom of the Markdown. Footnotes are not supported in wikis.

Alerts
Alerts are a Markdown extension based on the blockquote syntax that you can use to emphasize critical information. On {% data variables.product.github %}, they are displayed with distinctive colors and icons to indicate the significance of the content.

Use alerts only when they are crucial for user success and limit them to one or two per article to prevent overloading the reader. Additionally, you should avoid placing alerts consecutively. Alerts cannot be nested within other elements.

To add an alert, use a special blockquote line specifying the alert type, followed by the alert information in a standard blockquote. Five types of alerts are available:

> [!NOTE]
> Useful information that users should know, even when skimming content.

> [!TIP]
> Helpful advice for doing things better or more easily.

> [!IMPORTANT]
> Key information users need to know to achieve their goal.

> [!WARNING]
> Urgent info that needs immediate user attention to avoid problems.

> [!CAUTION]
> Advises about risks or negative outcomes of certain actions.
Here are the rendered alerts:



Hiding content with comments
You can tell {% data variables.product.github %} to hide content from the rendered Markdown by placing the content in an HTML comment.

<!-- This content will not appear in the rendered Markdown -->
Ignoring Markdown formatting
You can tell {% data variables.product.github %} to ignore (or escape) Markdown formatting by using \ before the Markdown character.

Let's rename \*our-new-project\* to \*our-old-project\*.



For more information on backslashes, see Daring Fireball's Markdown Syntax.

Note

The Markdown formatting will not be ignored in the title of an issue or a pull request.

Disabling Markdown rendering
{% data reusables.repositories.disabling-markdown-rendering %}

Further reading
{% data variables.product.prodname_dotcom %} Flavored Markdown Spec
AUTOTITLE
AUTOTITLE
AUTOTITLE
  
# Airlanggayudhoyono-Intel-Mil.Info
[[Int:{Airlanggayudhoyono@Intel-Mil.Info}|{{Mywebsite.com/Airlanggayudhoyono@Intel-Mil.Info}}]]
[[[["{{Intl:Airlanggayudhoyono@Intel-Mil.Info}}|
Skip to content
Navigation Menu


Airlanggayudhoyono-Intel-Mil.Info


Code
Issues
Pull requests

Open a pull request
The change you just made was written to a new branch named Airlanggayudhoyono@Intel-Mil.Info-dev-patch-1. Create a pull request below to propose these changes. Learn more about diff comparisons here.
...
 Able to merge. These branches can be automatically merged.
Add a title
Update Airlanggayudhoyono@Intel-Mil.Info

Add a description
Comment


 

Remember, contributions to this repository should follow our GitHub Community Guidelines.
️
ReviewersNo reviews
AssigneesNo one—
Labels
None yet
ProjectsNone yet
MilestoneNo milestone
Development
Use Closing keywords in the description to automatically close issues

Helpful resources
GitHub Community Guidelines
 1 commit
 1 file changed
 1 contributor
Commits on Dec 5, 2025
Update Airlanggayudhoyono@Intel-Mil.Info 

@nenekisun-dev
nenekisun-dev authored now



 Showing  with 165 additions and 1 deletion.
 166 changes: 165 additions & 1 deletion166  README.md

Original file line number	Diff line number	Diff line change
@@ -1,2 +1,166 @@
# Airlanggayudhoyono-Intel-Mil.Info
[[Int:{Airlanggayudhoyono@Intel-Mil.Info}|{{Mywebsite.com/Airlanggayudhoyono@Intel-Mil.Info}}]]
[[Int:{Airlanggayudhoyono@Intel-Mil.Info}|{{Mywebsite.com/Airlanggayudhoyono@Intel-Mil.Info}}Skip to content
Navigation Menu
bhadresh
dqp

Code
Issues
5
Pull requests
1
Actions
Projects
Wiki
Security
You’re making changes in a project you don’t have write access to. Submitting a change will write it to a new branch in your fork nenekisun-dev/dqp, so you can send a pull request.
dqp/data/pages
/
823.html
in
master

Edit

Preview
Indent mode

Spaces
Indent size

2
Line wrap mode

No wrap
Editing Airlanggayudhoyono@Intel-Mil.Info file contents

Sign up for free
Log in
 Search metadata
 Search text contents
 Search TV news captions
 Search radio transcripts
 Search archived web sites
Advanced Search
Full text of "takeout-20180930T174816Z-001"
See other formats
GOOGLE PRIVACY POLICY 


When you use our Services, you're trusting us with your 
information. We understand this is a big responsibility and 
work hard to protect your information and put you in 
control. 


This Privacy Policy is meant to help you understand what information we collect, why we collect it, and 
how you can update, manage, export, and deleteyour information. 


Effective May 25, 2018 

Archived versions 


We build a ränge of Services that help millions of people daily to explore and interact with the world in new 
ways. Our Services include: 

• Google apps, sites, and devices, like Search, YouTube, and Google Home 

• Platforms like the Chrome browser and Android operating System 

• Products that are integrated into third-party apps and sites, like ads and embedded Google Maps 

You can use our Services in a variety of ways to manage your privacy. For example, you can sign up for a 
Google Account if you want to create and manage content like emails and photos, or see more relevant 
search results. And you can use many Google Services when you’re signed out or without creating an 
account at all, like searching on Google or watching YouTube Videos. You can also choose to browsethe 
web privately using Chrome in Incognito mode. And across our Services, you can adjust your privacy 
settings to control what we collect and how your information is used. 

To help explain things as clearly as possible, we’ve added examples, explanatory Videos, and definitions 
for key terms. And if you have any questions about this Privacy Policy, you can contact us. 


INFORMATION GOOGLE COLLECTS 




We want you to understand the types of Information we 
collect as you use our Services 


We collect Information to provide better Services to all our users — from figuring out basic stuff like which 
language you speak, to more complex things like which ads you’ll find most useful, the people who matter 
most to you online, or which YouTube Videos you might like. The information Google collects, and how 
that information is used, depends on how you use our Services and how you manage your privacy 
Controls. 

When you’re not signed in to a Google Account, we störe the information we collect with unique identifiers 
tied to the browser, application, or device you're using. This helps us do things like maintain your language 
preferences across browsing sessions. 

When you're signed in, we also collect information that we störe with your Google Account, which we treat 
as personal information. 


Things you create or provide to us 

When you create a Google Account, you provide us with personal information that includes your name 
and a password. You can also chooseto add a phone number or payment information to your account. 
Even if you aren’t signed in to a Google Account, you might choose to provide us with information — like 
an email address to receive Updates about our Services. 


We also collect the content you create, upload, or receive from others when using our Services. This 
includes things like email you write and receive, photos and Videos you save, docs and spreadsheets you 
create, and comments you make on YouTube Videos. 


Information we collect as you use our Services 


Your apps, browsers & devices 


We collect information about the apps, browsers, and devices you use to access Google Services, which 
helps us provide features like automatic product Updates and dimming your screen if your battery runs 
low. 










The information we collect includes unique identifiers, browser type and settings, device type and 
settings, operating System, mo
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
55
56
57
58
59
60
61
62
63
64
[[int:{Airlanggayudhoyono@Intel-Mil.Info}<!DOCTYPE html>
Matahatiagung13@gmail.com<html lang="en">
List updated, Focused item: No license, selected, 1 of 14

KEY TERMS
Affiliates
Algorithm
Application data cache
Browser web storage
Cookies
Device
Google Account
IP address
Non-personally identifiable information
Personal information
Pixel tag
Referrer URL
Sensitive personal information
Server logs
Unique identifiers
Affiliates
An affiliate is an entity that belongs to the Google group of companies, including the following companies that provide consumer services in the EU:{{Intl:Airlanggayudhoyono@Intel-Mil.Info|Personal information:


Http://mywebsite.com/Airlanhgayudhoyono@Intel-Mil.Info Data UE-A.S., Ekstensi Inggris Raya ke UE-A.S., dan Swiss-A.S. Untuk mempelajari selengkapnya, lihat bagian Tempat kami menyimpan dan memproses data pribadi , dan kunjungi situs web Kerangka Kerja Privasi Data Departemen Perdagangan AS.
This is information that you provide to us which personally identifies you, such as your name, email address, or billing information, or other data that can be reasonably linked to such information by Google, such as information we associate with your Google Account. Skip to main content

Wayback Machine Texts Video Audio Software Images Donate More
Sign up for free
Log in
Search metadata
Search text contents
Search TV news captions
Search radio transcripts
Search archived web sites
Advanced Search
Full text of "takeout-20180930T174816Z-001"
See other formats
GOOGLE PRIVACY POLICY


When you use our Services, you're trusting us with your
information. We understand this is a big responsibility and
work hard to protect your information and put you in
control.


This Privacy Policy is meant to help you understand what information we collect, why we collect it, and
how you can update, manage, export, and deleteyour information.


Effective May 25, 2018

|Archived versions

Ikon Kesalahan
Alamat tidak dapat ditemukan
Pesan Anda tidak terkirim ke Ai13@he.net karena alamat tersebut tidak dapat ditemukan, atau tidak bisa menerima email.
Tanggapan dari server jarak jauh adalah:
550 Bad destination mailbox address - No such user at that domain


