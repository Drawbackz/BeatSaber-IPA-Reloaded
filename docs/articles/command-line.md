# The Command Line

BSIPA has 2 command lines: the installer, and the game.

Their documentation is below.

# [The Installer (`IPA.exe`)](#tab/installer)

The installer has quite a few options, which are documented inline with the `-h` or `--help` flag.

This is what it currently looks like:

[!code[IPA command line](_ipa_command_line.txt "the result of IPA.exe -h")]

# [The Game](#tab/game)

The game *also* gets quite a few command line options, though there isn't anything as convenient as a help page for them.

Here's a quick list of what they are and what they do.

- `--debug`

  > Enables the loading of debug information in Mono. The debugging information must be in the portable PDB format,
  > in the same location as the DLL that it's for.
  >
  > This option also forces BSIPA to show all debug messages in the console, as well as where they were called.
  >
  > This overrides the config settings `Debug.ShowDebug` and `Debug.ShowCallSource`.
  >

- `--mono-debug`

  > Enables the built-in Mono soft debugger engine.
  >
  > By default, it acts as a client, and requires that there be a soft
  > debugger server running on port 10000 on `localhost`.
  >
  > Implies `--debug`.
  >

- `--server`

  > Does nothing on its own.
  >
  > When paired with `--mono-debug`, this option makes the Mono soft debugger act in server mode. It begins listening on
  > port 10000 on any address, and will pause startup (with no window) until a debugger is connected. I reccommend using
  > SDB, but that is a command line debugger and a lot of people don't care for those.
  >

- `--no-yeet`

  > Disables mod yeeting.
  >
  > By default, whenever BSIPA detects that the game is now running a newer version than previous runs, it will move all
  > mods to another folder and not load them. (They still get checked for updates though.) When this is enabled, that
  > behaviour is disabled.
  >
  > Overrides the config setting `YeetMods`.
  >

- `--condense-logs`

  > Reduces the number of log files BSIPA will output for a given session.
  >
  > By default, BSIPA will create a subfolder in the `Logs` folder for each mod sublog, as well as each mod. This disables
  > that behaviour, and restricts it to only create a global log and mod logs.
  >
  > Overrides the config setting `Debug.CondenseModLogs`.
  >
- `--no-updates`

  > Disables automatic updating.
  >
  > By default, BSIPA will check [BeatMods](http://beatmods.com) for all of the loaded mods to see if there is a new version
  > avaliable. If there is, it will be downloaded and installed on the next run. This flag disables that behaviour.
  >
  > Overrides the config settings `Updates.AutoCheckUpdates` and `Updates.AutoUpdate`.
  >
  