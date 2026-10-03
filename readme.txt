Windower4 unofficial addon: Balloon

Balloon displays NPC dialogue in a customizable speech balloon.

Installation
------------

1. Download or clone this repository.
2. Copy the entire `Balloon` folder into your Windower 4 `addons` folder. The
   result should look like this:

       Windower4/addons/Balloon/Balloon.lua
       Windower4/addons/Balloon/ui.lua
       Windower4/addons/Balloon/theme.lua
       Windower4/addons/Balloon/themes/
       Windower4/addons/Balloon/portraits/

   Do not copy only `Balloon.lua`; the themes, portraits, and Lua modules are
   part of the addon.
3. Open the file `Windower4/scripts/init.txt` in a text editor and add this
   exact line:

       lua l balloon

   This makes Windower load Balloon automatically for every character and
   session. You do not need to run a load command manually each time.

For a one-time manual test, start Windower 4, log into a character, and run
the following command instead:

    //lua load balloon

If it does not load, confirm that the folder is exactly named `Balloon` and
that `Balloon.lua` is directly inside it. The addon uses Windower's built-in
Lua libraries and does not require a separate dependency installation. After
loading it, try `//bl help` for the available commands. Use `//bl 2` to show
both the normal log and the balloon, which is the safest mode for first-time
setup.

Commands (Balloon or Bl):

  //bl 0                 Disable future balloons and show the log.
  //bl 1                 Show balloons and hide the log.
  //bl 2                 Show balloons and show the log.
  //bl reset             Reset the balloon position.
  //bl theme <name>      Load a theme from themes/<name>/.
  //bl theme list        List the bundled themes and current theme.
  //bl scale <number>    Scale the balloon, for example 1.5.
  //bl delay <seconds>   Set the promptless close delay; decimals are allowed.
  //bl text_speed <n>    Set animated text speed in whole characters per frame.
  //bl animate           Toggle the animated advancement prompt.
  //bl portrait          Toggle character portraits.
  //bl system            Toggle system-message balloons.
  Edit `settings.xml` and add message-mode numbers to `AdditionalChatModes`
  if your server uses another chat mode for NPC dialogue. Mode 142 is excluded
  by default because it commonly contains fishing and item-acquisition messages.
  //bl move_closes       Toggle closing balloons when the player moves.
  //bl debug <mode>      Enable debug output (off, all, mode, codes, chunk,
                        process, or chars).
  //bl test <name> : <message>
                        Display a test balloon.
  //bl help              Show help.

The balloon can be repositioned with the mouse while it is visible. Mode 0
only disables future balloons; it does not close one already on screen. When the
log is hidden, the game may still advance it by one blank line while waiting
for a button press. Themes select the appropriate English or Japanese font.

Themes are stored under themes/. Portraits are stored under portraits/.
Character-specific balloon backgrounds go under themes/<name>/characters/.
The bundled `dark-fade` theme uses a near-black panel with softly faded edges;
load it with `//bl theme dark-fade`.
The bundled `ffxi-window5` and `ffxi-window5-solid` themes reproduce the newer
FFXI Window 5 dialogue styles. The `-solid` variant uses an opaque background.

See docs/Portrait-Creation.md for portrait guidance. Feedback is welcome via
the GitHub issue tracker:
https://github.com/aldenpark/Balloon
