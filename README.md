# Web Console for Universal Devices IoX

A browser-based console for a Polisy or eisy running IoX.

## Notable features

**Programs**

- Adding, removing and moving programs takes effect without a save.
- Save Changes and Undo Changes act only on the programs you pick.
- A dot marks a program with unsaved edits. A folder holding one gets a hollow
  ring; a folder edited itself gets a solid dot.
- Drag lines to reorder them, or use Move Line Up and Down.
- Live status beside any line that names a device, and it can be turned off.

**Find and Replace**

- Every program containing a device is listed together, and each can be expanded
  to the matching line.
- Replacing stages the program and turns the line amber, so you can see the
  change before it is written.
- Nothing is written until you save, and you choose which programs to save.
- Nodes deleted from the system are detected, including where they survive only
  in a program's comments.

**Devices and scenes**

- Live status to the right of each name in the list.
- Z-Wave configuration parameters show names and descriptions, not bare
  numbers.
- Drag a device onto the network root to take it out of a folder.
- Add a device to a scene from a pulldown in the scene itself.
- Right-click a device in a scene for "Go to this device in the tree", which
  opens every folder above it and scrolls to it.
- Replacing an Insteon device handles one sitting in a folder: it is moved to
  the root, replaced, and put back where it was.
- The device links table switches between the IoX links and the device's own,
  with a Compare button, and shows the description.

**Elsewhere**

- A dark interface, with icons drawn for it.
- Collapsing the tree leaves the network root and My Programs open.

## Back your controller up first

This writes to real hardware, and some mistakes cannot be undone through the
API. Take a backup with whichever tool you already use, and keep the file
somewhere other than the box. There is no warranty of any kind.

## Download

The Windows and macOS builds are under [Releases](../../releases).

Windows includes everything it needs. macOS uses the Node already on the Mac;
if there is none, https://nodejs.org or `brew install node`.

## Running it

Unzip anywhere and open the file inside:

    Windows   Web Console for Universal Devices IoX.bat
    macOS     Web Console for Universal Devices IoX.command

Your browser opens at http://localhost:3000, where you choose a device and sign
in. It stops on its own about a second after you close the last page.

**Windows** may show "Windows protected your PC" the first time. Choose More
info, then Run anyway.

**macOS** may refuse to open the .command the first time. Right-click it and
choose Open.

## Not a Universal Devices product

A third-party companion tool. Not affiliated with, endorsed by, or sponsored by
Universal Devices, Inc.

Polisy, eisy and IoX are trademarks of Universal Devices, Inc., used here only
to say which hardware this talks to.

## Licence

[PolyForm Strict 1.0.0](https://polyformproject.org/licenses/strict/1.0.0). Use
it for any noncommercial purpose. Do not redistribute it, and do not distribute
changed versions or new works based on it. For anything else, ask.

Full terms, and what the licence does not cover, are in [LICENSE](LICENSE).
Node.js and the zwave-js device database travel with the builds under their own
MIT licences, each carrying its notice beside the file it covers.

---

Current build: `2026-09-08 05:44  7f9f611`
