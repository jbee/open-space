---
layout : default
title: Gameplay
---
# Gameplay

## Messages
- Can be devided into groups
	
	Goal: Partial or full automation of colonies.
	Some events should occur as message so that the player can switch to manual in the right moment.
	
## Menu
- Is organized as a stack of nested screens (clicked by the player)

Example:

    Colony:Earth > All Colonies > Turn
    

## Automation
KI can control a colony or a group of colonies. The player supplies presettings (in %) for

- Research
- Production
- Growth

Generally colonies can be grouped into named groups. When a colony is manages from the group list
page the player can navigate to the previous or next colony of the same group directly.

Also there can be an abstract group-colony where the player can take the same action for all colonies of the group (e.g. chose what to build).

Beside the ability to compose custom groups by selecting the members there are also groups that are computed from expressions so the members change dynamically whether or not the expression is evaluated to true or false.
Some examples of such groups are:

- Manual controlled colonies
- KI controlled colonies
- Growing colonies
- Shrinking colonies
- Researching colonies
- Top X researching Colonies
- Colonies having a research higher than Y


## Setup
There will be a lot of numbers in the game. Numbers play a huge role but not all player might want 
to see all of them from the very beginning so there should a setup before a new game is started
how many numbers should be used and/or shown:

- Use and show all numbers
- Substitute numbers with words where possible (like: "very high", "high, "medium", "low", "very low")
- Simplify where possible (some variables to become constants and are not shown)

Generally as much numbers as possible should be normalized to the same scale so that the player can
get a feeling for all of them.