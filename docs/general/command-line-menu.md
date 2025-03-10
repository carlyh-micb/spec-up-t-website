---
sidebar_position: 26
---

# Command Line Menu

You don't have to be a command-line wizard to use Spec-Up-T. There's even a menu, so all you have to do is type in a number, which makes a difference, right?

Still, it can be confusing. And if you're used to a regular application you control with your mouse, it takes some getting used to.

## Start command line menu

:::info
Currently, the menu is only tested on MacOs and has not been tested on Windows OS.
:::

Assuming you already [installed](./installation.md) Spec-Up-T, here you find further instructions.

To start, run this command in the terminal:

```bash
npm run menu
```

You will now see this menu:

```bash
Please choose one of the following options:

   [0] Add content
   [1] Render specification
   [2] Export to PDF
   [3] Update new xrefs
   [4] Update all xrefs
   [5] Add, remove or view xref source
   [6] Configure
   [7] Open documentation website
   [8] Freeze specification
   [Q] Quit

   An xref is a reference to another repository.

   Enter your choice:
```

These menu options act as shortcuts to the below commands, such as `npm run render` and others. You can choose between using the menu or entering the direct commands yourself.

### `[0] Add content`

Gives info on how to add content.

### `[1] Render specification`

**Creates the specification, an index.html, in the `docs` directory, as specified in the `specs.json` file.**

To view the `index.html` file, you can:

- Open it via `file:///` in your file manager or
- Access it via HTTP by placing it on a web server.

The easiest way is to double-click the file in your file manager, which should open it in your browser.

By the way, there are **three** modes for rendering the specification:

| Command | Behavior |
|---|---|
| **`npm run edit`** | Renders the site and watches for changes, re-rendering automatically when you save a file. |
| **`npm run render`** | Renders the site once without watching for changes. |
| **`npm run dev`** | Enables debugging features. |

### `[2] Export to PDF`

**Creates a PDF. The PDF will be created in the same directory as the `index.html` file.**

### `[3] Update new xrefs`

**Creates all newly added “xref”'s (external references).**

Also runs [1].

`xrefs` are references to external glossaries (specifications). Each `xref` is checked against a local data collection to see if a reference exists, maintaining an external term's original version.

The xrefs are not always automatically looked up when you choose option [1] because every lookup invokes the GitHub API, and you are faced with a limit at some point. You then have to wait for the limitation to be lifted again. Without a unique token, you run into the limit pretty quickly. Hence this option to take it slow. By the way, you can create a token for free at GitHub.

### `[4] Update all xrefs`

**(re)creates all “xref” (external references).**

If you delete an xref, it is also deleted from the system's bookkeeping.

### `[5] Add, remove or view xref source`

**See an overview of all external references, or add or delete**

### `[6] Configure`

Configure a new installation.

### `[7] Open documentation website`

This command will redirect to the documentation website (the site you are reading right now).

### `[8] Freeze specification`

**Makes a copy of the `index.html` file and adds a version number to the file name.**

Example: `index-v1.html`, `index-v2.html` etc. These files are placed in the same folder as the `index.html` but in a subfolder called `versions`.

### `[Q] Quit`

This command will take you out of the menu.
