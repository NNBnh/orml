<h1 align="center">Orange markup language</h1>
<p align="center">A simple and powerful markup language</p>
<p align="center"><img src="https://emojipedia-us.s3.dualstack.us-west-1.amazonaws.com/thumbs/160/twitter/282/tangerine_1f34a.png"></p>
<p align="center"><a href="https://github.com/NNBnh/orml/blob/main/LICENSE"><img src="https://img.shields.io/github/license/NNBnh/orml?labelColor=585858&color=FF9470&style=for-the-badge" alt="License: GPL-3.0"></a> <!-- <a href="https://gist.github.com/NNBnh/9ef453aba3efce26046e0d3119dab5a7#development-completed"><img src="https://img.shields.io/badge/development-completed-%23FF9470.svg?labelColor=585858&style=for-the-badge&logoColor=FFFFFF" alt="Development completed"></a> --></p>

## 💡 About

<pre><code class="language-orml">[cite <b><i>Orange markup language</i></b>] is an "original" markup language,
design to replace both <a href="https://github.github.com/gfm">Markdown</a> and <a href="https://en.wikipedia.org/wiki/HTML5">HTML5</a>.

[="<b>📔 Story</b>"
  After looking for some alternative to <a href="https://github.github.com/gfm">Markdown</a>, I discover <a href="https://www.pml-lang.dev">PML</a>
  (Practical Markup Language) and [_ <em>IMO</em>] it's the best designed markup
  language so far.

  But I found it's a bit waste opportunity to have such a beautiful syntax
  that can directly harvest the raw power of <a href="https://en.wikipedia.org/wiki/HTML5">HTML5</a> but chose not to do so.
  And although PML's way of doing <a href="https://www.pml-lang.dev/docs/reference_manual/index.html#node_list">list</a> and <a href="https://www.pml-lang.dev/docs/reference_manual/index.html#node_table">table</a> is more consistent
  to it's syntax, I just miss the simple Markdown way.

  This motivates me to create a new markup language but with a different
  approac: by using HTML5 as the core, change the syntax to PML, add some
  features from Markdown, and we have [* <b>Orange markup language!</b>]
]

[="<b>✨ Features</b>"
  - With the raw power of <a href="https://en.wikipedia.org/wiki/HTML5">HTML5</a> plus:
    - <a href="#-11-syntax">Beautiful syntax</a> inspired by <a href="https://www.pml-lang.dev">PML</a>.
    - <a href="#%EF%B8%8F-13-alias-tags">Tag's aliases</a>.
    - Can be integrated with web frameworks (WIP).
  - Come with many <a href="https://github.github.com/gfm">Markdown</a>'s convenient features:
    - <a href="#-22-codes">Code spans</a>.
    - <a href="#-23-simple-lists">Simple lists</a>.
    - <a href="#%EF%B8%8F-24-simple-tables">Simple tables</a>.
]</code></pre>

Here are some comparison:

| Markdown               | AsciiDoc               | HTML               | ORML      | Style                    |
| ---------------------- | ---------------------- | ------------------ | --------- | ------------------------ |
| `**...**` or `__...__` | `*...*`                | `<b>...</b>`       | `[b ...]` | **Bold**                 |
| `*...*` or `_..._`     | `_..._`                | `<i>...</i>`       | `[i ...]` | _Italic_                 |
| `<u>...</u>`           | `[.underline]#...#`    | `<u>...</u>`       | `[u ...]` | U̲n̲d̲e̲r̲l̲i̲n̲e̲d̲               |
| `~~...~~`              | `[.line-through]#...#` | `<s>...</s>`       | `[s ...]` | ~~Strike~~               |
| `<mark>...</mark>`     | `#...#`                | `<mark>...</mark>` | `[% ...]` | `𝐇𝐢𝐠𝐡𝐥𝐢𝐠𝐡𝐭𝐞𝐝`            |
| `<sub>...</sub>`       | `~...~`                | `<sub>...</sub>`   | `[, ...]` | <sub>subscripted</sub>   |
| `<sup>...</sup>`       | `^...^`                | `<sup>...</sup>`   | `[^ ...]` | <sup>superscripted</sup> |
| `` `...` ``            | `` `...` ``            | `<pre>...</pre>`   | `[$ ...]` | `Monospace`              |

<br>

<!--

## 🚀 Setup

### 🧾 Dependencies

### 📥 Installation

<br>

## ⌨️ Usage

<br>

-->

## 📙 Reference

This document attempts to specify Orange markup language syntax.

> *Orange markup language will often be referred to as ORML in this document.*

### 📜 1. HTML power

ORML is basically HTML5 under the hood. So every syntaxes, elements and rulesets (even [`&` character reference](https://www.w3schools.com/charsets/ref_html_symbols.asp)) of HTML will be applied to ORML but with changes declared below.

####  📏 1.1. Syntax

> An HTML element is defined by a start tag, some content , and an end tag (some time not require):
> - A start tag open with a `<` character follow by the tag name and optionally with some attributes, then end with a `>` character. An end tag is the same but open with `</`.
> - An attribute start with the attribute name follow by a `=` character then some value wrapped by `"`/`'` characters.
>
> Examples:
>
> ```html
> <tagname>
> <tagname>content</tagname>
> <tagname attribute="value" more-attribute="value">
> <tagname attribute="value" more-attribute="value">content</tagname>
> ```

An ORML element is defined by a tag with some context inside it:
- A tag open with a `[` character follow by the tag name and optionally with some attributes and/or some context, then end with a `]` character.
- An attribute start with the attribute name follow by a `=` character then some value wrapped by `"`/`'` characters or by a curly brackets (`{`, `}`).
- The tag's context must be at the end of the tag (right before the `]` character). If the context look like an attribute, you need to escape the `=` character <!-- (escape `{` or/and `}` if it look like a dynamic attribute) -->.
<!-- - An attribute can be [Svelte's dynamic attribute](https://svelte.dev/tutorial/dynamic-attributes) which start and end with an open and close curly brackets (`{`, `}`). -->

Examples:

```orml
[tagname]
[tagname content]
[tagname attribute="value" more-attribute="value"]
[tagname attribute="value" more-attribute="value" content]
```

#### 🔥 1.2. Replaced/Removed tags

The following HTML tags have been removed or replaced on ORML:

| HTML tags                                                         | ORML tags | Description               |
| ----------------------------------------------------------------- | --------- | ------------------------- |
| [`<!DOCTYPE>`](https://www.w3schools.com/tags/tag_doctype.asp)    | _Remove_  | Defines the document type |
| [`<html>...</html>`](https://www.w3schools.com/tags/tag_html.asp) | _Remove_  | Defines an HTML document  |
| [`<!--...-->`](https://www.w3schools.com/tags/tag_comment.asp)    | `[# ...]` | Defines a comment         |

#### 🏷️ 1.3. Alias tags

To make ORML more readable, the following HTML tags have aliases (and it's the prefer way to write those tags):

> **NOTE:** Some of the aliases are strict, meaning that you have to write it in exactly that specific way.

| HTML tags                                                                                        | ORML alias tags                | Description                                         |
| ------------------------------------------------------------------------------------------------ | ------------------------------ | --------------------------------------------------- |
| [`<strong>...</strong>`](https://www.w3schools.com/tags/tag_strong.asp)                          | `[* ...]`                      | Defines important text                              |
| [`<em>...</em>`](https://www.w3schools.com/tags/tag_em.asp)                                      | `[_ ...]`                      | Defines emphasized text                             |
| [`<ins>...</ins>`](https://www.w3schools.com/tags/tag_ins.asp)                                   | `[+ ...]`                      | Defines text that has been inserted into a document |
| [`<del>...</del>`](https://www.w3schools.com/tags/tag_del.asp)                                   | `[- ...]`                      | Defines text that has been deleted from a document  |
| [`<mark>...</mark>`](https://www.w3schools.com/tags/tag_mark.asp)                                | `[% ...]`                      | Defines marked/highlighted text                     |
| [`<pre>...</pre>`](https://www.w3schools.com/tags/tag_pre.asp)                                   | `[$ ...]`                      | Defines monospace text (preformatted text)          |
| [`<small>...</small>`](https://www.w3schools.com/tags/tag_small.asp)                             | `[. ...]`                      | Defines smaller text                                |
| [`<sub>...</sub>`](https://www.w3schools.com/tags/tag_sub.asp)                                   | `[, ...]`                      | Defines subscripted text                            |
| [`<sup>...</sup>`](https://www.w3schools.com/tags/tag_sup.asp)                                   | `[^ ...]`                      | Defines superscripted text                          |
| [`<hr>` (`<hr>...</hr>`)](https://www.w3schools.com/tags/tag_hr.asp)                             | `[---]` (`[--- ...]`)          | Defines thematic change in the content              |
| [`<span>...</span>`](https://www.w3schools.com/tags/tag_span.asp)                                | `[; ...]`                      | Defines section in a document                       |
| [`<span class="spoiler">...</span>`](https://www.w3schools.com/tags/tag_span.asp)                | `[? ...]`                      | Defines spoiler text                                |
| [`<input type="checkbox" disabled="">`](https://www.w3schools.com/tags/tag_input.asp)            | `[ ]` <sub>strict</sub>        | Defines unchecked checkbox                          |
| [`<input type="checkbox" disabled="" checked="">`](https://www.w3schools.com/tags/tag_input.asp) | `[@]` <sub>strict</sub>        | Defines checked checkbox                            |
| [`<a href="URL">...</a>` or `<a href='URL'>...</a>`](https://www.w3schools.com/tags/tag_a.asp)   | `["URL" ...]` or `['URL' ...]` | Defines hyperlink                                   |

> *If the hyperlink alias tag doesn't have any content, it will use the URL as content:*<br>
> - *If it's also a cross reference, it will remove the first `#` character of the content and wrapped by a square brackets (`[`, `]`).*
> - *If it's also a email address (start with `mailto:`), it will trim `mailto:` and the following whitespaces at the beginning of the content.*

#### 📚 1.4. Chapter tags

Tag: `[="HEADER" ...]`

Inspired by [PML's Chapter node](https://www.pml-lang.dev/docs/reference_manual/index.html#node_ch),
chapter tag is an alias for the [HTML's `<section>` tag](https://www.w3schools.com/TAgs/tag_section.asp) with a definedable header:
- The header level will automatically be assigned by how many chapter tag is the current one in plus one.
- If there is a chapter tag inside more than 5 chapter tags, it's will be header level will alway be 6.
- Header can include any inline elements like [tags](#11--syntax), [autolinks](#-21-autolinks), [code spans](#-22-codes)...

Examples:

```orml
[section
  [h1 Title]
  [section
    [h2 [_ About]]
    Some introduction...
  ]

  [section
    [h2 Tutorial]
    How to...

    [section
      [h3 The `print()` command]
      Information...
    ]
  ]
]
```

Can be better write as:

```orml
[="Title"
  [="[_ About]"
    Some introduction...
  ]

  [="Tutorial"
    How to...

    [="The `print()` command"
      Information...
    ]
  ]
]
```

<table><body><tr><td>

# Title
## _About_
Some introduction...

## Tutorial
How to...

### The `print()` command
Information...

</td></tr></body></table>

<br>

### 📑 2. Markdown simplicity

To make the language easier to read and write, ORML include many feature from [GFM](https://github.github.com/gfm).

> *Because ORML doesn't support [indented code blocks](https://github.github.com/gfm/#indented-code-blocks) so every element (fenced code blocks, lists, tables, ...) can be indented freely (by it own rule) without become a code block.*

#### 🔗 2.1. Autolinks

ORML support [autolinks (extension)](https://github.github.com/gfm/#autolinks-extension-) (**not the original [autolinks](https://github.github.com/gfm/#autolinks)**) exactly like from [GFM](https://github.github.com/gfm).

Examples:

```orml
You can just type https://github.com/NNBnh and it will turn in to a link.
```

<table><body><tr><td>

You can just type https://github.com/NNBnh and it will turn in to a link.

</td></tr></body></table>

#### 📟 2.2. Codes

ORML support [fenced code blocks](https://github.github.com/gfm/#fenced-code-blocks) from [GFM](https://github.github.com/gfm) but with the following difference:
- A [code fence](https://github.github.com/gfm/#code-fence) is a sequence of at least three consecutive `` ` `` characters (and not `~` characters).
- The line with the closing code fence may optionally contain some text that start with the `.` character following the code fence; this is trimmed of leading and trailing whitespace and called the [info string](https://github.github.com/gfm/#info-string) (and it may not contain any `` ` `` characters).

ORML support [code spans](https://github.github.com/gfm/#code-spans) from [GFM](https://github.github.com/gfm) but with the following difference:
- The closing backtick strings of a [code spans](https://github.github.com/gfm/#code-spans) may optionally contain some text that start with the `.` character that function like [fenced code blocks](https://github.github.com/gfm/#fenced-code-blocks)'s [info string](https://github.github.com/gfm/#info-string)

Examples:

`````orml
This is a code span: `print("Hello, World!")`.python

This is a code block:

```
string = "y"

while True:
    print(string)
```.python
`````

<table><body><tr><td>

This is a code span: `print("Hello, World!")`

This is a code block:

```python
string = "y"

while True:
    print(string)
```

</td></tr></body></table>

#### 📝 2.3. Simple Lists

ORML support [list items](https://github.github.com/gfm/#list-items)
and [lists](https://github.github.com/gfm/#lists) from [GFM](https://github.github.com/gfm) but with the following difference:
- A [bullet list marker](https://github.github.com/gfm/#bullet-list-marker) is a `-` character (and not a `+` nor a `*` character).
- An [ordered list marker](https://github.github.com/gfm/#ordered-list-marker) is a sequence of 1–9 arabic digits `0-9`, followed by a `.` character (and not followed by a `)` character).

Examples:

```orml
Unordered list items:
- Start with a `-` character:
  - Not with `+`.
  - Nor with `*`.
- Very simple

Ordered list items:
1. Make every entry clarify
2. Look professional
```

<table><body><tr><td>

Unordered list items:
- Start with a `-` character:
  - Not with `+`.
  - Nor with `*`.
- Very simple

Ordered list items:
1. Make every entry clarify
2. Look professional

</td></tr></body></table>

#### 🗄️ 2.4. Simple tables

ORML support [tables](https://github.github.com/gfm/#tables-extension-) from [GFM](https://github.github.com/gfm) but with the following difference:
- A [table](https://github.github.com/gfm/#table) is an arrangement of data with rows and columns, consisting of at least one data rows, some header rows or/and footer rows (both are optional) separate by a delimiter row.
- The [delimiter row](https://github.github.com/gfm/#delimiter-row) consists of cells whose only content are hyphens `-`, and optionally, a leading or trailing equals sign `=` (and not colon `:`), or both, to indicate left, right, or center alignment respectively.
  - If there is no delimiter row in the table, all rows are data.
  - If there is one delimiter row in the table, all rows above the delimiter row are header, the rest are data.
  - If there is two or more delimiter row in the table, all rows above the first delimiter row are header, all rows below the last delimiter row are footer, the rest are data.

#### 🔣 2.5. Backslash escapes

Except inside [code spans or fenced code blocks](#-22-codes), any punctuation or space character preceded by a backslash will be treated literally, even if it would normally indicate formatting.

| Escapes  | Charater | Name                  |
| -------- | -------- | --------------------- |
| `\\`     | `\`      | Backslash             |
| `\&`     | `&`      | Ampersand             |
|          |          |                       |
| `\[`     | `[`      | Left square brackets  |
| `\]`     | `]`      | Right square brackets |
| `\=`     | `=`      | Equals sign           |
| `\'`     | `'`      | Apostrophe            |
| `\"`     | `"`      | Quotation marks       |
| `\{`     | `{`      | Left curly brackets   |
| `\}`     | `}`      | Right curly brackets  |
|          |          |                       |
| `` \` `` | `` ` ``  | Grave accent          |
|          |          |                       |
| `\-`     | `-`      | Hyphen/minus          |
| `\.`     | `.`      | Period                |
|          |          |                       |
| `\\|`    | `\|`     | Vertical bar          |
| `\-`     | `-`      | Hyphen/minus          |
| `\=`     | `=`      | Equals sign           |

<br>

## 💌 Credits
Special thanks to:
- [**PML (Practical Markup Language)**](https://www.pml-lang.dev) by [Christian Neumanns](https://www.pml-lang.dev/about/faq.html#creator)
- [**HTML5 (HyperText Markup Language)**](https://en.wikipedia.org/wiki/HTML5) by [W3C](https://www.w3.org)
- [**GitHub Flavored Markdown**](https://github.github.com/gfm) by [Github](https://github.com)
- [**Pandoc**](https://pandoc.org) by [John MacFarlane](https://johnmacfarlane.net)

<br><br><br><br>

---

> <h1 align="center">Made with ❤️ by <a href="https://github.com/NNBnh"><i>NNB</i></a></h1>
>
> <p align="center"><a href="https://www.buymeacoffee.com/nnbnh"><img src="https://img.shields.io/badge/buy_me_a_coffee%20-%23F7CA88.svg?logo=buy-me-a-coffee&logoColor=333333&style=for-the-badge" alt="Buy Me a Coffee"></a></p>
