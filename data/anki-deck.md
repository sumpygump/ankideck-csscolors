# Anki Deck Definition for csscolors

This file provides details on creating the Csscolors Deck from scratch.

Steps to create this deck from scratch:

1. Create new note type (this is like a new category of notes for this deck)
2. Add fields
3. Edit cards
4. Create new deck + Import data

## Create new note type

In Anki, under Tools | Manage Note Types... create a new note type by clicking
the "Add" button. The option is to clone the new note type from another type.
You can select "Add:Basic" and press "OK". Then name it "CSS named colors".

Note Types

 - "CSS named colors"

## Add fields

With the new note type highlighted in the Manage Note Types window, click the
button "Fields..."

Edit the fields by using the button "Rename" for the first two and then "Add"
to create the rest. The fields should be as follows. (This matches what is in
the CSV file that contains the data for the cards).

The fields should be in this order so, "1: Hex", "2: Name", etc.

Fields

 - Hex
 - Name
 - Rvalue
 - Gvalue
 - Bvalue

## Cards for Note Type "CSS named colors"

The cards represent the physical display of the front and back of a card (what
you will be quizzed on).

Edit the cards by clicking the "Cards..." button on the Manage Note Types
window with the correct note type selected.

From there, use the following snippets to edit the text of the front template,
back template and styling.

Front template:

```
<div class="contain">
    <div class="color-dot" style="background-color:{{Hex}}"></div>
    <div class="desc">{{Hex}}</div>
    <div class="rgb-graph">
        <span class="bar"><span class="bar-r" style="height:{{ Rvalue }}%"></span></span>
        <span class="bar"><span class="bar-g" style="height:{{ Gvalue }}%"></span></span>
        <span class="bar"><span class="bar-b" style="height:{{ Bvalue }}%"></span></span>
    </div>
</div>
```

Back Template:

```
{{FrontSide}}

<hr id=answer>

<span class="name">{{Name}}</span>
```

Styling:

```
.card {
    font-family: arial;
    font-size: 30px;
    text-align: center;
    color: black;
    max-width: 1024px;
    overflow-y: scroll;
    position: relative;
    height: 100%;
    margin: 0 auto;
    padding: 0;
}
.contain {
    margin: 16px;
    height: 80%;
}

.color-dot {
    width: 200px;
    height: 200px;
    margin: 0 auto 20px auto;
    border-radius: 50%;
}

.rgb-graph {
    height: 16px;
    border: 1px solid #dcdcdc;
    width: 14px;
    display: flex;
    padding: 1px;
    margin: 0 auto;
}
.rgb-graph .bar {
    display: flex;
    align-items: flex-end;
    height: 16px;
    width: 4px;
    margin-right: 1px;
}
.rgb-graph .bar-r {
    background-color: red;
    width: 4px;
    display: block;
}
.rgb-graph .bar-g {
    background-color: #00a900;
    width: 4px;
    display: block;
}
.rgb-graph .bar-b {
    background-color: blue;
    width: 4px;
    display: block;
}
```

## Reverse cards

To create the reverse card, from the Cards window, click "Options" on the far
right and choose "Add Card Type...", it will create a copy of the card. Click
the button "Flip" at the bottom to reverse the front and back card template
definitions.

Then click Save to save everything.

## Import data

From the main Anki window, click the button "Create Deck". Name the deck "CSS
Colors"

From the main Anki menu, choose File | "Import...".

Select the CSV file included in this repository `csscolors.anki.csv`.

In the import window be sure to select the correct Type: "CSS named colors" and
the correct deck.

Now you will have all the cards ready to learn.
