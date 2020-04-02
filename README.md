[purr]: https://purrbot.site/github

[list1]: https://user-images.githubusercontent.com/11576465/77761661-ac55b900-7038-11ea-9537-b0ac210c8af5.png
[list2]: https://user-images.githubusercontent.com/11576465/77761888-03f42480-7039-11ea-8a0c-9099d8eb8d54.png
[infobox]: https://user-images.githubusercontent.com/11576465/77762169-63523480-7039-11ea-90a3-f6badb80da20.png
[cbox]: https://user-images.githubusercontent.com/11576465/77764056-4e2ad500-703c-11ea-8838-b0734cdcc988.png
[tabs]: https://user-images.githubusercontent.com/11576465/77806369-c917de00-7084-11ea-91b6-99787c5b1a3f.png

[boxes]: https://squidfunk.github.io/mkdocs-material/extensions/admonition/#admonition
[MkDocs]: https://mkdocs.org

[squidfunk]: https://github.com/squidfunk
[henrywhitaker3]: https://github.com/henrywhitaker3
[facelessuser]: https://github.com/facelessuser

[Material Dark Theme]: https://github.com/henrywhitaker3/mkdocs-material-dark-theme
[pymdown]: https://github.com/facelessuser/pymdown-extensions/

# Docs
This repository is home of the content found on https://docs.purrbot.site  
It currently houses the API-documentation for the various endpoints under https://purrbot.site/api and the official wiki of [\*Purr*][purr].

## Contributions
Any contributions to update and improve the wiki, as well as the API-documentation are welcome, but please follow those basic guidelines:

### Only edit the content in the docs-folder and mkdocs.yml
The content found under the "docs" folder is the place to edit files in. Each file is saved as a markdown (.md) file.  
Only the docs folder (and the mkdocs.yml file if new pages where added or got removed) should be altered.  
At no point should you touch the content of any other file outside the docs-directory.  
Any pull request which alters any file other than the above mentioned ones will be denied.

### Markdown formatting
We use [MkDocs] to turn Markdown files into static HTML pages.  
MkDocs *mostly* follows the basic markdown formatting with some minor exceptions and alterations:

#### Lists
Ordered (numbered) and unordered lists require an empty line in between the start of the list, and any text above it.  
Example:  
```markdown
Some text here.

- This list
- Requires an empty line
- To actually work.

Some more text here.
- This list
- Won't work because
- it misses an empty line
```

Result:  
![list1]

Additionally, if you want to make intended lists, will you need to use 4 spaces compared to the usual 2 or 3 spaces.  
Example:  
```markdown
- Entry 1
    - 2nd Entry

----

- This list
  - Will not have intents
```

Result:  
![list2]

#### Blocks
MkDocs adds a custom markdown formatting which implements Info boxes.  
The syntax is as follows:  
```markdown
!!! info "title here"
    Content goes here.

    - Same markdown rules
        - Apply here too.
```

Result:  
![infobox]

The first argument is the type of box, which can be one of the following options:

- info
- warning
- note
- example
- summary
- tip
- success
- question
- failure
- danger
- bug
- example
- quote

Note that the title is optional and can be omited, which in return uses the default name.  
The boxes also require an empty line before and after its title and content.  
You can read more about this [here][boxes]

#### Collapsable Blocks
Collapsable blocks are provided through the [PyMdown] extension as "Details".   
The syntax is the exact same as with the [normal blocks](#blocks) with the difference, that you use three question marks (`???`) instead of exclamation marks.

Example:  
```markdown
??? info "Closed info box"
    Content goes here.
	
    - Same markdown rules
        - Apply here too.

???+ info "Open info box"
    Content goes here.
	
    - Same markdown rules
        - Apply here too.
```

Result:  
![cbox]

Adding a plus (`+`) after the question marks, will have the box open by default, while it is closed otherwise.  
The same options in terms of type and title are available as with the normal boxes (See above).

#### Tabs
Tabs are provided through the [PyMdown] extension and use thre equal signs (`===`).  
They are quite similar to [normal blocks](#blocks) and [collapsable blocks](#collapsable-blocks) and can even be used in combination with those.

Example:  
```markdown
=== "Tab 1"
    My text here

=== "Tab 2"
    My other text here

!!! info "Box example"
    === "Tab 1"
        My text

    === "Tab 2"
        My other text
```

Result:  
![tabs]

## Credits
A big thank you goes to the following people/groups:
- [MkDocs] for providing the software, to generate documentation.
- [squidfunk] for the MkDocs Material Theme.
- [henrywhitaker3] for the CSS file for the [Material Dark Theme]
- [facelessuser] for the [PyMdown Extensions][pymdown]