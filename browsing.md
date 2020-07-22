# Browsing

The Browse screen allows you to search through your cards and notes, and edit
them. It is opened by clicking on _Browse_ in the main window, or by pressing
_b_ on your keyboard. It is comprised of three sections: the _sidebar_ on the
left, the _card list_ on the top right, and the _current note_ on the bottom
right. By positioning the mouse between two sections, it is possible to click
and drag to expand one section and shrink another.

## Sidebar

The sidebar on the left allows quick access to common search terms. Clicking
on an item will search for it.

You can hold down Ctrl (Command on a Mac) while clicking in order to append
the clicked item to the current search with an AND condition, instead of
starting a new search. If you wanted to show learning cards that were
also in the German deck for instance, you could click on "Learning",
then Ctrl+click on "German".

You can hold down Shift to create an OR search instead of an AND. For
example, you could click one deck, then shift-click another to show
cards from either of the decks in the same view.

You can hold down Alt (Option on a Mac) in order to reverse the search
(prepend a _-_) – for instance, to show all cards in a current deck that
do _not_ have a certain tag. Alt/option can be combined with either Ctrl
or Shift (e.g., Ctrl-Alt-clicking will result in adding a new search
term that is negated).

To remove tags that are not used by any notes, use Tools&gt;Check
Database from the main window.

## Searching

Above the card list is a search box. You can type in various things
there to search for cards. For information on the search syntax, please
see the [searching section](searching.md).

## Card List

The card list displays cards that match the current search.

The columns are configurable: right click on one (or ctrl+click on a
Mac) to choose which columns you’d like to see. You can drag columns to
reorder them. Clicking on a column will sort by that column; click again
to reverse the sort order. Not all columns can be sorted on.

The due column behaves differently for different types of cards. New
cards show a number rather than a due date, which indicates the order
the new cards will be presented in. Cards in (re)learning and reviews
will both show a due date, but when sorting they are first grouped by
type and then sorted by date.

The "edited" and "changed" columns sound the same but track different
things. "Edited" tracks the last time changes were made to the _note_
(e.g., when the content of a field was edited), while "changed" tracks
the last time changes were made to the _card_ (e.g., when you reviewed
the card and the review history and interval were updated).

When you click on a card, its note will be shown in the bottom section.
If you drag the mouse or hold ctrl or command to select multiple cards,
the editor will be temporarily hidden. Various operations (such as
changing the deck) can operate on multiple cards at once.

The background colour will change depending on the card. Marked cards
are a shade of purple. Suspended cards are a shade of yellow. For more
information about marked and suspended cards, please see [editing and
more](studying.md).

One of the available columns is called the _sort field_. Anki allows you
to choose one field from each type of note to be used for sorting. You
can change the sort field by clicking on "Fields…​" in the current note
section.

The question and answer columns display what you’d see on the question
and answer while reviewing, except the answer column will strip the
question part for clarity. You can also choose a [custom
format](templates/styling.md#browser-appearance) in the card type editor instead of showing
what would be seen during review.

## Current Note

The bottom right area displays the currently selected card’s note. For
more information about cards and notes, please see [the
basics](getting-started.md). For more information on formatting buttons, please see
[editing](editing.md).

You can see a preview of what the currently selected card would look
like when reviewing by clicking the "preview" button next to the search
box. Note that this will not display any type answer fields on your
cards, which makes it easier to preview cards quickly.

## Menu

Up the top of the window/screen is the menu. You can also access it quickly by
right clicking on command+clicking on the card list area.

_Info_ shows various information about the currently selected card,
including its review history. For more information, see the
[statistics](stats.md) section.

_Mark_ and _Suspend_ are documented in [editing and more](studying.md).

_Change Deck_ allows you to move cards to a different deck. Cards can be
placed in different decks, so if you want to move all cards in a note,
you should first use Edit &gt; Select Notes.

_Add Tags_ and _Remove Tags_ allow you to add or remove tags from notes
in bulk. To remove unused tags from the list on the left, use
Tools&gt;Check Database from the main window.

_Delete_ removes the selected card(s) and their notes. It is not
possible to remove individual cards, as individual cards are controlled
by the [templates](templates/intro.md).

## Find and Replace

This option (Notes→Find and Replace…​) allows you to replace text in the
notes you have selected. The regular expression option allows you to
perform complex replacements. For example, given the following text in a
field:

    <img src="pic.jpg" />

Searching for:

    <img src="(.+?)" />

and on Anki 2.1.28, replacing with:

    ${1}

on older Anki versions, replacing with:

    \1

Will change the card to:

    pic.jpg

A full discussion on regular expressions is outside the scope of this
document. There are a number of tutorials available on the web. For a syntax guide, on Anki 2.1.28+ please see <https://docs.rs/regex/1.3.9/regex/#syntax>. For older Anki versions, please see <http://docs.python.org/library/re.html>.

## Finding Duplicates

You can use the Notes→Find Duplicates option to search for notes that
have the same content. When you open the window, Anki will look at all
of your note types and present a list of all possible fields. If you
want to look for duplicates in the "Back" field, you’d select it from
the list and then click "Search".

Unlike the check that happens when you add cards manually, the duplicate
finding feature is not limited to a single note type. This means that by
default, it will search in all note types that have the field you
provided.

The _optional limit_ text box allows you to narrow down where Anki will
look for duplicates. If you only want to search for duplicates in the
"French Vocab" and "French Verbs" note types, you would enter:

    note:'french vocab' or note:'french verbs'

Or you might want to look only for duplicates in a particular deck, so
you could use:

    deck:'myDeck'

The search syntax is the same as used when searching in the browser.
Please see the [searching](searching.md) section for more information.

You can click one of the links in the search results list to display the
duplicate notes in that set. If the search brings up a large number of
duplicates, you may wish to instead click the Tag Duplicates button,
which will tag all matching notes with "duplicate." You can then search
for this tag in the browser and handle them all from the same screen.

## Other Menu Items

Some other items in the menus:

_Reschedule_ allows you to move cards to the end of the new card queue,
or reschedule them as a review card on a given date. The second option
is useful if you have imported already-learnt material, and you want to
start it off with higher initial intervals. For example, choosing 60 and
90 will give all the imported cards an initial interval of 2 to 3
months.

The card’s revision history is not cleared when rescheduling:
rescheduling changes the current state of a card, but not its history.
If you want to hide the history, you will need to export your notes as a
text file, delete the notes, and then import the text file again,
creating new notes.

_Reposition_ allows you to change the order new cards will appear in.
You can find out the existing positions by enabling the _due_ column, as
described in the card list section above. If you run the reposition
command when multiple cards are selected, it will apply increasing
numbers to each card in turn. By default the number increases by one for
each card, but this can be adjusted by changing the "step" setting. The
_Shift position of existing cards_ option allows you to insert cards
between currently existing ones, pushing the currently existing ones
apart. For instance, if you have five cards and you want to move 3, 4,
and 5 between 1 and 2, selecting this setting would cause the cards to
end up in the order 1, 3, 4, 5, 2. By contrast, if you turn this option
off, 2 and 3 will get the same position number (and it will thus be
random which one comes up first).

_Change Note Type_ allows you to convert the selected notes from one
type to another. For example, imagine you have a Russian note type and a
Computer note type, and you accidentally added some computer-related
text into a Russian note. You can use this option to fix that mistake.
The scheduling of cards is not affected.

_Select Notes_ takes the currently selected cards, finds their notes,
and then selects all cards of those notes. If your notes have only one
card, this does nothing.

The _Go_ menu exists to provide keyboard shortcuts to jump to various
parts of the browser, and to go up and down the card list.
