# Introduction

Lazy markup language

#TODO

| Markdown               | AsciiDoc               | HTML               | LZML      | Style                    |
| ---------------------- | ---------------------- | ------------------ | --------- | ------------------------ |
| `**...**` or `__...__` | `*...*`                | `<b>...</b>`       | `[b ...]` | **Bold**                 |
| `*...*` or `_..._`     | `_..._`                | `<i>...</i>`       | `[i ...]` | _Italic_                 |
| `<u>...</u>`           | `[.underline]#...#`    | `<u>...</u>`       | `[u ...]` | <u>Underlined</u>        |
| `~~...~~`              | `[.line-through]#...#` | `<s>...</s>`       | `[s ...]` | ~~Strike~~               |
| `<mark>...</mark>`     | `#...#`                | `<mark>...</mark>` | `[h ...]` | <mark>Highlighted</mark> |
| `<sub>...</sub>`       | `~...~`                | `<sub>...</sub>`   | `[, ...]` | <sub>subscripted</sub>   |
| `<sup>...</sup>`       | `^...^`                | `<sup>...</sup>`   | `[^ ...]` | <sup>superscripted</sup> |
| `` `...` ``            | `` `...` ``            | `<pre>...</pre>`   | `[m ...]` | `Monospace`              |

# Preliminaries

#TODO

# Blocks and inlines

#TODO

# Leaf blocks

## Fenced code blocks

#FIXME

A code fence is a sequence of at least three consecutive backtick characters (`` ` ``).
A fenced code block begins with a code fence, with indented any number of spaces or tabs.

The line with the opening code fence may optionally contain some text following the code fence; this is trimmed of leading and trailing whitespace and called the info string.
It may not contain any backtick characters.

> The reason for this restriction is that otherwise some inline code would be incorrectly interpreted as the beginning of a fenced code block.

The content of the code block consists of all subsequent lines, until a closing code fence with as many backticks as the opening code fence.
If the leading code fence is indented N spaces, then up to N spaces of indentation must be present on each line and they will be removed from each line of the content.

The closing code fence must be indented exactly the same as the opening code fence, and may be followed only by spaces, which are ignored.
If the end of the containing block or document is reached and no closing code fence has been found,
the code block contains all of the lines after the opening code fence until the end of the containing block or document.

A fenced code block may interrupt a paragraph, and does not require a blank line either before or after.

The content of a code fence is treated as literal text, not parsed as inlines.
The first word of the info string is typically used to specify the language of the code sample, and rendered in the `class` attribute of the `code` tag.

## Tables

#TODO

- https://github.github.com/gfm/#tables-extension-
- https://www.pml-lang.dev/docs/reference_manual/index.html#node_admon
- https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#tables

# Container blocks

## List items

#FIXME

A list marker is a bullet list marker or an ordered list marker.

A bullet list marker is a `-` character.

An ordered list marker is a sequence of 1–9 arabic digits (`0-9`), followed by a `.` character.
(The reason for the length limit is that with 10 digits we start seeing integer overflows in some browsers.)

<!-- 
| Starter                         | Description                |
| ------------------------------- | -------------------------- |
| `-`                             | Bullet points              |
| `0.`, `1.`, `2.`, `3.`, ...     | Decimal numbers            |
| `a.`, `b.`, `c.`, `d.`, ...     | Alphabetically             |
| `I.`, `II.`, `III.`, `IV.`, ... | Roman numbers              |
-->

The following rules define list items:
1. **Basic case:** If a sequence of lines _Ls_ constitute a sequence of blocks _Bs_ starting with a non-whitespace character,
   and _M_ is a list marker of width _W_ followed by 1 ≤ _N_ ≤ 4 spaces, then the result of prepending _M_ and the following spaces to the first line of _Ls_,
   and indenting subsequent lines of _Ls_ by _W + N_ spaces, is a list item with _Bs_ as its contents.
   The type of the list item (bullet or ordered) is determined by the type of its list marker.
   If the list item is ordered, then it is also assigned a start number, based on the ordered list marker. Exceptions:
    1. When the first list item in a [list](#list) interrupts a paragraph—that is,
       when it starts on a line that would otherwise count as [paragraph continuation text](#paragraph-continuation-text)—then
       (a) the lines _Ls_ must not begin with a blank line, and
       (b) if the list item is ordered, the start number must be 1.
    2. If any line is a [thematic break](#thematic-breaks) then that line is not a list item.
2. **Item starting with indented code:** If a sequence of lines _Ls_ constitute a sequence of blocks _Bs_ starting with an indented code block,
   and _M_ is a list marker of width _W_ followed by one space, then the result of prepending _M_ and the following space to the first line of _Ls_,
   and indenting subsequent lines of _Ls_ by _W + 1_ spaces, is a list item with _Bs_ as its contents.
   If a line is empty, then it need not be indented.
   The type of the list item (bullet or ordered) is determined by the type of its list marker.
   If the list item is ordered, then it is also assigned a start number, based on the ordered list marker.
3. **Item starting with a blank line:** If a sequence of lines _Ls_ starting with a single [blank line](#blank-line) constitute a (possibly empty) sequence of blocks _Bs_,
   not separated from each other by more than one blank line, and _M_ is a list marker of width _W_, then the result of prepending _M_ to the first line of _Ls_,
   and indenting subsequent lines of _Ls_ by _W + 1_ spaces, is a list item with _Bs_ as its contents. If a line is empty,
   then it need not be indented. The type of the list item (bullet or ordered) is determined by the type of its list marker.
   If the list item is ordered, then it is also assigned a start number, based on the ordered list marker.
4. **Indentation:** If a sequence of lines _Ls_ constitutes a list item according to rule #1, #2, or #3,
   then the result of indenting each line of _Ls_ by 1-3 spaces (the same for each line)
   also constitutes a list item with the same contents and attributes. If a line is empty, then it need not be indented.
5. **Laziness:** If a string of lines _Ls_ constitute a list item with contents _Bs_,
   then the result of deleting some or all of the indentation from one or more lines in which the next non-whitespace character
   after the indentation is [paragraph continuation text](#paragraph-continuation-text) is a list item with the same contents and attributes.
   The unindented lines are called [lazy continuation line](#lazy-continuation-line)s.

## Task list items

A task list item is a [list item](#list-items) where the first block in it is a paragraph which begins with a task list item marker and at least one whitespace character before any other content.

A task list item marker consists of an optional number of spaces, a left bracket (`[`), either a whitespace character or the letter `x` in lowercase,and then a right bracket (`]`).

When rendered, the task list item marker is replaced with a semantic checkbox element; in an HTML output, this would be an `<input type="checkbox">` element.

If the character between the brackets is a whitespace character, the checkbox is unchecked. Otherwise, the checkbox is checked.

## Lists

#FIXME

A list is a sequence of one or more list items of the same type. The list items may be separated by any number of blank lines.

Two list items are of the same type if they begin with a list marker of the same type.
Two list markers are of the same type if
(a) they are bullet list markers or
(b) they are ordered list. #FIXME

A list is an ordered list if its constituent list items begin with ordered list markers, and a bullet list if its constituent list items begin with bullet list markers.

The start number of an ordered list is determined by the list number of its initial list item. The numbers of subsequent list items are disregarded. #FIXME

A list is loose if any of its constituent list items are separated by blank lines,
or if any of its constituent list items directly contain two block-level elements with a blank line between them. Otherwise a list is tight.
(The difference in HTML output is that paragraphs in a loose list are wrapped in `<p>` tags, while paragraphs in a tight list are not.)

# Inlines

## Backslash escapes

#TODO

| Escapes  | Charater | Name                  |
| -------- | -------- | --------------------- |
| `\\`     | `\`      | Backslash             |
| `\&`     | `&`      | Ampersand             |
| `\[`     | `[`      | Left square brackets  |
| `\]`     | `]`      | Right square brackets |
| `\=`     | `=`      | Equals sign           |
| `\'`     | `'`      | Apostrophe            |
| `\"`     | `"`      | Quotation marks       |
| `` \` `` | `` ` ``  | Grave accent          |
| `\-`     | `-`      | Hyphen/minus          |
| `\\|`    | `\|`     | Vertical bar          |

## Code spans

#FIXME

A backtick string is a string of one or more backtick characters (`` ` ``) that is neither preceded nor followed by a backtick.

A code span begins with a backtick string and ends with a backtick string of equal length.
The contents of the code span are the characters between the two backtick strings, normalized in the following ways:

- First, line endings are converted to spaces.
- If the resulting string both begins and ends with a space character, but does not consist entirely of space characters, a single space character is removed from the front and back.
  This allows you to include code that begins or ends with backtick characters, which must be separated by whitespace from the opening or closing backtick strings.

## Auto media

#TODO

`[! "URL" ...]`

---

## Removes

#TODO

| HTML Tag                                                       | Description                 |
| -------------------------------------------------------------- | --------------------------- |
| [`<!DOCTYPE>`](https://www.w3schools.com/tags/tag_doctype.asp) | Defines the document type   |
| [`<html>`](https://www.w3schools.com/tags/tag_html.asp)        | Defines an HTML document    |
| [`<body>`](https://www.w3schools.com/tags/tag_body.asp)        | Defines the document's body |

## Replace

#TODO

| HTML tag                                                                            | LZML Tag                    | Description                                                            |
| ----------------------------------------------------------------------------------- | --------------------------- | ---------------------------------------------------------------------- |
| [`<mark>...</mark>`](https://www.w3schools.com/tags/tag_mark.asp)                   | `[h ...]`                   | Defines Highlighted text                                               |
| [`<pre>...</pre>`](https://www.w3schools.com/tags/tag_pre.asp)                      | `[m ...]`                   | Defines monospace text (preformatted text)                             |
| [`<small>...</small>`](https://www.w3schools.com/tags/tag_small.asp)                | `[. ...]`                   | Defines smaller text                                                   |
| [`<sub>...</sub>`](https://www.w3schools.com/tags/tag_sub.asp)                      | `[, ...]`                   | Defines subscripted text                                               |
| [`<sup>...</sup>`](https://www.w3schools.com/tags/tag_sup.asp)                      | `[^ ...]`                   | Defines superscripted text                                             |
| [`<!--...-->`](https://www.w3schools.com/tags/tag_comment.asp)                      | `[# ...]`                   | Defines a comment                                                      |
|                                                                                     |                             |                                                                        |
| [`<strong>...</strong>`](https://www.w3schools.com/tags/tag_strong.asp)             | `[* ...]`                   | Defines important text                                                 |
| [`<em>...</em>`](https://www.w3schools.com/tags/tag_em.asp)                         | `[~ ...]`                   | Defines emphasized text                                                |
| [`<ins>...</ins>`](https://www.w3schools.com/tags/tag_ins.asp)                      | `[+ ...]`                   | Defines a text that has been inserted into a document                  |
| [`<del>...</del>`](https://www.w3schools.com/tags/tag_del.asp)                      | `[- ...]`                   | Defines text that has been deleted from a document                     |
|                                                                                     |                             |                                                                        |
| [`<address>...</address>`](https://www.w3schools.com/tags/tag_address.asp)          | `[@ ...]`                   | Defines contact information for the author/owner of a document/article |
| [`<abbr>...</abbr>`](https://www.w3schools.com/tags/tag_abbr.asp)                   | `[a ...]`                   | Defines an abbreviation or an acronym                                  |
| [`<code>...</code>`](https://www.w3schools.com/tags/tag_code.asp)                   | `[c ...]`                   | Defines a piece of computer code                                       |
| [`<cite>...</cite>`](https://www.w3schools.com/tags/tag_cite.asp)                   | `[t ...]`                   | Defines the title of a work                                            |
| [`<dfn>...</dfn>`](https://www.w3schools.com/tags/tag_dfn.asp)                      | `[d ...]`                   | Specifies a term that is going to be defined within the content        |
| [`<kbd>...</kbd>`](https://www.w3schools.com/tags/tag_kbd.asp)                      | `[k ...]`                   | Defines keyboard input                                                 |
| [`<var>...</var>`](https://www.w3schools.com/tags/tag_var.asp)                      | `[v ...]`                   | Defines a variable                                                     |
|                                                                                     |                             |                                                                        |
| [`<h1>...</h1>` to `<h6>...</h6>`](https://www.w3schools.com/tags/tag_hn.asp)       | `[= ...]` to `[====== ...]` | Defines HTML headings                                                  |
| [`<hr>`](https://www.w3schools.com/tags/tag_hr.asp)                                 | `[---]`                     | Defines a thematic change in the content                               |
| [`<blockquote>...</blockquote>`](https://www.w3schools.com/tags/tag_blockquote.asp) | `[> ...]`                   | Defines a section that is quoted from another source                   |
|                                                                                     |                             |                                                                        |
| [`<samp>...</samp>`](https://www.w3schools.com/tags/tag_samp.asp)                   | `[; ...]`                   | Defines sample output from a computer program                          |
| [`<div>...</div>`](https://www.w3schools.com/tags/tag_div.asp)                      | `[/ ...]`                   | Defines a section in a document                                        |

#TODO

| HTML                                                                | LZML          | Description         |
| ------------------------------------------------------------------- | ------------- | ------------------- |
| [`<a href="URL">...</a>`](https://www.w3schools.com/tags/tag_a.asp) | `["URL" ...]` | Defines a hyperlink |






[Button, and menu macros](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#keyboard-button-and-menu-macros)

[Admonitions](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#admonitions)

[More delimited blocks](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#more-delimited-blocks)


[IDs, roles, and options](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#ids-roles-and-options)

[Attributes and substitutions](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#attributes-and-substitutions)


[Bibliography](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#bibliography)

[Footnotes](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#section-footnotes)






```
| Escapes  | Charater | Name                  |
| ======== | ======== | ===================== |
| `\\`     | `\`      | Backslash             |
| `\&`     | `&`      | Ampersand             |
| `\[`     | `[`      | Left square brackets  |
| `\]`     | `]`      | Right square brackets |
| `\=`     | `=`      | Equals sign           |
| `\'`     | `'`      | Apostrophe            |
| `\"`     | `"`      | Quotation marks       |
| `` \` `` | `` ` ``  | Grave accent          |
| `\-`     | `-`      | Hyphen/minus          |
| `\|`     | `|`      | Vertical bar          |

[table
  [thead
    [tr [th Escapes  ][th Charater ][th Name                  ]]
  ]
  [tbody
    [tr [td `\\`     ][td `\`      ][td Backslash             ]]
    [tr [td `\&`     ][td `&`      ][td Ampersand             ]]
    [tr [td `\[`     ][td `[`      ][td Left square brackets  ]]
    [tr [td `\]`     ][td `]`      ][td Right square brackets ]]
    [tr [td `\=`     ][td `=`      ][td Equals sign           ]]
    [tr [td `\'`     ][td `'`      ][td Apostrophe            ]]
    [tr [td `\"`     ][td `"`      ][td Quotation marks       ]]
    [tr [td `` \` `` ][td `` ` ``  ][td Grave accent          ]]
    [tr [td `\-`     ][td `-`      ][td Hyphen/minus          ]]
    [tr [td `\|`     ][td `|`      ][td Vertical bar          ]]
  ]
]
```
