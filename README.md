# Quirky Quarks

A tabletop board game of Quirky Quarks implemented in Lua for [Tabletop Simulator (TTS)](https://www.tabletopsimulator.com/).

## Overview

Quirky Quarks is a particle physics-themed game where players collect subatomic particle cards, build composite particle quest cards, and score points across 5 rounds with 5 distinct phases.

Purchase the board game here: https://www.quirkyquarks.com/ or at the CERN bookshop in Switzerland!

## Gameplay

### Objective
Score the most victory points (VP) by completing Quest cards and accumulating currency.

### Components
- **Particle Cards**: Up Quark, Down Quark, Gluon, Photon, Electron, Positron, Proton, Neutron, Anti Up/Down
- **Quest Cards**: Composite particles like Hydrogen, Helium, Neutronium, Antihydrogen
- **Colliders**: SLAC, Tevatron, ESRF, LHC, SuperKEKB
- **Currency**: 1 eV and 3 eV coins

### Phases (per round)
1. **Funding** - Receive 3 eV, draw cards
2. **Research** - Bid on colliders to win particle cards
3. **Ejection** - Eject unwanted cards, earn 1 eV per ejection
4. **Discovery** - Auction bidding on remaining ejection pile cards
5. **Quest** - Spend particles to complete Quest cards

### Players
2-4 players

## Core Scripts

| Script | Description |
|--------|-------------|
| `Global.-1.ttslua` | Main game state controller - handles phases, turn order, scoring, and global game logic |
| `Global.-1.xml` | UI layout definition for game interface |

## Buttons & Controls

| Script | Description |
|--------|-------------|
| `Start Button.*.ttslua` | Initializes game - deals hands, places starting coins, sets player order |
| `Buy Card.*.ttslua` | Handles quest card purchases - validates costs, applies Gluonium discounts |
| `Score Button.*.ttslua` | Calculates victory points from quests and currency |
| `Phase Button.*.ttslua` | Advances through game phases (Funding→Research→Ejection→Discovery→Quest) |
| `Auto Buy Button.*.ttslua` | Automates card buying process |
| `Secondary Buy.*.ttslua` | Secondary purchase option for multi-card buys |

## Game Phases

| Script | Description |
|--------|-------------|
| `Collider Board.*.ttslua` | Research phase bidding - players bid on colliders to win particle cards |
| `Ejection Pile.*.ttslua` | Ejection phase card discarding and Discovery phase auction mechanics |
| `Turn Control.*.ttslua` | Manages current turn, player order, and skip mechanics |

## Deck Management

| Script | Description |
|--------|-------------|
| `Particle Deck.*.ttslua` | Main deck - handles draws, reshuffles discards when needed |
| `Particle Discard.*.xml` | Discard pile configuration |
| `Quest 1 Deck.*.ttslua` | Quest 1 card deck management |
| `Quest 2 Deck.*.ttslua` | Quest 2 card deck management |
| `Quest 1 Discard.*.xml` | Quest 1 discard pile |
| `Quest 2 Discard.*.xml` | Quest 2 discard pile |

## Player Boards

| Script | Description |
|--------|-------------|
| `Red Build.*.ttslua` | Red player's build zone for completed quests |
| `Red Coins.*.ttslua` | Red player's coin display and tracking |
| `Red.*.ttslua` | Red player general zone |
| `Blue Build.*.ttslua` | Blue player's build zone for completed quests |
| `Blue Coins.*.ttslua` | Blue player's coin display and tracking |
| `Blue.*.ttslua` | Blue player general zone |
| `Green Build.*.ttslua` | Green player's build zone for completed quests |
| `Green Coins.*.ttslua` | Green player's coin display and tracking |
| `Green.*.ttslua` | Green player general zone |
| `Yellow Build.*.ttslua` | Yellow player's build zone for completed quests |
| `Yellow Coins.*.ttslua` | Yellow player's coin display and tracking |
| `Yellow.*.ttslua` | Yellow player general zone |

## Currency

| Script | Description |
|--------|-------------|
| `1 eV.*.ttslua` | 1 eV coin bag management |
| `3 eV.*.ttslua` | 3 eV coin bag management |
| `Quarter.*.ttslua` | Quarter coin handling |

## Dice & Tokens

| Script | Description |
|--------|-------------|
| `round_dice.*.ttslua` | Round tracking die |
| `phase_dice.*.ttslua` | Phase indicator die |
| `Sort Tile 1.*.ttslua` | Card sorting helper tile |

## License

MIT License