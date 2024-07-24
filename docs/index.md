# Home

## About

These pages serve as personal documentation for all sorts of things. If it's more then 3 characters and I need to remember it, it's probably on here. It's explicity for personal use but if you can make use of anything you find here, feel free of course but use at your own risk, see disclaimer below. 

> The software is provided "as is," without any warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and non-infringement. In no event shall the authors or copyright holders be liable for any claim, damages, zombie apocalypses, alien invasions, spontaneous combustion, reality distortions, gravitational anomalies, acts of piracy (both digital and maritime), quantum entanglements gone awry, black hole creations, sudden outbreaks of disco fever, magical mishaps, bad hair days, decapitations, unexpected moustache growth, time travel paradoxes, existential crises, unintentional unicorn summoning,, loss of limbs, themonuclear warfare or other liability, whether in an action of contract, tort, or otherwise, arising from, out of, or in connection with the software or the use or other dealings in the software.

## Markdown documentation

### Basic syntax

| Feature          | Syntax                                 |
|------------------|----------------------------------------|
| Heading # H1     | `# H1`                                 |
| ## H2            | `## H2`                                |
| ### H3           | `### H3`                               |
| Bold             | `**bold text**`                        |
| Italic           | `*italicized text*`                    |
| Blockquote       | `> blockquote`                         |
| Ordered List     | `1. First item` <br> `2. Second item` <br> `3. Third item` |
| Unordered List   | `- First item` <br> `- Second item` <br> `- Third item`   |
| Code             | `` `code` ``                           |
| Horizontal Rule  | `---`                                  |
| Link             | `[title](https://www.example.com)`     |
| Image            | `![alt text](image.jpg)`               |


### Extended syntax

| Element              | Markdown Syntax                                                      |
|----------------------|----------------------------------------------------------------------|
| Table                | `| Syntax | Description |`<br>`| ----------- | ----------- |`<br>`| Header | Title |`<br>`| Paragraph | Text |` |
| Fenced Code Block    | \```<br>{<br>  "firstName": "John",<br>  "lastName": "Smith",<br>  "age": 25<br>}<br>\``` |
| Footnote             | `Here's a sentence with a footnote.[^1]`<br>`[^1]: This is the footnote.` |
| Heading ID           | `### My Great Heading {#custom-id}`                                  |
| Definition List      | `term`<br>`: definition`                                             |
| Strikethrough        | `~~The world is flat.~~`                                             |
| Task List            | `- [x] Write the press release`<br>`- [ ] Update the website`<br>`- [ ] Contact the media` |
| Emoji                | `That is so funny! :joy:`                                            |
| Highlight            | `I need to highlight these ==very important words==.`                |
| Subscript            | `H~2~O`                                                              |
| Superscript          | `X^2^`                                                               |


## Unix commands
    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

```
some copy i hope to copy
```

> wtf is even a blockquote

## Git
Code lives on four places through git

- local `code on your machine`
- staging area `code ready to be added to commit`
- commit `collection of changes made to repo`
- repo `final code on github`

Connecting to repo
```
git remote add origin <link>
```

Checking changes staged for commit
```
git status
```

Adding changes to commit `adds all changed files to commit, you can also do file.sth instead of .`
```
git add .
```

Making a commit
```
git commit -m "What changed?"
```

Pushing commit to repo `pushes to main branch`
```
git push -u origin main
```