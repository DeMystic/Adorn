# Adorn Quick Reference

This document is not the full specification of Adorn.  It is a quick reference for how Adorn expects features to be implemented in Adorn compliant markdown documents.

For a the full standard, see the Adorn Format Standard document.

## 1: Slot Comments

A slot should always fall under its own heading in your document.  The module in a slot can be made up of any kind of text, including sub headings, tables, or even other slot comments. 

You open a slot with an opening slot comment under its heading and close it with a closing slot comment at the end of the slot.

In a slot comment leave any field that you can not find a reference for empty.

Never reference a source that simply copied the text you want to use verbatim from a third source. Instead, reference the source that first produced the text in the form that you want to copy/modify.

Follow each opening comment of this type with a link to the credits section of your document of the following format:

    [(Credit: name of author)](#title-of-source-work)

Use the name of the work as the hyperlink text in the odd case that there is no author name.

## 1.1: Slots Containing Text from Other Slots

If the text in your slot is a copy of the entire text from a slot in a source document use this comment. Still use this comment if you have changed the formatting, but left the text the same. 

Opening slot comment to be placed under the heading that defines your slot:

    <!---Slot_Name: "name of this slot", Copied_From, Source_Slot: "name of source slot", Link: "URL of source"-->

Closing slot comment to be placed after your slot:

    <!---/Slot_Name: "name of this slot"-->
    
If the text in your slot is a modified form of the text in a slot in a source document OR if the text in your slot includes only part of the text in the source slot use this pair of opening and closing comments. Any non-formatting textual changes count as modifications.

Opening slot comment to be placed under the heading that defines your slot:

    <!---Slot_Name: "name of this slot", Modified_From, Source_Slot: "name of source slot", Link: "URL of source"-->

Closing slot comment to be placed after your slot:

    <!---/Slot_Name: "name of this slot"-->

## 1.2: Slots Containing Purely Original Text

If a slot contains only your original content use this pair of opening and closing comments.

Opening slot comment to be placed under the heading that defines your slot:

    <!---Slot_Name: "name_of_this_slot", Original-->

Closing slot comment to be placed after your slot:

    <!---/Slot_Name: "name_of_this_slot"-->

## 1.3: Slots Containing Text from non-Slot Sources

If a slot contains text from a source that does not use Adorn use this pair of opening and closing comments.  

Also use this type of opening and closing comments to include text from documents that do use Adorn when the the text you want to use is not annotated as a slot in the source document.

Use the following format if the text in your slot is directly coppied from the text in the source document.

Opening slot comment to be placed under the heading that defines your slot:

    <!---Slot_Name: "name of this slot", Copied_From, Source_Document: "Name of source document", Link: "URL of source if applicable"-->

Closing slot comment to be placed after your slot:

    <!---/Slot_Name: "name of this slot"-->

Alternatively, Use the following format if the text in your slot is modified from the text in the source document.

Opening slot comment to be placed under the heading that defines your slot:

    <!---Slot_Name: "name of this slot", Modified_From, Source_Document: "Name of source document", Link: "URL of source if applicable"-->

Closing slot comment to be placed after your slot:

    <!---/Slot_Name: "name of this slot"-->

## 2: Non-Modular Borrowed Text

To copy text from a source that is too short or broken up to warrant a slot, use the following comments.

Like with slot comments, leave the fields empty if there is no appropriate way to fill them.

Like with slot comments, never reference a source that simply copied the text you want to use verbatim from a third source. Instead, reference the source that first produced the text in the form that you want to copy/modify.

Place this comment at the end the paragraph that contains the copied text.

    <!---Copied_From, Source_Document: "Name of source document", Link: "URL of source if applicable"-->

Place this comment at the end the paragraph if you modified the source text or intermingled it with your own text:

    <!---Modified_From, Source_Document: "Name of source document", Link: "URL of source if applicable"-->

Follow each comment of this type with a link to the credits section of your document of the following format:

    [(Credit: name of author)](#title-of-source-work)

Use the name of the work as the hyperlink text in the odd case that there is no author name.

## 3: Attribution

All document that use Adorn need to have a Credits and a Licenses section.

## 3.1: Credits

All text included from other sources needs to be represented in the Credits section of your game file or module file.

When crediting a work, if a required piece of information can not be found, the field may be left blank if leaving it blank does not violate the terms of the license that covers that work.

You only need to include a link to the License section in a credit when the credited work's license requires you to include some text in your document.

## 3.1.1: Crediting a Document That Uses Adorn

A credit to an authors original text from an Adorn compliant source document looks like:

Raw markdown text:

    <a name="title-of-source-work">Title of Source Work\</a>
    - Title: **Title of Source Work**, By: **Author Name**. [Link to Source](URL_of_Source) | [License Name](#license-name)

Rendered markdown text:

><a name="title-of-source-work">Title of Source Work</a>
>- Title: **Title of Source Work**, By: **Author Name**. [Link to Source](URL_of_Source) | [License Name](#license-name)

A credit to a text that is a modified version of text from some other Adorn compliant source document looks like:

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

Note that you start with the citation to the work you directly used as a source, then work back towards the original author of the text.

## 3.1.2: Crediting a Document That Does Not Use Adorn

A credit to a non Adorn compliant source looks like:

Raw markdown text:

    <a name="title-of-source-work">Title of Source Work</a>
    - Title: Title of Source Work, By: Author Name, Version: Edition of the Work etc. [Link to Source](URL_of_Source) | [Link to License: License Name](#license-name)

Rendered markdown text:

><a name="title-of-source-work">Title of Source Work</a>
>- Title: Title of Source Work, By: Author Name, Version: Edition of the Work etc. [Link to Source](URL_of_Source) | [Link to License: License Name](#license-name)

## 3.1.3: Crediting Adorn

At the end of your credits section put the following credit to the adorn standard:

    Adorn
    - This document uses the Adorn Standard for easy and transparent sharing of text.  To learn more, about Adorn see the [Adorn Standard](https://github.com/DeMystic/Adorn).  The text of the Adorn Standard is offered under a [CC BY 4.0 License](https://creativecommons.org/licenses/by/4.0/).

## 3.2: Licenses

All text that you are required to include by the licenses of the text you have copied/modified into your document is included in the Licenses section.

When you use text from one source that is modified from some third source, always check if you need to be compliant with the license of that third source.  If so, include any text required to be compliant with the license of that third source in this section as well.

Use the following format to include this text:

Raw markdown text:

    <a name="license-name">License Name</a>
    - Required Text 1
    - Required Text 2

Rendered markdown text:

><a name="license-name">License Name</a>
>- Required Text 1
>- Required Text 2

## 3.3: Acknowledgements  

Sometimes you want to acknowledge someone's influence on your work, do that in the Acknowledgements section. Format it however you like.

## 4: Including a License for Your Document

In this section we briefly discuss a few licenses.  This discussion is not intended as a full description of the licenses, nor is it intended as legal advice.

At the end of your file you may include a License for your own document.

The default Licenses for Adorn compliant documents are:
- [The CC BY 4.0 License](https://creativecommons.org/licenses/by/4.0/)
- [The CC BY-SA 4.0 License](https://creativecommons.org/licenses/by/4.0/)

See the full Adorn Format Standard or the links to the licenses above for more details about what these two licenses imply.

You are not restricted to picking between the two Licenses mentioned above. See [the other CC licenses](https://creativecommons.org/licenses) for more examples.

Choose carefully before publish/upload a work with a license attached.  Many licenses are irrevocable.

## 5: License for this Document

The text of this abridged version of the standard is offered under a [CC BY 4.0 License](https://creativecommons.org/licenses/by/4.0/)

The below text summarizes what the license requires of you but is not a replacement for the license. See the link above for the license itself.

You can not add any text to your document that implies that the authors of Adorn endorse your work. You also may not do anything to restrict others from using the text of the Adorn standard.

Simply adding [the credit to the adorn standard](#313-crediting-adorn) is generally enough for a document that implements the standard to be compliant. In many regions, implementing the standard in your document may even qualify as fair use and require no citation to Adorn at all (we still very much still appreciate the citation in that case, it helps us grow!)

If you are using parts of this text to publish a new standard based on Adorn, you need to explicitly state in your document that you modified the original text of the Adorn Standard and link to both the Adorn Standard and the CC BY 4.0 license that it is shared under. You must also state explicitly that the text of Adorn is offered under the CC BY 4.0 license.
