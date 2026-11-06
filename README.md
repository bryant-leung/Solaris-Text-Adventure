# Solaris Text Adventure

A Pokémon-inspired text adventure game in Java, built for the Year 1 Object Oriented Programming module at the University of Birmingham (2024).

You wake up in **Solaris**, a region where humans and Pokémon live side by side. Explore 60+ locations across icelands, meadows, forests, rivers, coasts and tropics, catch wild Pokémon, open hidden chests and finish quests, all by typing commands.

## Features

- **Game world loaded from a text file.** Rooms, exits, items and equipment are all defined in `data/game.txt` and read in by a custom parser, so the map can be changed without touching code.
- **Command parser.** A tokeniser and parser turn what you type (`use key on chest`) into commands.
- **Wild encounters.** Each area has its own Pokémon, and you can try to catch them.
- **Quests and puzzles.** A chest chain (Diamond Key → Ruby Chest), and a pier quest where you gather clues and talk to people to find a lost Zigzagoon.
- **Combining items:** join the Yin and Yang relics, then combine the result with the Town Emblem to earn a Gym Entry Pass.
- **Fishing mini-game**, an **equipment shop**, and **Rotom**, a helper that lists the Pokémon you've caught.
- **Score** for finishing quests and events.
- **94 JUnit tests** covering the commands, game objects, parser and file loader.

## Commands

| Command | Example |
|---|---|
| `move <direction>` | `move north` |
| `look <room / exit / features / item>` | `look room` |
| `get <item>` / `drop <item>` | `get key` |
| `use <item> on <target>` | `use DiamondKey on RubyChest` |
| `combine <item> and <item>` | `combine RelicYIN and RelicYANG` |
| `status <player / inventory / map / score / item>` | `status inventory` |
| `help <topic>` | `help move` |
| `quit` | |

## Running it

Needs Java 17 or newer.

```bash
sh run.sh     # compile and play
sh test.sh    # compile and run the tests
```

## Project layout

```
src/org/uob/a2/
  Game.java          main game loop and quests
  commands/          one class per command
  gameobjects/       rooms, items, player, Pokémon, encounters, shop, mini-game
  parser/            tokeniser and parser for typed commands
  utils/             loads the world from data/game.txt
test/                JUnit tests
data/game.txt        the game world
docs/                generated Javadoc
```

## Notes

Fan project for a university module. Pokémon and related names belong to Nintendo, Game Freak and The Pokémon Company.
