# Adorn Standard

This document is the full specification for the Adorn Standard. 

For a quick reference, see the Adorn Quick Reference Document.

Adorn is a standard for making modular TTRPGs (Table Top Role Playing Games) using the markdown format.  Homebrewing a game can be immensely fun, so Adorn hopes to lower the threshold for free remixing of TTRPG content while making sure that all authors are well acknowledged.

It is designed to be just about as easy to use as writing the text of a game without it.
Your full usable game lives in one markdown document which you can as easily modify as you could with any other markdown document.
Adorn is essentially just a standard way to call out which blocks of text currently in your game could be replaced with other blocks of text.
We call these places where text can be swapped "Slots" and we call the different possible versions of the text in a slot "Modules."

You denote that a part of your document is actually a slot by adding a simple slot comment to your game in the Adorn format.
This comment generally gives the name of the slot and where the current module in the slot came from.

In addition to prescribing some simple formatting rules, Adorn suggests that you host your text on GitHub.  It is free to make a repository on GitHub and if you make your repository public, GitHub will host the rendered text of your game for others to see.  This rendering is even done by default when you use the markdown format. On top of this, GitHub automatically tracks changes in your documents so that you can make radical changes to your work without invalidating other works that reference yours. see the [Hosting on GitHub](#6-hosting-on-github) section of this document for more details.

The goal of Adorn is to support and encourage sharing of modules as much as possible so it also includes standard practices for attribution.
This includes standards for:
- Giving credit to the author of a source at the point where you use it in your document.
- Including the relevant license text for the sources you use.
- Including a license in your own work so that others can use it.

## 1: Documents with Slots

In Adorn, a slot denotes a place in a document where one chunk of text may be easily swapped out for another.
The specific text contained in a slot is referred to as a module.
Slots often contain text that is copied from or modified from some other work.
Often the copied/modified text is also a module in the source document. (in other words, it lives in a slot in the source document)
Slots can also contain modules original to the current document that you want to be easily referenced by other documents.
(see Making a Slot for more details)

## 2: Document Types

Adorn concerns itself with two different kinds of documents.

## 2.1: Game Files

Game files are the markdown file in which you write the text of your game.  This file should appear almost the same as any other markdown file with the addition of a few Adorn specific annotations and attributions.  See style_guide.md and sample_game.md for more details. 

## 2.2: Module Files

Module files are also markdown files.  Module files contain a list of related (generally interchangeable) modules, each in their own slot.  Similar to game files, module files are essentially just normal markdown files with a few Adorn specific annotations and attributions.  Module files contain all the same pieces as a game file as specified in this document(e.g. a [Credits](#51-credits) section and a [Licenses](#52-licenses) section) but instead of containing a game, they just contain a serries of slots each containing a module. See style_guide.md and sample_modules.md for more details. 

## 3: Making a Slot

Each slot should fall under its own heading in your game text. (For including smaller pieces of text from other works see the [Non-Modular Borrowed Text](#4-non-modular-borrowed-text) section)
The module in a slot can be made up of any kind of text. For example it can include tables, its own sub headings, or even other slot comments.
You can denote any heading as a slot by adding an opening slot comment directly below the heading.  Also add a closing slot comment at the end of the slot.
Each slot should have a name that is unique when compared to other slots in the same document. (slot names do not have to be the same as the the name of the heading they fall under)
The slot's heading should always be followed by a link to the credits section at the end of the game file (see the [Attribution](#5-attribution) section for more details)

## 3.1: Slot Comments

See sample_game.md and sample_modules.md for examples of slot comments in use.

There are a few different ways to annotate a slot using slot comments.  These are based on where you got the module (a.k.a the text currently in the slot) from and if you modified it.

In all slot comments you may leave any field that you can not find the data for empty.

Never reference a source that simply copied the text you want to use verbatim from a third source. Instead, reference the source that first produced the text in the form that you want to copy/modify. You can check the slot comment or the credits section of an Adorn compliant source to see whether they modified or copied the text you want to use. The original author and all modifying authors will be linked to in the [credits section](#51-credits), but not directly in the slot comment.

Always follow a slot comment with an embedded link to the Credits section of your document using the following format:

    [(name of author)](#title-of-source-work)

Use the name of the work as the hyperlink text in the odd case that there is no author name.
(See the [Attribution](#5-attribution) section for more details)

## 3.1.1: Slots Containing Text from Other Slots

Use this format if your source is a module from a slot in another document or a subsection of a module from a slot in another document.  Make sure the the source you are copying from is either the original source of the text, or has modified the text from the original source (see the slot comments below for how to tell the difference).  If the source text you found is copied and not modified, use the Credits section of the source document to find the source it cites used and cite that source instead. (See [Credits](#51-credits) for more details)

If the text in your slot is a copy of the entire text from a slot in a source document use the following pair of comments. Still use these comments if you have changed the formatting, but left the text the same. 

Opening slot comment to be placed under the heading that defines your slot:

    <!---Slot_Name: "name of this slot", Copied_From, Source_Slot: "name of source slot", Link: "URL of source"-->

Closing slot comment to be placed after your slot:

    <!---/Slot_Name: "name of this slot"-->
    
If the text in your slot is **modified** from text in a slot in a source document use the following pair of opening and closing comments instead of the above. Any non-formatting textual changes count as modifications. Including only a subsection of the source slot also counts as a modification.

Opening slot comment to be placed under the heading that defines your slot:

    <!---Slot_Name: "name of this slot", Modified_From, Source_Slot: "name of source slot", Link: "URL of source"-->

Closing slot comment to be placed after your slot:

    <!---/Slot_Name: "name of this slot"-->

## 3.1.2: Slots Containing Purely Original Text

A slot that does not derive its text from another source can also be defined.  This can be useful if you are making a module file or if you want the content from a game file to be easily referenced by other game file.  In this case the following comments are used.

Opening slot comment to be placed under the heading that defines your slot:

    <!---Slot_Name: "name_of_this_slot", Original-->

Closing slot comment to be placed after your slot:

    <!---/Slot_Name: "name_of_this_slot"-->

## 3.1.3: Slots Containing Text from non-Slot Sources

This format is used if you want to use text from a source that does not use Adorn.  It also lets you include text from documents that do use Adorn when the the text you want to use is not annotated as a slot in the source document.  Use the following pair of comments if the slot contains a direct copy of the source text. 

Opening slot comment to be placed under the heading that defines your slot:

    <!---Slot_Name: "name of this slot", Copied_From, Source_Document: "Name of source document", Link: "URL of source if applicable"-->

Closing slot comment to be placed after your slot:

    <!---/Slot_Name: "name of this slot"-->

Alternatively, Use the following format if the text in your slot is modified from the text in the source document.

Opening slot comment to be placed under the heading that defines your slot:

    <!---Slot_Name: "name of this slot", Modified_From, Source_Document: "Name of source document", Link: "URL of source if applicable"-->

Closing slot comment to be placed after your slot:

    <!---/Slot_Name: "name of this slot"-->

## 4: Non-Modular Borrowed Text

Sometimes you only use a few lines of text from another source and it does not make sense to turn that text into a slot with its own heading.  Adorn still supports this with a slightly different format than with slots.  

Just like with slots, never reference a source that simply copied the text you want to use verbatim from a third source. Instead, reference the source that first produced the text in the form that you want to copy/modify. You can check the comment or the credits section of an Adorn compliant source to see whether they modified or copied the text you want to use. The original author and all modifying authors will be linked to in the [credits section](#51-credits), but not directly in the comment.

Place this comment at the end the paragraph that contains strictly copied text from the source.

    <!---Copied_From, Source_Document: "Name of source document", Link: "URL of source if applicable"-->

If you modified the source text or intermingled it with your own text use this comment at the end of the paragraph that contains the text:

    <!---Modified_From, Source_Document: "Name of source document", Link: "URL of source if applicable"-->

Follow this comment with an embedded link to the credits section of your document of the following format:

    [(name of author)](#title-of-source-work)

Use the name of the work as the hyperlink text in the odd case that there is no author name.
(see the [Attribution](#5-attribution) section for more details)

## 5: Attribution

All document that use Adorn need to have a Credits and a Licenses section.

## 5.1: Credits

All text included from other sources needs to be represented in the Credits section of your game file or module file.

When crediting a work, if a required piece of information can not be found, the field may be left blank if leaving it blank does not violate the terms of the license that covers that work.

Note that you only need to include a link to the License section in a credit when the credited work's license requires you to include some text in your document.

## 5.1.1: Crediting a Document That Uses Adorn

A credit to an Adorn compliant document source document looks like:

Raw markdown text:

    <a name="title-of-source-work">Title of Source Work\</a>
    - Title: **Title of Source Work**, By: **Author Name**. [Link to Source](URL_of_Source) | [License Name](#license-name)

Rendered markdown text:

><a name="title-of-source-work">Title of Source Work</a>
>- Title: **Title of Source Work**, By: **Author Name**. [Link to Source](URL_of_Source) | [License Name](#license-name)

Note that the link to the license should be a link to the the text of license section of your document.  The license section contains any text that the original license requires you to include. (See [Licenses](#52-licenses) for more details)

Also note that credits are prefaced by anchors so that they can be linked to at the point of use in your document. See the [Slot Comments](#31-slot-comments) and [Non-Modular Borrowed Text](#4-non-modular-borrowed-text) sections for more details on formatting these links at the point of use.

If the text you include is a modified version of some text from a third source, you need to credit that original source as well. In fact, you need to cite all modifying works between your work and the original text.  Do this even when the origial text does not use Adorn.  Luckily, Adorn makes this easy in that you can often just copy the citation in the work you directly cite and modify it slightly.  To keep citations as streamlined as possible, please make sure the slot you directly cite is a modified slot and is not simply a copy. If it is a copy, cite the source of the copy instead (If they follow the Adorn format well, the source should be easy to find in the document's Credits section!)

Raw markdown text:

    <a name="title-work-you-directly-quoted">Title of Work You Directly Quoted</a>
    - Title: **Title of Work You Directly Quoted**, Modified By: **Author of Work You Directly Quoted**, [Link to Source](URL_of_Source) | [License Name](#license-name)
        - Title: **Title of Second Modifying Work**, Modified By: **Author of Second Modifying Work**, [Link to Source](URL_of_Source) | [License Name](#license-name)
        - Title: **Title of First Modifying Work**, Modified By: **Author of First Modifying Work**, [Link to Source](URL_of_Source) | [License Name](#license-name)
    - Title: **Title of Original Work**, By: **Author of Original Work**, Link: URL of document. [Link to Source](URL_of_Source) | [License Name](#license-name)

Rendered markdown text:

><a name="title-work-you-directly-quoted">Title of Work You Directly Quoted</a>
>- Title: **Title of Work You Directly Quoted**, Modified By: **Author of Work You Directly Quoted**, [Link to Source](URL_of_Source) | [License Name](#license-name)
>    - Title: **Title of Second Modifying Work**, Modified By: **Author of Second Modifying Work**, [Link to Source](URL_of_Source) | [License Name](#license-name)
>    - Title: **Title of First Modifying Work**, Modified By: **Author of First Modifying Work**, [Link to Source](URL_of_Source) | [License Name](#license-name)
>- Title: **Title of Original Work**, By: **Author of Original Work**, [Link to Source](URL_of_Source) | [License Name](#license-name)

Note that you start with the citation to the work you directly used as a source, then work bact towards the original author of the text.

## 5.1.2: Crediting a Document That Does Not Use Adorn

Adorn gives a standardized way to credit work from non Adorn compliant sources as well.  However, if a non Adorn work is based on copied text from a third separate work, Adorn does not give a standardized way to credit that third work. In this case, please follow the terms of the license of the work you copied the text from and that third work.

The format for citing a non Adorn source is below:

Raw markdown text:

    <a name="title-of-source-work">Title of Source Work</a>
    - Title: Title of Source Work, By: Author Name, Version: Edition of the Work etc. [Link to Source](URL_of_Source) | [Link to License: License Name](#license-name)

Rendered markdown text:

><a name="title-of-source-work">Title of Source Work</a>
>- Title: Title of Source Work, By: Author Name, Version: Edition of the Work etc. [Link to Source](URL_of_Source) | [Link to License: License Name](#license-name)

## 5.1.3: Crediting Adorn

At the end of your credits section please also put the following credit to the Adorn standard.  This both indicates that you are using the standard and helps other authors find us!

    Adorn
    - This document uses the Adorn standard for easy and transparent sharing of text.  To learn more, about Adorn see the [Adorn Standard](https://github.com/DeMystic/Adorn).  The text of the Adorn standard is offered under a [CC BY 4.0 License](https://creativecommons.org/licenses/by/4.0/).

## 5.2: Licenses

All text that you are required to include by the licenses of the works that you have copied or modified from goes in this section.  Each license that requires you to include text in your document has its own section here.  

When you use text from one source that is modified from some third source, always check if you need to be compliant with the license of that third source.  If so, include any text required to be compliant with the license of that third source in this section as well.

Start each section with an anchor containing the license name and follow it with the text that the license requires you to include.  Often this text includes the text of the original license or a link to it.  Use the following format to do this.

Raw markdown text:

    <a name="license-name">License Name</a>
    - Required Text 1
    - Required Text 2

Rendered markdown text:

><a name="license-name">License Name</a>
>- Required Text 1
>- Required Text 2

If it is unclear if the author intends for you to use their text the way you want to, reach out to them and ask even if their license seems to permit the use you intend.

Some licenses require you to include some version of themselves in your work. Those licenses go in this section.

Some licenses require you to include text in addition to the licenses text.  That text also goes in this section. If the license requires you to add specific text to other parts of your document outside of what adorn requires, pease do so.

## 5.3: Acknowledgements  

Sometimes you want to acknowledge someone's influence on your work because:
- You used some of their ideas (but none of their text)
- They inspired you with their own work
- They supported you in some way
- Any other reason.

The Acknowledgements section is the place todo it!  Adorn prescribes no format for how to do this, but encourages you to do it liberally and to feel free to link to this section (or to any piece of this section) in your text if you think it's appropriate.

## 5.4: Including a License for Your Document

In this section we briefly discuss a few licenses.  This discussion is not intended as a full description of the licenses, nor is it intended as legal advice.  Follow the links provided to find the full legal text of the mentioned licenses.

At the end of your file, you may include a license for your own document. This is what allows other authors to use and share the text within your document. The license also tells other authors exactly what they can/cant do with your work and how to credit you.

The default licenses for Adorn compliant documents are:
- [The CC BY 4.0 License](https://creativecommons.org/licenses/by/4.0/)
- [The CC BY-SA 4.0 License](https://creativecommons.org/licenses/by/4.0/)

A work licensed under a CC BY license can be shared more freely while a work licensed under a CC BY-SA license forces others who use the work to share their work too.

Licensing your work under a CC BY license essentially means that anyone can use your work for any purpose as long as they credit you appropriately and don't say that you endorse their work. Licensing your work under a CC BY-SA license essentially means the same as doing so under a CC BY license, but anyone using your work must also publish their work under a license with the similar terms.  The way that CC BY-SA forces people to share work under similar terms and is sometimes referred to as "copyleft."

Note that if your work is licensed under CC BY-SA, it can still include text from other sources that are licensed under CC BY (like the text of this standard).

You are not restricted to picking between the two Licenses mentioned above, but they have the benefit of making your work very easy and attractive to copy/modify while still giving you credit as an original or modifying author.

Note that both of the above licenses allow commercial use of your work by others. See [the other CC licenses](https://creativecommons.org/licenses) for examples of licenses that more strictly limit commercial use and/or other kinds of use.

Choose carefully before you publish/upload a work with a license attached.  Many licenses are irrevocable.

## 6: Hosting on GitHub

Files that comply with Adorn are typically hosted on GitHub or another online git-based repository.
GitHub (and other git-based repositories) automatically keep record or all older versions of your module files and game files which means that people who copy text from your modules can always cite the correct version of the source material.

You can get very fancy when automating your workflow using git, but it's also easy enough to simply copy the text of your document or your document itself from your personal computer into your GitHub repository. In that case GitHub takes care of all the version control itself.

## 7: License for the Text of This Standard

The text of this standard is offered under a [CC BY 4.0 License](https://creativecommons.org/licenses/by/4.0/)

The below text summarizes what the license requires of you but is not a replacement for the license.  See the link above for the license itself.

You can not add any text to your document that implies that the authors of Adorn endorse your work.  You also may not do anything to restrict others from using the text of the Adorn standard.

Simply adding [the credit to the adorn standard](#513-crediting-adorn) is generally enough for a document that implements the standard to be compliant. In many regions, implementing the standard in your document may even qualify as fair use and require no citation to Adorn at all (we still very much still appreciate the citation in that case, it helps us grow!) 

If you are using parts of this text to publish a new standard based on Adorn, you need to explicitly state in your document that you modified the original text of the Adorn Standard and link to both the Adorn Standard and the CC BY 4.0 license that it is shared under.  You must aslo state explicitly that the text of Adorn is offered under the CC BY 4.0 license.
