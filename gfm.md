Various extensions introduced by GitHub Flavored Markdown: https://github.github.com/gfm/

- [Extension: Tables](#extension-tables)
  - [Creating a table](#creating-a-table)
  - [Formatting content within your table](#formatting-content-within-your-table)
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

![Screenshot of a {% data variables.product.github %} Markdown table rendered as two equal columns. Headers are shown in boldface, and alternate content rows have gray shading.](https://github.com/github/docs/raw/main/assets/images/help/writing/table-basic-rendered.png)

The pipes on either end of the table are optional.

Cells can vary in width and do not need to be perfectly aligned within columns. There must be at least three hyphens in each column of the header row.

```markdown
| Command | Description |
| --- | --- |
| git status | List all new or modified files |
| git diff | Show file differences that haven't been staged |
```

![Screenshot of a {% data variables.product.github %} Markdown table with two columns of differing width. Rows list the commands "git status" and "git diff" and their descriptions.](https://github.com/github/docs/raw/main/assets/images/help/writing/table-varied-columns-rendered.png)

## Formatting content within your table

You can use [formatting](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) such as links, inline code blocks, and text styling within your table:

```markdown
| Command | Description |
| --- | --- |
| `git status` | List all *new or modified* files |
| `git diff` | Show file differences that **haven't been** staged |
```

![Screenshot of a {% data variables.product.github %} Markdown table with the commands formatted as code blocks. Bold and italic formatting are used in the descriptions.](https://github.com/github/docs/raw/main/assets/images/help/writing/table-varied-columns-rendered.png)

You can align text to the left, right, or center of a column by including colons `:` to the left, right, or on both sides of the hyphens within the header row.

```markdown
| Left-aligned | Center-aligned | Right-aligned |
| :---         |     :---:      |          ---: |
| git status   | git status     | git status    |
| git diff     | git diff       | git diff      |
```

![Screenshot of a Markdown table with three columns as rendered on {% data variables.product.github %}, showing how text within cells can be set to align left, center, or right.](https://github.com/github/docs/raw/main/assets/images/help/writing/table-inline-formatting-rendered.png)

To include a pipe `|` as content within your cell, use a `\` before the pipe:

```markdown
| Name     | Character |
| ---      | ---       |
| Backtick | `         |
| Pipe     | \|        |
```

![Screenshot of a Markdown table as rendered on {% data variables.product.github %} showing how pipes, which normally close cells, are shown when prefaced by a backslash.](https://github.com/github/docs/raw/main/assets/images/help/writing/table-escaped-character-rendered.png)

## Further reading

* [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)