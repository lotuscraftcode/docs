## What is Craftia?

Your space ship has discovered an unexplored planet and has positioned itself in a hovering pattern over the planet's surface. You are part of the away team with a mission to explore the planet's surface. Unfortunately the ship is not in great condition. The left engine is having issues and food supplies are running low. The away team will have to make do with what it can find on the planet. You can pick up a go kit with an elytra for gliding down to the surface, a compass and a lode stone to mark areas of interest and navigate back to them.

The ship's warp system is functional which allows you to warp back to the ship at any time.

## Arriving for the first time

When you join Craftia, you will start in the space ship and your personal spawn (not world spawn) will be set to the space ship. Get your go kit with the following command:

    /kits go

The go kit contains Elytra, a compass and a lode stone.

## Explore the planet surface

Wear elytra on your body so you can glide down to the surface and explore. At any time you can warp back to the space ship with the command:

    /warp ship

It takes 5 seconds for the space ship's warp system to tune in on your coordinates and initiate the warp. You must not be moving or be under attack during this time.

If you find a place of interest that you want to return to, place the lode stone and right-click with your compass. After warping back to the space ship (or going elsewhere on the map), your compass will guide you back to this point.

You can get as many go kits as you want. This enables you to mark many places of interest with lode stones and finding them again with your compasses.

## Establish a base

You can establish a base that is protected from other explorers. When you've found a good spot for your base, run the command:

    /setbase

This will create a based that stretches 30 blocks in each direction (including vertically) from where you are standing. Your location with be set as the home warp point. You can warp to this location from the space ship with the command:

    /warphome

Other explorers can walk onto your base but they cannot break blocks or open doors, so you can protect yourself and your chests by building a house and keeping the door closed. You can remove your base with the command:

    /removebase

This allows you to create a new base somewhere else.

## Advanced commands

Your base is protected using a WorldGuard region. You can use advanced commands to modify the region, the location of the warp point and decide whether strangers are able to open doors and chests. You can also add and remove other explorers as members of your region.

### Select a new area and redefine your region

You can use any of the [WorldEdit selection commands](https://worldedit.enginehub.org/en/latest/usage/regions/selections/) to select an area of the map and then redefine the region of your base. For example you can use `pos` commands like this:

* Mark one corner by standing on it and running the command `//pos1`
* Mark the opposing corner by standing on it and running the command `//pos2`
* Claim the region with `/region claim <name-of-region>`. This only works if you don't already have a region/base
* If you already have a region, you can redefine it to the new area with `/region redefine <name-of-region>`

### Delete a region with a custom name

`/removebase` expects the name of your region to be "<username>base". If you have given your region another name with `/region claim` then delete it with:

    /region delete <name-of-your-region>

### Inspect your region

To see details about your region, stand inside the region and run the command:

    /region info

If the command shows details about the `__global__` region, then you are not standing inside your region.

### Adjust the shape of your region

If you want to make small adjustments to your region area, you can first select the current region:

    /region select <name-of-your-region>

Now you can change the shape of the region using `//expand` and `//contract` commands:

    //expand 4 west

to expand your region 4 blocks westwards or

    //expand vert 10

to expand your region 10 blocks upwards or 

    //expand vert -10

to expand downwards 10 blocks (you can use any other number). `//contract` works in a similar way. Once you have modified your selected area, it's important that you now actually redefine your region:

    /region redefine <name-of-your-region>

This is the command that actually sets the new dimensions of the region so don't forget it.

### Add members to your region

When you claim a region, you are the region's owner and nobody else can break or place blocks in the region. If you want another explorer to share access to your region you can add them as a member:

    /region addmember <name-of-your-region> <name-of-user>

You can remove them with 

    /region removemember <name-of-your-region> <name-of-user>

### Restrict Chest Access in your region

When you claim your region, only you and its members can open and close doors and break blocks. This means you can easily protect your base and prevent others from accessing chests by keeping them behind closed doors.

But if you forgot to close the door, then a stranger can walk in and open your chests. You can protect you chests with the following command:

    /region flag <name-of-your-region> -g nonmembers chest-access deny

Turn chest access back on with

    /region flag <name-of-your-region> -g nonmembers chest-access allow
