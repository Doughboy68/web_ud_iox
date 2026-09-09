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

Use whichever tool you already do, and keep the file somewhere other than the
box. It has been tested against real hardware without incident, but no amount
of testing covers every setup. There is no warranty of any kind.

## Download

The Windows and macOS builds are under [Releases](../../releases).

Windows includes everything it needs. macOS uses the Node already on the Mac;
if there is none, https://nodejs.org or `brew install node`.

## Running it

Expand it anywhere and open the file inside:

    Windows   Web Console for Universal Devices IoX.bat
    macOS     Web Console for Universal Devices IoX.command

Your browser opens at http://localhost:3000, where you choose a device and sign
in. It stops on its own about a second after you close the last page.

**Windows** may show "Windows protected your PC" the first time. Choose More
info, then Run anyway.

**macOS** will not run software whose developer it cannot check, and this is not
signed. The first time, double-click it and press Done at the refusal, then open
System Settings, go to Privacy & Security, scroll to the message naming the file
and press Open Anyway. Double-click it again and it opens.

## Install it on the controller

It can copy itself into `/USER/WEB/iox` on the controller, so you can use it
from any browser on your network with nothing running on a computer. The button
is in the Status window, under "On the device".

Afterwards it is at `http://<your-controller>:8080/USER/WEB/iox/index.htm`.

What to know first:

- Tested on a Polisy. It is not offered on other models; setting
  `IOX_INSTALL_ANY=1` overrides that, and then you are the first to find out
  whether it works.
- Status is polled every two seconds rather than arriving live: there is no
  event stream a browser can read from the controller. Commands are still sent
  immediately and status refreshes straight after one, but it feels a beat
  behind, and progress during a long operation such as adding a device is not
  shown as it happens.
- Nothing outside `/USER/WEB/iox` is written, and every file is read back and
  compared byte for byte after it is written.
- The controller serves those files with an hour of cache, so hard-reload the
  page after installing or updating or you may see the previous copy.
- Removing it deletes the files it installed and leaves the empty folder.
- The installed copy cannot install, update or remove itself, and cannot
  rebuild the Z-Wave or product-name tables. Run the downloaded copy for those.

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

Current build: `2026-09-08 09:00  20060bd`
