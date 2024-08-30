# Markdown Cheat Sheet

> More info found here https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax


| Feature            | Syntax Example                                                     | Description                              |
|--------------------|--------------------------------------------------------------------|------------------------------------------|
| Headings           | `# H1`, `## H2`, `### H3`                                          | Create headings                          |
| Italics            | `*italic*` or `_italic_`                                           | Italic text                              |
| Bold               | `**bold**` or `__bold__`                                           | Bold text                                |
| Bold and Italic    | `***bold and italic***` or `___bold and italic___`                 | Bold and italic text                     |
| Unordered List     | `- Item`, `* Item`, `+ Item`                                       | Create unordered list                    |
| Ordered List       | `1. Item`                                                          | Create ordered list                      |
| Link               | `[link](https://example.com)`                                      | Create a hyperlink                       |
| Image              | `![alt text](https://example.com/image.jpg)`                       | Insert an image                          |
| Blockquote         | `> Blockquote`                                                     | Create blockquote                        |
| Inline Code        | `` `code` ``                                                       | Inline code snippet                      |
| Code Block         | ```` ```lang<br>code<br>``` ````                                   | Code block                               |
| Table              | `| Header | Header |<br>|--------|--------|<br>| Cell | Cell |`    | Create a table                          |
| Horizontal Rule    | `---`, `***`, `___`                                                | Create horizontal rule                   |
| HTML               | `<div>HTML</div>`                                                  | Embed HTML                               |
| Footnote           | `text[^1]<br>[^1]: Footnote text`                                  | Create a footnote                        |
| Task List          | `- [ ] Task`, `- [x] Task`                                         | Create task list                         |


# HTML and CSS in Markdown Cheat Sheet

| Feature         | Syntax Example                                                                                     | Description                                     |
|-----------------|----------------------------------------------------------------------------------------------------|-------------------------------------------------|
| Basic HTML      | `<div><h2>Heading</h2><p>Paragraph</p></div>`                                                      | Embed basic HTML elements                       |
| Links           | `<a href="https://example.com" target="_blank">Link</a>`                                           | Create hyperlinks with HTML                     |
| Images          | `<img src="https://example.com/image.jpg" alt="Image" width="200" height="150">`                   | Insert images with HTML                         |
| Forms           | `<form action="/submit" method="POST"><input type="text" name="name"><input type="submit"></form>` | Embed forms                                     |
| Tables          | `<table><tr><td>Cell</td></tr></table>`                                                            | Create tables with HTML                         |
| Inline CSS      | `<p style="color: blue;">Styled Text</p>`                                                          | Add inline CSS to HTML elements                 |
| Internal CSS    | `<style>.class { color: red; }</style><div class="class">Styled Div</div>`                         | Define internal styles within a `<style>` tag   |
| External CSS    | `<link rel="stylesheet" href="https://example.com/styles.css">`                                    | Link to external CSS files                      |
| Mixed Markdown  | `# Markdown <div style="color: red;">HTML</div>`                                                   | Combine Markdown and HTML                       |

# Advanced Styled Content in Markdown
> I cannot get this to work on github yet

```markdown

## Example 1: Colored Text

You can use inline styles to add color to your text.

<p style="color: blue; font-size: 18px;">This is a blue, larger text paragraph.</p>

<p style="color: green; font-weight: bold;">This is a bold, green text.</p>

## Example 2: Styled Div

Use a div with styles for more complex styling.

<div style="background-color: lightgrey; padding: 20px; border-radius: 10px;">
  <h2 style="color: darkblue;">Styled Div Heading</h2>
  <p style="font-family: Arial, sans-serif;">This is a paragraph inside a styled div. The div has a light grey background, padding, and rounded corners.</p>
</div>

## Example 3: Styled Table

Create a table with HTML and add styles.

<table style="width: 100%; border-collapse: collapse; margin: 20px 0;">
  <thead>
    <tr style="background-color: #f2f2f2;">
      <th style="border: 1px solid #ddd; padding: 8px; text-align: left;">Header 1</th>
      <th style="border: 1px solid #ddd; padding: 8px; text-align: left;">Header 2</th>
    </tr

```

