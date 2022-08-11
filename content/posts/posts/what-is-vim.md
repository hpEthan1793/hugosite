---
title: "What Is Vim"
date: 2021-01-15T20:21:33+02:00
draft: false
toc: false
images:
tags:
  - linux
  - vim
  - neovim
---

Vim is the editor of choice for many developers and power users. It’s a text editor based on the old vi editor written by Bill Joy in the 1970s for a version of UNIX. It inherits the key bindings of vi, but also adds a great deal of functionality and extensibility that are missing from the original vi.<br />

Even though Vim isn’t as easy to use initially as standard GUI text editors like Gedit or word processors like OpenOffice.org’s Writer, over a longer term you can become more productive using Vim. If you’re a touch-typist, you’ll find that your speed will improve even more with Vim because your hands rarely need to leave the “home” keys–and you’ll only need to use the mouse if you choose to do so. <br />

If you’re a programmer or working with structured markup languages like HTML, LaTeX, DocBook, etc., Vim is the bee’s knees. It offers a number of features that I’ll cover in later installments that make working with programming and markup languages much easier. <br />

### The Modes

Some people disagree on how many modes Vim actually has. I’m going to define three: insert mode, command mode, and last-line mode. Let’s start with the default mode you’ll see when you start up Vim–command mode. <br />

When you run vim filename to edit a file, Vim starts out in command mode. This means that all the alphanumeric keys are bound to commands, rather than inserting those characters. Typing j won’t insert the character “j”–it will move the cursor down one line. Typing dd will delete an entire line, rather than inserting “dd.” <br />

To enter the insert mode, type i (for “insert”) and now the keys will behave as you’d expect. You can type normally until you want to make a correction, save the file, or perform another operation that’s reserved for command mode or last-line mode. To get out of insert mode, hit the Escape key. <br />

Once you press Escape, you’re in command mode again. What if you’d like to save your file or search through your document? No problem, press : and Vim will switch to last-line mode. Vim is now waiting for you to enter a command like :w to write the file or :q to exit the editor. <br />

### Movement in Vim

The first thing you’ll want to learn is how to move around a file. When you’re in command mode, you’ll want to remember the following keys and what they do:

<table class="table table-dark table-responsive">
  <thead>
    <tr>
      <th scope="col">Key</th>
      <th scope="col">Function</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>h</td>
      <td>Moves the cursor one character to the left</td>
    </tr>
    <tr>
      <td>j</td>
      <td>Moves the cursor one line down</td>
    </tr>
    <tr>
      <td>k</td>
      <td>Moves the cursor one line up</td>
    </tr>
    <tr>
      <td>l</td>
      <td>Moves the curosr one character to the right</td>
    </tr>
    <tr>
      <td>0</td>
      <td>Moves the cursor to the beginning of the line</td>
    </tr>
    <tr>
      <td>$</td>
      <td>Moves the cursor to the end of the line</td>
    </tr>
    <tr>
      <td>w</td>
      <td>Moves the cursor forward by one word</td>
    </tr>
    <tr>
      <td>b</td>
      <td>Moves the cursor backward by one word</td>
    </tr>
    <tr>
      <td>G</td>
      <td>Moves to the beginning of the file</td>
    </tr>
    <tr>
      <td>gg</td>
      <td>Moves to the end of the file</td>
    </tr>
  </tbody>
</table>

### Editing

Now that you know how to move around a bit, let’s try editing. Move the cursor to the beginning of a word. Now type x. What happened? You should have deleted the character that the cursor was on. Want to undo it? No problem. Type u (for undo) and it will be restored. <br />

Want to delete an entire word? Move your cursor to the beginning of a word again. Use dw. Note that this will only delete the word from the cursor on–so if you have the cursor in the middle of a word, it will only delete from that point on. Again, u will undo it. Note that Vim has multiple levels of undo, so you can undo the change before that and the change before that, etc. <br />

Want to undo your undo? Hit Ctrl-r. That will redo your last undo. <br />

Again, here’s a longer list of the commands you’ll definitely want to know starting out: <br />

<table class="table table-dark table-responsive">
  <thead>
    <tr>
      <th scope="col">Key</th>
      <th scope="col">Function</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>d</td>
      <td>Starts the delete operation</td>
    </tr>
    <tr>
      <td>dw</td>
      <td>Deletes a single word</td>
    </tr>
    <tr>
      <td>d0</td>
      <td>Deletes to the beginning of the line</td>
    </tr>
    <tr>
      <td>d$</td>
      <td>Deletes to the end of the line</td>
    </tr>
    <tr>
      <td>dd</td>
      <td>Deletes the entire line</td>
    </tr>
    <tr>
      <td>dgg</td>
      <td>Delete to the beginning of the file</td>
    </tr>
    <tr>
      <td>dG</td>
      <td>Deletes to the end of the file</td>
    </tr>
    <tr>
      <td>u</td>
      <td>Undo the last operation</td>
    </tr>
    <tr>
      <td>Ctrl-r</td>
      <td>Redo last edit</td>
    </tr>
  </tbody>
</table>

### Search

Now that you know how to enter text, make some changes and so forth, it’s time to learn how to use search and replace in Vim. It’s really pretty easy. If you want to search through the document from command mode, use / followed by the text you want to search for. So, if I want to search for “bunny” I can enter / and then bunny and hit enter. <br />

If I want to find it again, I hit n. If I want to look for a previous instance of the text, I’ll use N instead, which will search the opposite direction through the document. <br />

Want to reverse the direction of your search? Use ? instead of / and Vim will move backwards through the document. Using n and N as above will reverse the direction of the search. <br />

<table class="table table-dark table-responsive">
  <thead>
    <tr>
      <th scope="col">Key</th>
      <th scope="col">Function</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>/text</td>
      <td>Search for text in the file going forward</td>
    </tr>
    <tr>
      <td>n</td>
      <td>Move the cursor to the next instance of the text from the last search</td>
    </tr>
    <tr>
      <td>N</td>
      <td>Move the cursor to the previous instance of the text from the last search</td>
    </tr>
    <tr>
      <td>?text</td>
      <td>Search for text in the document going backwards</td>
    </tr>
  </tbody>
</table>

### Copy and Paste

You’ve already learned to delete text. The last text that you’ve deleted is stored in the buffer ready to be pasted back into the document. So if you’ve run dd and deleted an entire line, you can now hit p or P to paste it back into the document. This goes for single lines, multiple lines, and even entire documents. <br />

Want to select text? In command mode, hit V and you’ll be able to move the cursor using the arrow keys or the standard movement keys (h, k, j, l) to highlight text. This is pretty easy, but can be slow. Want to copy entire lines at a time? Use V instead of v and you’ll highlight entire lines at a time. Again, you can use the movement keys to highlight additional lines. <br />

Vim has a really cool trick as well. You can highlight in columns. Use Ctrl-v and you’ll be able to highlight a column instead of an entire line. This can be useful when working with some text files that have data in columns and you want to select an entire column, but not an entire line. <br />

When you’ve highlighted what you want, hit y and it will “yank” the text into the buffer to be pasted later. So a usual paste operation might look like this: <br />

Hit v to highlight some text. Then hit y to yank it into the buffer. Then move the cursor where you want it, and use p in command mode. There you go–you’ve just pasted some text! <br />

The commands you most need to start out: <br />

<table class="table table-dark table-responsive">
  <thead>
    <tr>
      <th scope="col">Key</th>
      <th scope="col">Function</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>v</td>
      <td>Highlight one character at a time</td>
    </tr>
    <tr>
      <td>V</td>
      <td>Highlight one line at a time</td>
    </tr>
    <tr>
      <td>Ctrl-v</td>
      <td>Highlight by columns</td>
    </tr>
    <tr>
      <td>p</td>
      <td>Paste text after the current line</td>
    </tr>
    <tr>
      <td>P</td>
      <td>Paste text before the current line</td>
    </tr>
    <tr>
      <td>y</td>
      <td>Yank (copy) text into the copy buffer</td>
    </tr>
  </tbody>
</table>

### Save and Quit

If you’re in insert mode, hit Escape. Then enter : and you’ll see a line at the bottom of the screen with a cursor ready to take input. <br />

To write the file you’re editing, enter w. (So, you’ll have :w.) That will write the file to the existing filename. If you don’t have a filename or want to write out to a different filename, use :w filename. <br />

To quit Vim after you’ve finished, hit :q. Since Vim is your friend, it won’t just pop out on you if you haven’t saved your file. It will say “no write since last change,” and suggest that you add ! to override. <br />

If you really want to quit, go ahead and use :q! to leave without being nagged.You can also exit Vim using ZZ, which will save and quit the file. Again, all this might sound a bit complex, but it really isn’t. It’s a bunch of smaller things to learn that when you add them all up, make for a very powerful package. <br />

For now that should be enough to get you started. Don’t fret, though. We’ll go through more Vim usage next week, and keep working on Vim until you’re an expert. <br />
