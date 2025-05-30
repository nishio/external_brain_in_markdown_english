---
title: "Transport-Pipes"
---

Plug-in to introduce pipes into the micra.
- No more hoppers and droppers forcing you to achieve pipe-like things.

Normal pipe
- Made on a workbench with four pieces of glass.

Golden Pipe
- There is an item sorting function.
- Color is what is shown at the joints, not the color of the pipes that connect them.
- Can also be set to pass through "other" than the specified one.
- Gold block required
- At first I thought it was very useful, but as I got to know the other pipes, it became less and less valuable! but as I got to know the other pipes, it became less and less valuable.

Extraction Pipe
- Pipes with the function of transferring items in chests, etc. to pipes.
- Actually, it has a filter for what it sucks out as well.
    - So instead of gold pipes, you can do the same with chests and extraction pipes, gold blocks are just more compact.
- Can be set up to be controlled by Redstone.
- Stack size to be transported at one time can be 16
    - Useful when you want to move a chest full of stuff to another place.
- See below for Direct settings.
    - Physically unnatural behavior but super convenient

Colored pipes
- Compact piping because different colors are not connected.
    - However, ordinary white pipes can be connected to any of them.
    - In addition, the cross-sectional view of the pipe can be set to not connect even if they are the same color by tapping the pipe's cross-sectional view with a wrench.

Pipes can be used to put things in the kamado.
- Burned items are from the top and sides, fuel is from the sides only, and results are sucked out from the bottom.

craft pipe
- Craftable.
- For example, coal can be automatically turned into coal blocks before being put into chests.

Official commentary is here.
- 5.0.0 for Minecraft 1.13 [https://www.spigotmc.org/resources/transport-pipes.20873/](https://www.spigotmc.org/resources/transport-pipes.20873/)
    - However, this 5.0.0 does not support 1.17
- Here is a good 5.3.0 [https://github.com/BlackBeltPanda/Transport-Pipes/releases](https://github.com/BlackBeltPanda/Transport-Pipes/releases)
- 1.18 supported in 5.4.0.

What is a Direct setting?
- Tweet
    - > [nishio](https://twitter.com/nishio/status/1438919182934966279): Wow, so whether or not the items flowing through the pipe separate when they come to a branch of the pipe is determined by the attributes of the sucking pipe when it is sucked out of the chest? Really?
    - > [nishio](https://twitter.com/nishio/status/1438925551108984832): No, I think it's "send all pipes to the 0th one except the direction they came from" depending on the option, and that 0th one is determined by the order of the enum representing the direction. I think that the behavior changes depending on the direction of the pipe.
        - This is the Direct setting
    - > [nishio](https://twitter.com/nishio/status/1438927890440089604): yes correct, in the left arrangement the item goes straight into the chest by the torch, in the right arrangement the item turns right and enters the chest with the torch. This is because the east-west pipe has priority over the north-south pipe.
        - ![image](https://gyazo.com/5ffeff86977c1057c4b9fdd5d2cce0a5/thumb/1000)
    - > [nishio](https://twitter.com/nishio/status/1438929863927160833): Given this, automatic sorting chests can be realized with just this. Since the front-back direction of the screen is east-west, priority is given to the chests on the left, and they behave in the order of "if it fits in that chest, put it in, if not, go to the pipe on the right".
        - ![image](https://gyazo.com/e1a30e49903d5ac3585f5de9a6dd4f98/thumb/1000)
    - > In addition, the top and bottom have the lowest priority, so if they are stacked vertically, they can be oriented freely on all four sides.

Explanation for those who understand Java
- If the item is in DIRECT mode, send all of them to the first possible direction of movement option.
    - [ItemDistributorService.java#L119](https://github.com/BlackBeltPanda/Transport-Pipes/blob/33dfb9aaf42438405328511b5e5235b416c33ef0/src/main/java/de/robotricker/transportpipes/duct/pipe/filter/ItemDistributorService.java#L119)
java

```
if (pipeItem.getExtractMode() == ExtractMode.DIRECT) {
    splitMap.put(weightsDirectionList.get(0), item.getAmount());
}
else {
```

- The possible direction of movement is the direction in which the pipes are connected, minus the opposite direction in which the item came from.
    - [Pipe.java#L329](https://github.com/BlackBeltPanda/Transport-Pipes/blob/33dfb9aaf42438405328511b5e5235b416c33ef0/src/main/java/de/robotricker/transportpipes/duct/pipe/Pipe.java#L329)
java

```
protected Map<TPDirection, Integer> calculateItemDistribution(PipeItem pipeItem, TPDirection movingDir, List<TPDirection> dirs, TransportPipes transportPipes) {
	Map<TPDirection, Integer> absWeights = new HashMap<>();
	dirs.stream().filter(dir -> !dir.equals(movingDir.getOpposite())).forEach(dir -> absWeights.put(dir, 1));
	return itemDistributor.splitPipeItem(pipeItem, absWeights, this);
}
```

- Direction" is an enumeration defined in the order of east, west, south, north, and up.
    - [TPDirection.java](https://github.com/BlackBeltPanda/Transport-Pipes/blob/33dfb9aaf42438405328511b5e5235b416c33ef0/src/main/java/de/robotricker/transportpipes/location/TPDirection.java)
:

```
public enum TPDirection {
    EAST(1, 0, 0, BlockFace.EAST, LangConf.Key.DIRECTIONS_EAST.get()),
    WEST(-1, 0, 0, BlockFace.WEST, LangConf.Key.DIRECTIONS_WEST.get()),
    SOUTH(0, 0, 1, BlockFace.SOUTH, LangConf.Key.DIRECTIONS_SOUTH.get()),
    NORTH(0, 0, -1, BlockFace.NORTH, LangConf.Key.DIRECTIONS_NORTH.get()),
    UP(0, 1, 0, BlockFace.UP, LangConf.Key.DIRECTIONS_UP.get()),
    DOWN(0, -1, 0, BlockFace.DOWN, LangConf.Key.DIRECTIONS_DOWN.get());
```


---
This page is auto-translated from [/nishio/Transport-Pipes](https://scrapbox.io/nishio/Transport-Pipes) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.