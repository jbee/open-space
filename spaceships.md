---
layout : default
title: Spaceships
---
# Spaceships

## Models
A model is a prototype without a specific scale described by multiple layers of blocks of different components.  
When designing a model normally the smallest layer size is chosen that allows to describe the composition of choice.
However a larger layer size can be selected to achieve more optical details by describing in a larger scale and 
create classes that have a negative (dividing) factor. 

## Classes
A _Class_ is a Model in a specific size or scale. Each Model can be scaled up or down by a integral number factor.

## Components
### Costs
Consist of 2 parts

- Manufacturing
- Assembly (installation, deinstallation)

During updates of spaceships there can be 3 partial costs

- Deinstallation of existing components
- Manufacturing of the new component
- Installation of the new component

It is also possible to switch components by just do

- Deinstallation
- Installation

Hence there is a store on each planet that contains all already manufactured components.
Also transporters can be used to transport manufactured components from another planet to the planet
where a spaceship is assembled.   

## Composition
A spaceship is described by multiple layers each consisting of square blocks in a 2-dimensional surface.
Each block is a cube in 3-D. It can be selected which edges should be rounded visually.

	   x
	  xxx
	xxxxxxx
	xxxxxxx
	xx   xx
	
All components are placed as blocks. Some might be or chosen to be larger than a single block. The can become 2x2, 3x3 or 4x4 blocks big but will stay 1 layer (block) height.
The damage model is also per block. Some edges have special functions, others don't allow neighbor blocks.

## Blocks
### Edges
Each edge of a block can have **one** special purpose like

- connect to a consumption/requirement
- outer edge (so that a weapon can fire that way)

To prevent the need for rotation the use of each edge is automatically chosen. 
The player can customize this by giving all edges a priority 1-4 for each possible purpose (those are derived from the component or block type).

### Conduction
One type of blocks are conductions that connect one or more types of resource between blocks.
This allows to adapt the design of known science fiction spaceships into the game.

The difference is that a conduction is not so heavy and cheaper to manufacture than another component 
block but they increase the risk of disconnection between dependent components.

Because conduction can conduct mass, energy and control at the same time a more compact design becomes possible. 

### Damage
The damage a component block can take before it stops working depends on several things:

- Material
- Structural points (mainly derived from size)

Some thoughts about damage
- Mass passes shields
- Mass disrupts components dependent on their material (its strength). This allows to cause damage on inner components even though the outer is not destroyed yet. The damage cause will be weakened by the disrupted material.
- Missiles passes shields but cannot disrupt components.
- Components that are destroyed are passed as if they are non existent.
- A component has a degree of maximum damage where from it can be repaired again.
- Scanner effect the damage (better knowledge causes better hits) 

### Colors
- Weapons: Red
	- Ray (Beam): Purple
	- Mass: Orange
	- Missile: Yellow
- Control: Blue
	- Electronic: Cyan
	- Optical: ?
	- Mechanical: ?
- Energy: Green
	- Combustion: ?
	- ?
- Drive:
	- Repulsion (Mass based): ??
	- ?? (Enery based): ?
- Scanner: ?
- Cargo space: ?
- Special: ?

## Miniaturization
- Regulates the maximal available/plannable block count during the design process.

## Material
- Regulates the maximal available component size (in blocks like 2x2, 3x3, ...)
	- Bigger blocks can be attractive because
		- More connections are possible
		- The relative required space for requirements like control or energy can be reduced
	- the maximum is derived from the material properties (unclear now)  
	
Properties are:
- Strength
- ?

## Scanner
- Allow to see opponents component structure and current state
- Allow to target specific components

## Armour
- Is placed as blocks/components as well.
	- Allows to chose different materials in one ship
	- Allows to use inner armour
- Stops beam and missile damage 
- Dependent on the material just seperate single blocks or connected blocks can be created. E.g. metals cannot share damage where something fluid can - so metals are always single blocks and fluids can be connected blocks.

## Computer
Computers are mainly used as target computer. The main difference between different computer techniques is the reaction time needed to recompute the targeting for a moving target.

Damage is anti-proportional to 
- reaction time
- mobility of the target

Probability of a miss
- anti-proportional to reaction time
- proportional to mobility of the target

When targeting specific components it becomes harder to compute. Some computers are especially good at targeting components.



  	 