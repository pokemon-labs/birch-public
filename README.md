# pilot

pilot is a Pokémon Showdown bot that plays Gen 3 OU (ADV OU). It brings its
own teams, 134 of them, and picks one at random for each game.

It's meant for people who run their own Showdown server. Start it on the same
computer as the server, and players on that server can challenge it or meet
it on the ladder.

## Download

From the latest release on the right:

| | Most PCs (Intel or AMD) | ARM (Snapdragon laptops, Raspberry Pi 4 and 5, ARM servers) |
|---|---|---|
| **Windows** (10 or 11) | `pilot-windows-x86_64.exe` | `pilot-windows-arm64.exe` |
| **Linux** | `pilot-linux-x86_64` | `pilot-linux-arm64` |

It's a single file with nothing to install. On Linux, make it runnable first,
for example `chmod +x pilot-linux-x86_64`.

## Give it an account

Make a text file, for example `login.txt`. Put the bot's username on the
first line and its password on the second:

```
MyBotName
hunter2
```

If the name isn't registered, leave the second line out.

## Run it

Open a terminal (on Windows, Command Prompt or PowerShell) in the folder with
the program. Then run one of these:

```
pilot --login login.txt accept
```
Accepts Gen 3 OU challenges sent to the bot's name and declines other
formats. It plays up to three games at once.

```
pilot --login login.txt ladder
```
Plays your server's Gen 3 OU ladder, one game after another.

On Windows, type the .exe's name (for example `pilot-windows-x86_64.exe`) where
these say `pilot`. On Linux, type `./` and the file's name, for example
`./pilot-linux-x86_64`.

pilot looks for your server on port 8000, which is Showdown's default. If
your server uses another port, add `--port` and the number:

```
pilot --port 8001 --login login.txt ladder
```

To stop it, press Ctrl+C. If it loses the connection, it tries again every
30 seconds.

## See its teams

```
pilot teams        lists every team by number
pilot teams 12     shows team 12, ready to import into the teambuilder
```

## Good to know

- It only connects to a Showdown server on the same computer, so it can't be
  used on the main Pokémon Showdown site.
- A registered name logs in through Pokémon Showdown's login service, the
  same one your server already uses for everyone else.
- It takes a few seconds per turn on purpose.
- Some of the teams are jokes.
