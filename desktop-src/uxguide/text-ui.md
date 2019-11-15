User Interface Text
===================

### Introduction

Before thinking about the text you'll want to use, it's worth understanding how your audience will use it.

-   Users scan UI; they don't read it.

-   Users tend to read headers and labels first, especially those that appear relevant to their work.

-   Users tend to read descriptions/static text only when they think they need to.

-   Hint: if someone needs to read descriptive text, there's a good chance the label isn't as clear as it should be.

-   Users are more likely to read text close to where they are already reading---ensure that the important parts of text aren't far apart.

-   Assume that once users have decided what to do, they will immediately stop reading and do it.

Users don't read websites like they read a book. Instead, people's eyes are drawn to:

-   Main actions and interactable elements

-   Labels on actions

-   Titles

-   Descriptions

### Eliminate redundancy

Redundant text does a few unfortunate things:

-   It implies you aren't confident in the text you're presenting.

-   It implies that users aren't smart enough to understand your system.

-   It wastes users' time.

-   It makes text harder to scan.

-   It makes text overwhelming.

For these reasons, make sure you aren't repeating yourself. As a wise philosopher once said, "Why waste time say lot word when few word do trick."

### Avoid over-communication

Be concise. Only include absolutely necessary information in text. Reasons:

-   The eye tends to skip over it---especially unstructured text.

-   It prompts questions users weren't asking.

-   It buries important information.

If more information is necessary for some users or some scenarios, use progressive disclosure.

### Start with the outcome

Always start with the user's intended outcome when writing for UI. Users will skim for words they expect, and putting those words at the start of a sentence makes their lives better.

Take the following example:

|

Go to Partner Center > Administration > Customize > Sales to customize Sales & Success Center.

 |

The sentence starts with instructions on how to perform an action without telling users which action the instructions assist with.

Compare that to the following:

|

To customize Sales & Success Center, go to Partner Center > Administration > Customize > Sales.

 |

This is much easier for users to scan to find relevant information and complete the intended action.

Summary
-------

If you do only five things...

1.  Work on text early because text problems often reveal design problems.

2.  Design your text for scannability.

3.  Eliminate redundant text.

4.  Start user instructions with the intended outcome.

5.  Use easy-to-understand language---don't over-communicate.

Guidelines
----------

### Text fonts, sizes, and colors

### Bold, italic, and underlined text

We do not use italics, bold italics, or underlined text in our UI. You can, however, use bolded text to stress important information. We use it in the following ways:

-   Notifications: Product names, main info the user cares about, specific info.

-   Instructive text: When referring to the names of clickable elements (though it is generally best just to make the text referring to those elements actually clickable).

-   Don't bold the punctuation at the end of a bolded phrase or sentence.

### Punctuation

Periods (.)

-   Use periods at the end of complete sentences. Use one space between sentences, not two.

-   Don't place periods at the end of a phrase or incomplete sentence. 

-   Don't use periods with titles and headings, especially in dialogs or subheadings.

-   There may be exceptions for page titles and marketing material, i.e. at the end of a strong, short phrase or statement.

Question marks (?)

Place at the end of all questions. 

Exclamation points (!)

-   Avoid exclamation points.

-   Exception: Rare instances of congratulations, and never multiple in the same screen. Example: Good job!

-   Never (!!!) use exclamation points in failure messages or alerts.

-   Seriously. Don't.

Commas (,)

-   Always use an [Oxford Comma](https://www.grammarly.com/blog/what-is-the-oxford-comma-and-why-do-people-care-so-much-about-it/) when listing 3 or more items.

Colons (:)

-   Use a colon to introduce a list of items.

Ellipses (...)

Ellipses indicate incomplete information. Use ellipses in UI text as follows:

-   Actions: Indicate that an action needs additional input from the user. 

-   Don't use an ellipsis when an action opens a new modal or dialog---only when additional information is required.

-   Data: Indicate that text is truncated.

-   Labels: Indicate that a task is in progress, i.e. "Searching...".

Tip: Truncated text in a window or page with unused space indicates poor layout. Strive for layouts that eliminate or reduce the amount of truncated text.

Quotation marks and apostrophes ( " " ' )

-   Only put titles and action labels in quotation marks if required to prevent confusion and you can't format using bold instead.

-   Always use double-quotation marks (" ").

Ampersands (&)

-   Never use ampersands in sentence case

-   By default, don't use ampersands

-   Only use for proper titles (Example: Sales & Success Center)

-   Do: Save and publish

-   Don't: Save & Publish

Percentages (%)

Dashes (---)

Parentheses

### Lists

-   Use lists to present steps in a workflow, groups of objects (i.e. accounts), or sets of information. 

-   Number lists when the order is important, like when you're describing steps of a process. Don't use numbers when the list's order doesn't matter. 

-   Use point form for bullet point lists where possible

### Numbers

In body or header text (i.e. in a dialog):

-   Write numbers (other than one and two) with digits, not letters (23, not twenty-three).

-   Never start a sentence with digits.

In supplemental text (where the number is provided for comparison or evaluation):

-   Write numbers in digits.

-   Use consistent formatting between numbers on a page.

-   Example: Don't write 1,500 and 2.7k. Choose one.

-   Numbers over 3 digits get commas:

-   999

-   1,000

-   150,000

-   Write out large numbers in full. Abbreviate them only if there are space restraints, as in a chart: 1k, 150k.

-   Use numerals for big numbers up to one billion:

-   2,000,000 is better than two million.

-   Two trillion is better than 2,000,000,000,000 because most people can't interpret that many zeros.

-   As a compromise, you can often use numerals for the significant digits and write out the magnitude as a word. For example, write 24 billion (not twenty-four billion or 24,000,000,000).

-   Explain numbers starting with a trillion for most audiences. Explain numbers starting with a billion if you write for less numerate audiences or international users (you might say, for example, that "a trillion is a thousand billions.")

-   Most people don't understand numbers above a billion, and many people don't even know what a billion represents. There's also an internationalization issue here: "billion" represents a thousand millions in American English, but a million millions in many European languages.

-   Explain unusual abbreviations and measurement units, particularly those representing very big numbers.

-   Spell out numbers that don't represent specific facts.

-   A number is "a more compact (and thus attractive) representation of hard information than flowery verbiage."

### Capitalization

We only use sentence case for our UI. This means you should start the first word with a capital letter, and all following words with lower-case (with the exception of words that are always capitalized in English).

We also capitalize proper nouns and any elements that are unique to Vendasta. Example: Snapshot Report would be capitalized because it's unique. You would not capitalize users, however, because it is a common entity in the industry.

That said, many of our apps have not adopted sentence case and have not been audited yet. Consistency trumps all, so if an app primarily uses title case (capitalizing all words in a sentence), you'll want to do so as well.

### Dates and times

Even when working with dates, you should attempt to communicate with a conversational voice. We use two primary formats, depending on the context of the date.

Relative date format

The majority of the time, people don't need to know specifics. When an exact date isn't important, you'll want to go with relative formatting. Try to use the following increments:

|

2 minutes ago

 |
|

3 hours ago

 |
|

Yesterday

 |
|

6 days ago

 |
|

3 weeks ago

 |
|

7 months ago

 |

Whenever you reach the first instance where the next level can be used, move on to the next. (Example: instead of 7 days ago, write A week ago). Once you've done so, you do not need to include the previous unit of measurement.

Detailed/long date format

We use a detailed or long date format when specifics are important. This is important if you are working in a table or need to know a precise date. That said, we still want to remain business casual. Take the following example:

|

2:07 1/2/2020

 |

A few questions come to mind. Is this AM or PM? Is this referring to February 1st, or January 2nd? If this is in the future, what day of the week does this fall on?

To remove confusion, we use the following format:

|

Tuesday, Jan 2, 2020 at 2:07 PM

 |

A few notes on this:

-   Start with the day of the week.

-   Abbreviate the month to the first three letters. Do not put a period at the end.

-   We do this so it's easier to scan, and it takes up less space.

-   Keep the day of the week as just a number. This removes a lot of complexity when implementing, and it's generally easier to scan.

-   Include `at` when showing time. This makes it easy to separate the actual date and time.

-   Use a 12 hour cadence. Always show this in the user's local time.

-   Fun fact: some places only use 24-hour time, so you will need to use this in places like Europe or the Czech Republic.

-   Add AM or PM to the end in capitals. Make sure you put a space between the last digit and this text.

### Globalization and localization

Globalization means to create documents or products that are usable in any country, region, or culture. Localization means to adapt documents or products for use in a locale other than the country/region of origin. Consider globalization and localization when writing and formatting UI text. 

-   For components with variable contents (such as list views), choose a width appropriate for the longest valid data.

-   Include enough space in the UI for an additional 30 percent (up to 200 percent for shorter text) for any text that will be localized. Translation from one language to another often changes line length of text.

-   Avoid composing strings from substrings at run time---sentence structure can vary by language. Instead, use complete sentences to reduce ambiguity for the translator.

-   Don't reference a "Common" section in your translation files. Text is always context specific, and having multiple sections reference the same string (i.e.: Post) can cause issues when translating. 

-   Don't make only part of a sentence a link, because when translated, that text might not remain together. Link text should be a complete sentence or a single word or phrase (i.e. Learn more).

### Page titles

-   Use sentence case for titles except for words that are always capitalized in English or proper nouns unique to Vendasta (i.e. Snapshot Report).

-   Example: Manage accounts

-   Use adjectives sparingly in titles

-   If sidebar element exists, ensure that the title of the card/page matches the name of the element

-   All pages should have a title

### Pluralization

Do not add "(s)" to the end of a word. You should design the text so that software detects whether the word should be plural or not.

### Referencing UI elements

-   When possible, avoid referencing specific UI elements. Instead, just make that element easily usable or allow them to perform their work where they are currently looking.

-   Don't reference the element's location on the screen. Users with disabilities may not be able to utilize these instructions, and the element may not always appear in the same place.

Example: Instead of saying "Click the + above to add a comment", make the entire area clickable and say "Add a comment".

### Contractions

-   They're great! They give your writing an informal, friendly tone. In most cases, use them as you see fit.

-   Use common contractions, such as it's, you'll, you're, we're, let's, what's, that's, and don't.

-   Don't mix contractions and their spelled-out equivalents in UI text. For example, don't use can't and cannot in the same UI. 

-   Never form a contraction from a noun and a verb, such as Vendasta's developing a lot of new cloud services. 

-   Avoid ambiguous contractions, such as there'd, it'll, y'ain't, and they'll. 

### Modal titles

-   Phrase the main action that the user should intend to complete as a question.

-   Example: Delete sales order?

-   Note that if you have a modal that does not result in the user essentially answering a question, you should not present that information in a modal.

### Main instructions

Use the main instruction to explain concisely what users should do in a given window or page---communicate the user's objective rather than focusing just on manipulating the UI.

-   Express the main instruction in the form of an imperative direction or specific question.

-   Exceptions: Error messages, warning messages, and confirmations may need to use different sentence structures.

-   Use specific verbs whenever possible. Specific verbs (connect, save, install) are more meaningful to users than generic ones (configure, manage, set).

-   Don't feel obliged to use main instruction text if it would be redundant or obvious from the context of the UI.

-   Be concise---if possible, use only a single, complete sentence. If you must explain anything more, consider using progressive disclosure.

-   Use sentence-style capitalization.

Tip: You can evaluate a main instruction by imagining what you would say to a friend when explaining what to do with the window or page. If responding with the main instruction would be unnatural, unhelpful, or awkward, rework the instruction.

### Supplemental instructions

When necessary, use a supplemental instruction to present additional information helpful to understanding or using the window or page, such as qualifying information that helps users decide how to act on the main instruction. Use complete sentences and sentence-style capitalization.

Don't use a supplemental instruction if one isn't necessary. Aim to communicate everything with the main instruction if you can do so concisely. Avoid repeating the main instruction with slightly different wording.

### Labels

Labels refer to any interactive element that has a title. These can include checkboxes, radio buttons, drop-down lists, etc.

-   Label every interactive element or group of interactive elements.

-   Label placement:

-   Balloons, check boxes, command buttons, group boxes, links, tabs, and tips are labeled directly by the item.

-   Drop-down lists, list boxes, list views, progress bars, sliders, text boxes, and tree views are labeled above, flush left.

-   Keep labels brief. Note, however, that adding a word or two to a label can help clarity, and sometimes eliminates the need for supplemental explanations.

-   Prefer specific labels over generic ones. Ideally users shouldn't have to read anything else to understand the label.

-   For lists of labels, such as radio buttons, use consistent phrasing, and try to keep the length about the same for all labels.

-   For lists of labels, focus the label text on the differences among the options. If all the options have the same introductory text, move that text to the group label.\
    Don't:\
    ![screen shot of labels with duplicate first phrases](https://lh3.googleusercontent.com/Y0S4v_bIuTYFZuYcmJSywU6LwyJwoIxNaUw3W4bCZ8sJc3b3tgu6uDjTru9wD3ePvG9ICLT5DSbFy4lIXO3bJcw9ifGtdy7dkW2K88w1tphkGm95T3OYhSP4gsPLEObM2I4OAUc)\
    Do:\
    ![screen shot of first phrase moved to group label](https://lh4.googleusercontent.com/VSKnJxgBrwRxy8pAF8D_tV9mggrPSrsTTGBG8z4KEZ6ZHjZfLpNI_ociQj2ctrhLAx2AoRzbKm8BSkBvf1EJT9adUTFPH11Wnq_r6DB3b-QmnSvkEdy6FdRpyeOp5lvB1gJfjaU)\
    The correct example moves the identical introductory phrasing to the label, so the two options are more cleanly differentiated.

-   In general, aim for positive phrasing. For example, use do instead of do not, and notify instead of do not notify.

-   Exception: The check box label, "Don't show this message again," is widely used.

-   Omit instructional verbs that apply to all controls of the given type. Rather, focus labels on what is unique about the controls. For example, it goes without saying that users need to type into a text box control or that users need to click a link.\
    Incorrect:\
    ![screen shot of label: 'type your name' ](https://lh5.googleusercontent.com/MHCxfqcBCiefPUhUNpGHoIH9GagBeHVmq65035qD36z4nTxIizRBYifZA7qNN7XaTsOJJsdnwiqhXjKwpc_IwAVhqZiK7v4ngwl5lzd3SEemN1r8wQDkvbBT-nw3P_lO21hf8V8)\
    Correct:\
    ![screen shot of label: 'your name' ](https://lh6.googleusercontent.com/Ts3w6nDFCtbJeb_q-1INOPg_Qzva0wLQJP4Fd2YCUXl98i0DuM2Lg3G_0yuENVAUfbEImSaGJpGO63Fk0hc7y5ZDpy9cMm-wsyufwV13aNQ85grTKKLyFGYnqX3MWPd2hxlRlVQ)\
    In the incorrect examples, the control labels have instructional verbs that apply to all controls of their type.

-   In some cases, the following parenthetical annotations to control labels may be helpful:

-   If an option is optional, consider adding "(optional)" to the label.

-   If an option is strongly recommended, add "(recommended)" to the label. Doing so means the setting is optional, but should be set anyway.

-   You may specify units (seconds, connections, and so on) in parenthesis after the label.

### Supplemental label descriptions

-   Use supplemental text under labels when interactive elements require more information than can be concisely conveyed by their label. 

-   Don't use a supplemental explanation if one isn't necessary---aim to communicate everything with the label (if you can do so concisely). 

-   Supplemental explanations are often used with command links, radio buttons, and check boxes.

-   Adding a supplemental description to one label in a group doesn't mean that you have to provide explanations for all the other labels in the group (i.e. the Admin > Settings page in PC).

-   Use complete sentences and ending punctuation.

### Text with icons

When using an icon, try to always pair it with text. A few reasons to pair with text:

-   With rare exception (such as the play and pause buttons on a media player), icons can have many different contexts in different parts of the world.

-   Icons are used inconsistently across the web, so what means something in your app likely means something different elsewhere.

-   It helps users more clearly understand what an icon or button does.

If you are constrained by space, you may want to re-evaluate your design. While you don't want to clutter your UI, you do want it to be understood by the majority of people.

Style - Voice and Tone
----------------------

Overall, aim to create content that can be described as follows. 

-   Clear: Use simple words and sentences, and communicate necessary information.

-   Useful: Before you start writing, ask yourself: What purpose does this serve? Who is going to read it? What do they need to know?

-   Friendly. Write like a human. Don't be afraid to break a few rules if it makes your writing more relatable. All of our content, from success messages to system alerts, should be warm and human.

-   Appropriate. Write in a way that suits the situation. Just like you do in face-to-face conversations, adapt your tone depending on who you're writing to.

There are a few tricky scenarios and special grammar cases with certain terms. Please use the following:

-   Snapshot Report, not Snapshot

-   VendastaCon, not Vendastacon or VCon

-   Sales & Success Center, not Sales and Success Center

-   Master Key, not Masterkey or MasterKey

Avoid using abbreviations in outward-facing materials (e.g., VBC, RM, SM, etc.).

Other internal terms, such as PID and AGID, should not be used externally, either in writing or when speaking to partners.

<https://abissonnette-va.github.io/content-style-guide/03-voice-and-tone/>

Style - individual elements
---------------------------

### Buttons

Buttons should always contain actions. Write button labels in sentence case. The language should be clear and concise. Standard website buttons include:

-   Log in

-   Sign up 

-   Subscribe

-   Email us

### Checkboxes

Use sentence case for checkboxes.

### Drop-down menus

Use title case for menu names and sentence case for menu items.

Style - commonly fucked-up words list
-------------------------------------

<https://abissonnette-va.github.io/content-style-guide/16-word-list/>

[Stop naming things different things FFS](https://docs.google.com/spreadsheets/d/1mj1iDyKZtlqivrcHc5hheW2ZvVhWSeMIZ2NQW_-DbbQ/edit#gid=0)

HELP CONTENT
------------

[Help content](https://docs.microsoft.com/en-us/windows/win32/uxguide/winenv-help)

### NEXT STEPS

-   Standards on WHEN to include the discussed elements

-   Examples for each section. Do vs. Don't.

-   Standards on workflows, user inputs, etc.

-   Specifics on individual elements

-   Visual hierarchy for text (how to draw the eye)

-   Greater granularity for voice and tone depending on user persona/archetype and/or where in the platform we're working

-   Expand the punctuation section

Specific Messages
-----------------

Confirmation messages

<https://uxdesign.cc/are-you-sure-you-want-to-do-this-microcopy-for-confirmation-dialogues-1d94a0f73ac6>

Cancellation messages

<https://uxdesign.cc/the-microcopyist-cancellation-confirmation-conflagration-8a6047a4cf9>