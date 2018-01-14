# markdown-to-anki

A simple little tool to convert specifically formatted markdown to a format that
can be imported by anki into flash cards.

## Usage

```
# install
npm i -g markdown-to-anki

# print formatted cards to stdout
markdown-to-anki flashcards.md

# save cards as a file
markdown-to-anki flashcards.md > flashcards.txt
# then go open flashcards.txt with your anki app
```

When importing the cards, make sure the checkbox for "Allow HTML in fields" is
checked.

## Markdown Format

This tool expects your markdown to be specifically formatted, and deviations
from this format could cause it to break in unexpected ways, or produce "bad"
output.

Each card has a front and a back. The front and back are separated by a newline,
three dashes, and another newline:

```

---

```

And each card is separated by newlines surrounding three equals signs:

```

===

```

The front or back of a card can have any markdown you wish. This tool uses
[marked][1] to parse the markdown and generate html. Here's an example:

[1]: https://github.com/chjj/marked

```

Here is a question for the first card:

---

And here is the answer

===

This is a question on the second card

---

and yet another answer

===

Here's a card

with multiple paragraphs

---

- and
- a
- bulleted
- list

```
