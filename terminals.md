---
layout : default
title: Terminals
---
# Terminals

A terminal is a display and controller for one game screen.
A screen is a single interface that is presented to the user to carry out a screen specific task like battle, manage colony, colony list and so on.

Theoretically it should be possible to play the game using very different terminals for each of the game screens.
While battle in ASCII-Art + Keyboard control colonies could be managed in 3D-Open-GL with mouse control.

## Factories
Terminals are created from factories. A factory usually gets 2 inputs:

- Game
- Selection from previous Screen (e.g. Player, Colony, Spaceship, Battle, ...)

As long as all factory arguments are just simple data (identities) it will be
easy to play the game distributed using different actual UIs like browsers, desktop apps, consoles, mobile apps and so on.

This requires the game to run on a central unit that is asked for the terminals
or a data-only form of a game can be used effectively so that the state of a game
is recreated very fast before the terminal to the instance is provided.

Each change done through a terminal creates a new state. This is very close to
versions in a version control system like git. maybe it can be used as underlying
datastore.

When creating an actual instance for each terminal laziness is vital.
The game should just need to create objects that are actually used.
Also there should be the possibility to share data by give them an identifier
and version so that the game can cache data structures. Since it is a turn based
game the version is the turn plus the latest changes done in a turn. So changes
should be maintained as changeset/diff till the end of the turn. Than the diffs
are applied to the last turn what computes the next turn. This creates a functional
behaviour. A turn becomes a function depending only on the previous turn and the changes made and creates a new turn.
There are no side effects at all. Saving a game just means to keep a turns data.
Loding a game just means to use another previous turn data (mostly free cache memory and such performance things).

All this makes it very important to have a highly efficient, human readable, diffable and universal data format.
The format should allow to divide the description of record structures and types from actual values.
Thereby the "system" just learns once how to read a specific record format and translate it into typed instances (classes).

## Actions
Each Screen contains one or more action-sets. Actions are possible operations described as data. The result of an action is data as well. A typical example would be a selection.

## State
In general there are 2 kinds of state: 

- Navigation and selection state that is not changing the turn/game state at all
- Reconfiguration state that changes the turn/game state
	- Done or directly triggered by the player
	- triggered as an automatic reaction to a player action
	- triggered as an automatic reaction as a player configuration
	- triggered as an automatic reaction to a game rule (the game mechanics)
	
Screens could work a bit like RESTful HTTP resources. When you access them with a special navigation state you'll access another view of that resource.
E.g. colony view with colony id is a single colony screen, without it is a list of colonies. 
That would mean a view has multiple screens depending on the navigation state a particular screen is picked. Thereby a screen can expect a particular navigation state.