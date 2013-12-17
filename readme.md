### crafty.hexametric.js

A tool similar to crafty.isometric or crafty.diamondIso but for isometric hexagonal grid based layouts.


I'm sure there are loads of holes in this, but it's a start.. You can see a simple implementation [here](https://github.com/matthewsimo/hex-tests):

![hexametric grid](http://f.cl.ly/items/0J1b2R3i2b3c05193F28/Screen%20Shot%202013-12-17%20at%209.02.03%20AM.png "hexametric grid")


Once it's included in your project you have two things to do.

- Init the grid
- Place tiles


### Init the grid

Initializing the grid is simple:

```
  hex = Crafty.hexametric.init(64, 64, mapsize.x, mapsize.y);
```

So far, this only supports an offset "even-r" grid layout as described [here](http://www.redblobgames.com/grids/hexagons/#coordinates). Tile (0,0) will be the top, left most spot, and will go from there.

The first two parameters are tile dimensions, this tells hexametric how to offset things, for math purposes, use nice base2 numbers (32,64,128,etc)..

The last two parameters are the column number & row number, this is only somewhat implemented and doesn't clip or replace if you try to place a tile in an invalid column or row.


### Place tiles

```
  var t = Crafty.e("2D, Canvas, tile"+tile).attr({w: 64, h: 64});

  hex.place(t, x, y, 1);
```

This is the placing method, you need a Crafty entity ([Crafty.e](http://craftyjs.com/api/Crafty-e.html)) for the first parameter.

The next two parameters are the (x, y) coordinates you want the tile to sit on the grid. (EX: (3,3) would be the fourth row & fourth column (zero based))

The last parameter is for which layer you want the entity to be placed on, this will be useful if you have multiple layers in play... (ground tiles, ornament tiles, player tiles, etc..)


### Up Next

This was mostly to scratch my own itch and learn, I'm happy to accept pull requests and take requests.
