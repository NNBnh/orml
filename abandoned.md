<h1 align="center">Abandoned features</h1>
<p align="center">List of feature that was considered but doesn't include in the end</p>

## Old name

1. Lazy markup language (LZML)
2. Unoriginal markup language (UOML)
3. _"Original"_ markup language (ORML)

> Final name: Orange markup language (ORML).

## Tags alternative syntax

HTML:

```html
<tagname attribute="value">content</tagname>
```

ORML:

```orml
[tagname(attribute="value") content]
```

HTML:

```html
<tagname attribute="value">
```

ORML:

```orml
[tagname(attribute="value")]
```

> This is too cluttered and verbose to type.

## More alternative tags

| HTML tags                                                                     | ORML alternative tags       | Description                                                                        |
| ----------------------------------------------------------------------------- | --------------------------- | ---------------------------------------------------------------------------------- |
| [`<h1>...</h1>` to `<h6>...</h6>`](https://www.w3schools.com/tags/tag_hn.asp) | `[= ...]` to `[====== ...]` | Defines a headings (the number of `=` character to the header level is correspond) |

> Become redundant by the new `[= ...]` extend tag

| HTML tags                                                                           | ORML alternative tags  | Description                                                            |
| ----------------------------------------------------------------------------------- | ---------------------- | ---------------------------------------------------------------------- |
| [`<div>...</div>`](https://www.w3schools.com/tags/tag_div.asp)                      | `[/ ...]`              | Defines section in a document                                          |
| [`<address>...</address>`](https://www.w3schools.com/tags/tag_address.asp)          | `[@ ...]`              | Defines contact information for the author/owner of a document/article |
| [`<abbr>...</abbr>`](https://www.w3schools.com/tags/tag_abbr.asp)                   | `[A ...]`              | Defines abbreviation or an acronym                                     |
| [`<cite>...</cite>`](https://www.w3schools.com/tags/tag_cite.asp)                   | `[T ...]`              | Defines the title of a work                                            |
| [`<code>...</code>`](https://www.w3schools.com/tags/tag_code.asp)                   | `[C ...]` or `[$ ...]` | Defines piece of computer code                                         |
| [`<dfn>...</dfn>`](https://www.w3schools.com/tags/tag_dfn.asp)                      | `[D ...]`              | Specifies a term that is going to be defined within the content        |
| [`<kbd>...</kbd>`](https://www.w3schools.com/tags/tag_kbd.asp)                      | `[K ...]`              | Defines keyboard input                                                 |
| [`<blockquote>...</blockquote>`](https://www.w3schools.com/tags/tag_blockquote.asp) | `[Q ...]` or `[> ...]` | Defines section that is quoted from another source                     |
| [`<samp>...</samp>`](https://www.w3schools.com/tags/tag_samp.asp)                   | `[S ...]`              | Defines sample output from a computer program                          |
| [`<var>...</var>`](https://www.w3schools.com/tags/tag_var.asp)                      | `[V ...]`              | Defines variable                                                       |
| [`<!--OLD_TEXT-->...`](https://www.w3schools.com/tags/tag_comment.asp)              | `[~"OLD_TEXT" ...]`    | Defines text that has been changed in a document                       |

> These tags are very use-case specific therefore readability more appreciated.

## More productivity features

[Thematic breaks](https://github.github.com/gfm/#thematic-breaks)

> Although this feature (`---`) is a little easier to type that the `[---]` tag, it's make the syntax more complex.

[ATX headings](https://github.github.com/gfm/#atx-headings)

> Become redundant by the `[= ...]` tag

[Block quotes](https://github.github.com/gfm/#block-quotes)

> Become redundant by the quote tables

[Footnotes](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#section-footnotes)

> Although this feature (`[: ...]`) is a little easier to type that the `["URL" ...]` tag, it's make the syntax more complex.
>
> Same with [bibliography](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#bibliography).
