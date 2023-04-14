# Markdown Syntax

#### Table of Contents
- [Heading](#heading)
- [Paragraph](#paragraphs)
- [Line Breaks](#line-breaks)
- [Emphasis](#emphasis)
- [Blockquotes](#blockquotes)
- [Lists](#lists)
- [CodeBlocks](#code-blocks)
- [Images](#images)
- [Code](#code)
- [Escaping Backticks](#escaping-backticks)
- [Horizontal Rules](#horizontal-rules)
- [Links](#links)
- [URLs and Email Addresses](#urls-and-email-addresses)
- [Formatting Links](#formatting-links)
- [Strikethrough](#strikethrough)
- [Task Lists](#task-lists)

## Heading

`# level 1`

`## level 2`

`### level 3`

`#### level 4`

`##### level 5`

`###### level 6`

### Alternative Syntax

```
Heading level 1
===============
```

```
Heading level 2
---------------
```

#### Best Practice

Do  
`# Here's a Heading`

Don't  
`#Here's a Heading`

---

Do
```
Try to put a blank line before...

# Heading

...and after a heading.
```

Don't
```
Without blank lines, this might not look right.
# Heading
Don't!
```

## Paragraphs

Use a blank line to separate one or more lines of text
```
I really like using Markdown.

I think I'll use it to format all of my documents from now on.
```
#### Best Practice

Do
```
Don't put tabs or spaces in front of your paragraphs.

Keep lines left-aligned like this.
```

Don't
```
  This can result in unexpected formatting problems.

 Don't add tabs or spaces in front of paragraphs.
```

## Line Breaks

```
This is the first line.  
And this is the second line.
```

#### Best Pracitice

Do
```
First line with two spaces after.  
And the next line.

First line with the HTML tag after.<br>
And the next line.
Don't
```

Don't
```
First line with a backslash after.\
And the next line.

First line with nothing after.
And the next line.
```

## Emphasis

### Bold

`I just love **bold text**.`

`I just love __bold text__.`

`Love**is**bold`

#### Best Practice

Do
```
Love**is**bold
```

Don't
```
Love__is__bold
```

### Italic

`Italicized text is the *cat's meow*.`

`Italicized text is the _cat's meow_.`

`A*cat*meow`

#### Best Practice

Do
```
A*cat*meow
```

Don't
```
A_cat_meow
```

### Bold and Italic

`This text is ***really important***.`

`This text is ___really important___.`

`This text is __*really important*__.`

`This text is **_really important_**.`

`This is really***very***important text.`

#### Best Practice

Do
```
This is really***very***important text.
```

Don't
```
This is really___very___important text.
```

## Blockquotes

Add a `>` in front of a paragraph.
```
> Blockquotes
```

Output
> Blockquotes

### Blockquotes with Multiple Paragraphs

Add a `>` on the blank lines between the paragraphs.
```
> line 1
>
> line 2
```

Output
> line 1
>
> line 2

### Nested Blockquotes
Add a `>>` in fron of the paragraph
```
> line 1
>
>> line 2 (nested)
```

Output
> line 1
>
>> line 2 (nested)

### Blockquotes with Other Elements

```
> #### line 1
>
> - sub line 1
> - sub line 2
>
> *line 4* **line 4**
```

Output
> #### line 1
>
> - sub line 1
> - sub line 2
>
> *line 4* **line 4**

#### Best Practice

Do
```
Try to put a blank line before...

> This is a blockquote

...and after a blockquote.
```

Don't
```
Without blank lines, this might not look right.
> This is a blockquote
Don't do this!
```

## Lists

### Ordered Lists

1. First
2. Second
3. Third

#### Nested

1. First
2. Second
    1. Indented
3. Fourth

#### Best Practice

Do
```
1. First
2. Second
```

Don't
```
1) First
2) Second
```

### Unordered Lists

`-`, `*`, `+`
- First
- Second

#### Nested

- First
- Second
    - Indented

#### Best Practice

Do
```
- First
- Second
- Third
```

Don't
```
+ First
* Second
- Third
```

### Adding Elements in lists

#### Paragraph

```
* This is the first list item.
* Here's the second list item.  
    I need to add another paragraph below the second list item.
* And here's the third list item.
```

Output
* This is the first list item.
* Here's the second list item.  
    I need to add another paragraph below the second list item.
* And here's the third list item.

#### Blockquotes

```
* This is the first list item.
* Here's the second list item.  
    > I need to add another paragraph below the second list item.
* And here's the third list item.
```

Output
* This is the first list item.
* Here's the second list item.  
    > I need to add another paragraph below the second list item.
* And here's the third list item.

## Code Blocks

```
1. Open the file.
2. Find the following code block on line 21:

        <html>
          <head>
            <title>Test</title>
          </head>

3. Update the title to match the name of your website.
```

Output
1. Open the file.
2. Find the following code block on line 21:

        <html>
          <head>
            <title>Test</title>
          </head>

3. Update the title to match the name of your website.

## Images

```
1. Open the file containing the Linux mascot.
2. Marvel at its beauty.
    ![Tux, the Linux mascot](/assets/images/tux.png)
3. Close the file.
```

Output
1. Open the file containing the Linux mascot.
2. Marvel at its beauty.
    ![Tux, the Linux mascot](/assets/images/tux.png)
3. Close the file.

## Code

```
At the command prompt, type `nano`.
```

Output  
At the command prompt, type `nano`.


## Escaping Backticks

```
``Use `code` in your Markdown file.``
```

Output  
``Use `code` in your Markdown file.``

## Horizontal Rules

```
***

---

__________________
```

Output
***

---

__________________

### Best Practice

Do
```
Try to put a blank line before...

---

...and after a horizontal rule.
```

Don't
```
Without blank lines, this would be a heading.
---
Don't do this!
```

## Links

```
My favorite search engine is [Duck Duck Go](https://duckduckgo.com)
```

Output
My favorite search engine is [Duck Duck Go](https://duckduckgo.com)

### Adding Titles

Appear as a tooltip
```
My favorite search engine is [Duck Duck Go](https://duckduckgo.com "The best search engine for privacy")
```

Output
My favorite search engine is [Duck Duck Go](https://duckduckgo.com "The best search engine for privacy")

## URLs and Email Addresses

```
<https://www.markdownguide.org>
<fake@example.com>
```

Output  
<https://www.markdownguide.org>  
<fake@example.com>

## Formatting Links

```
I love supporting the **[EFF](https://eff.org)**.  
This is the *[Markdown Guide](https://www.markdownguide.org)*.  
See the section on [`code`](#code).
```

Output  
I love supporting the **[EFF](https://eff.org)**.  
This is the *[Markdown Guide](https://www.markdownguide.org)*.  
See the section on [`code`](#code).

## Strikethrough

```
~~The world is flat.~~ We now know that the world is round.
```

Output  
~~The world is flat.~~ We now know that the world is round.

## Task Lists

```
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media
```

Output
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media


## Automatic URL Linking

http://www.example.com

Disabling Automatic URL Linking
```
`http://www.example.com`
```

Output  
`http://www.example.com`
