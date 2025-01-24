Various extensions introduced by GitHub Flavored Markdown: https://github.github.com/gfm/

- [Extension: Tables](#extension-tables)
  - [Creating a table](#creating-a-table)
  - [Formatting content within your table](#formatting-content-within-your-table)
- [Extension: Task List Items](#extension-task-list-items)
- [Extension: Strikethrough](#extension-strikethrough)
- [Extension: Autolinks](#extension-autolinks)
- [Extension: Disallowed Raw HTML](#extension-disallowed-raw-html)
- [Further reading](#further-reading)

# Extension: Tables

## Creating a table

You can create tables with pipes `|` and hyphens `-`. Hyphens are used to create each column's header, while pipes separate each column. You must include a blank line before your table in order for it to correctly render.

```markdown

| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
```

![Screenshot of a GitHub Markdown table rendered as two equal columns. Headers are shown in boldface, and alternate content rows have gray shading.](https://github.com/github/docs/raw/main/assets/images/help/writing/table-basic-rendered.png)

The pipes on either end of the table are optional.

Cells can vary in width and do not need to be perfectly aligned within columns. There must be at least three hyphens in each column of the header row.

```markdown
| Command | Description |
| --- | --- |
| git status | List all new or modified files |
| git diff | Show file differences that haven't been staged |
```

![Screenshot of a GitHub Markdown table with two columns of differing width. Rows list the commands "git status" and "git diff" and their descriptions.](https://github.com/github/docs/raw/main/assets/images/help/writing/table-varied-columns-rendered.png)

## Formatting content within your table

You can use [formatting](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) such as links, inline code blocks, and text styling within your table:

```markdown
| Command | Description |
| --- | --- |
| `git status` | List all *new or modified* files |
| `git diff` | Show file differences that **haven't been** staged |
```

![Screenshot of a GitHub Markdown table with the commands formatted as code blocks. Bold and italic formatting are used in the descriptions.](https://github.com/github/docs/raw/main/assets/images/help/writing/table-varied-columns-rendered.png)

You can align text to the left, right, or center of a column by including colons `:` to the left, right, or on both sides of the hyphens within the header row.

```markdown
| Left-aligned | Center-aligned | Right-aligned |
| :---         |     :---:      |          ---: |
| git status   | git status     | git status    |
| git diff     | git diff       | git diff      |
```

![Screenshot of a Markdown table with three columns as rendered on GitHub, showing how text within cells can be set to align left, center, or right.](https://github.com/github/docs/raw/main/assets/images/help/writing/table-inline-formatting-rendered.png)

To include a pipe `|` as content within your cell, use a `\` before the pipe:

```markdown
| Name     | Character |
| ---      | ---       |
| Backtick | `         |
| Pipe     | \|        |
```

![Screenshot of a Markdown table as rendered on GitHub showing how pipes, which normally close cells, are shown when prefaced by a backslash.](https://github.com/github/docs/raw/main/assets/images/help/writing/table-escaped-character-rendered.png)

# Extension: Task List Items

GFM enables the  `tasklist`  extension, where an additional processing step is performed on  [list items](https://github.github.com/gfm/#list-items).

A  [task list item](https://github.github.com/gfm/#task-list-item)  is a  [list item](https://github.github.com/gfm/#list-items)  where the first block in it is a paragraph which begins with a  [task list item marker](https://github.github.com/gfm/#task-list-item-marker)  and at least one whitespace character before any other content.

A  [task list item marker](https://github.github.com/gfm/#task-list-item-marker)  consists of an optional number of spaces, a left bracket (`[`), either a whitespace character or the letter  `x`  in either lowercase or uppercase, and then a right bracket (`]`).

When rendered, the  [task list item marker](https://github.github.com/gfm/#task-list-item-marker)  is replaced with a semantic checkbox element; in an HTML output, this would be an  `<input type="checkbox">`  element.

If the character between the brackets is a whitespace character, the checkbox is unchecked. Otherwise, the checkbox is checked.

This spec does not define how the checkbox elements are interacted with: in practice, implementors are free to render the checkboxes as disabled or inmutable elements, or they may dynamically handle dynamic interactions (i.e. checking, unchecking) in the final rendered document.

[Example 279](https://github.github.com/gfm/#example-279)

```markdown
- [ ] foo
- [x] bar
```

- [ ] foo
- [x] bar

[Example 280](https://github.github.com/gfm/#example-280)

```markdown
- [x] foo
  - [ ] bar
  - [x] baz
- [ ] bim
```

- [x] foo
  - [ ] bar
  - [x] baz
- [ ] bim

# Extension: Strikethrough

GFM enables the  `strikethrough`  extension, where an additional emphasis type is available.

Strikethrough text is any text wrapped in a matching pair of one or two tildes (`~`).

[Example 491](https://github.github.com/gfm/#example-491)

```markdown
~~Hi~~ Hello, ~there~ world!
```

~~Hi~~ Hello, ~there~ world!

As with regular emphasis delimiters, a new paragraph will cause strikethrough parsing to cease:

[Example 492](https://github.github.com/gfm/#example-492)

```markdown
This ~~has a

new paragraph~~.
```

This ~~has a

new paragraph~~.

Three or more tildes do not create a strikethrough:

[Example 493](https://github.github.com/gfm/#example-493)

```markdown
This will ~~~not~~~ strike.
```

This will ~~~not~~~ strike.

# Extension: Autolinks

# Extension: Disallowed Raw HTML

GFM enables the  `tagfilter`  extension, where the following HTML tags will be filtered when rendering HTML output:

- `<title>`
- `<textarea>`
- `<style>`
- `<xmp>`
- `<iframe>`
- `<noembed>`
- `<noframes>`
- `<script>`
- `<plaintext>`

Filtering is done by replacing the leading  `<`  with the entity  `&lt;`. These tags are chosen in particular as they change how HTML is interpreted in a way unique to them (i.e. nested HTML is interpreted differently), and this is usually undesireable in the context of other rendered Markdown content.

All other HTML tags are left untouched.

# Further reading

* [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)