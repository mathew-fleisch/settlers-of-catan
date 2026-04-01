# Settlers of Catan: The Living Game

Welcome to the community-driven, Git-powered game of Settlers of Catan! This repository hosts a live game where every move is tracked via Git commits and every interaction is managed by the "Dungeon Master" (DM) rules engine.

## How to Play

### 1. Join the Game
To join an ongoing game, simply open a Pull Request (PR) adding your GitHub username to the `players` list in `game.yaml`. Once the PR is merged, you will be assigned a player color and starting position.

### 2. Make a Move
Moves are submitted by editing the `game.yaml` file. You can:
- **Build Roads/Settlements**: Specify the vertex or edge ID.
- **Trade**: Create trade offers in the `trade` section.
- **Move the Robber**: Update the robber's hex location.

Each valid change to `game.yaml` will trigger the DM engine to validate the move and update the game state.

### 3. "PR Chat" System
Every Pull Request acts as a chat channel. Comments made in PRs are periodically scraped and injected into the game's internal chat log, which is then rendered in the TUI. Use this to negotiate trades or form alliances!

## The TUI Experience

You can view the current state of the game in a high-fidelity Terminal User Interface (TUI).

### Viewing the Game
To see the board and your inventory:
1. Clone this repository.
2. Run the `catan` binary (available in the `catan/` engine repo or as a pre-built release).
3. Run `./catan` in this directory.

### Interactive Controls
- **[1]**: Board View
- **[2]**: Trade & Inventory View
- **[3]**: PR Chat View
- **[/]**: Start typing a message for the chat log.

## Automation & The Dungeon Master

The **Dungeon Master** is a GitHub Action (`dm.yml`) that runs on every push. It performs the following:
- **Validation**: Ensures all moves follow the official Catan rules.
- **Resource Distribution**: Automatically distributes resources when the dice are rolled.
- **Asset Generation**: Generates an updated `catan_game.gif` replay of the entire game so far, visible in the main README or PRs.

## Current Game Status

![Game Replay](catan_replay.gif)

Check out `STATUS.md` for the latest leaderboard and game milestones.
