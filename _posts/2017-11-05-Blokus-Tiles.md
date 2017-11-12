---
layout: post
title: "Blokus Game"
author: "Napassorn"
categories: resources
tags: [resources]
image:
  feature: city-4.jpg
---

[# Blokus-Tiles](https://github.com/napassornl/Blokus-Tiles)
A class assignment of C++ program that reads information about game tiles (tiles) for game Blokus and outputs similar file with only unique tiles contained in input file.

The program should expect three command line arguments:  
• the maximum size of the blokus tiles  
• the input file name  
• the output file name  

# The Blokus Game
Blokus tiles are free polyonimoes. Here is an excerpt from wikipedia:  

A polyomino is a plane geometric figure formed by joining one or more equal squares edge to edge. It is a polyform whose cells are squares.  

The format of the tiles is a square text box with * indicating the location of the cells, and . filling in the picture but meaning the absense of a cell. Empty lines separate the tiles for readability.  

Here is an example file (called a tileset) with 2 5x5 tiles:  
.....  
.*...  
**...  
*....  
*....  

.....  
.....  
**...  
*....  
**...  

The tiles represented are
*  
**  
*  
*  

**  
*  
**      

Note: Tiles can be picked up and flipped over. The cells must be connected side-to-side,
not on a corner. Think of them as rigid, flat pieces of colored plastic (since that
is actually what they represent in the game).

# Details
## Input Format
 • if any character other than . or * is encountered in a tileset, exit the
program immediately, with no output, and with a return code of 1.  
• there must be exactly one empty line after each tile. If this condition is
not met, exit the program immediately, with no output, and with a return
code of 2.  
• if any textbox is encountered with an incorrect overall size (not NxN), exit
the program immediately, with no output, and with a return code of 2.  

## Output Format
If no errors occur, the program should output the same tiles as contained in the
input tileset, and exit with a return code of 0.  
In addition:  
• the program should output nothing “extra”  
• the output tiles should be in the same order as the input tiles  

Here is an example:  
.**.  
....  
....  
....  

....  
*...  
*...  
....  

These represent the same piece (the domino) and the output file should have:  
.**.  
....  
....  
....  

