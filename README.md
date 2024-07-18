## Features

- Undo/redo
- Selection, copy/paste/delete
- **Dynamic audio** that responds to the physics (must be enabled first)
- Collidable windows
- Rope tool
- Ball tool
- Glue tool
- Precise connector tool
- Ghost trails, slow motion, gravity, and other settings
- Keyboard shortcuts to switch tools (and to use some tools without switching)
- Touch support

## Ways to Lose Data

This should be considered a toy.
However, since this is a topic I care about, I like to think about ways users can lose data, and I've documented it here.

There's **no save/load**. And the clipboard is internal, so you can't use it as a workaround to save/load. Everything is lost if you close the tab.

Some things are not in the undo state, even though they affect the world:
- browser window size,
- in-app window positions and sizes,
- simulation options like gravity

Furthermore, if the simulation is active, undo/redo is destructive,
because the states will be replaced with ones further ahead in time,
as you go back and forth.
For example, if you throw a point, and undo, the redo state is the state at which you undid the throw, so if you redo, it will be in midair.
Then it lands, and you undo and redo, and it's already landed in the redo state.

And some things don't create undo history, like dragging windows,
so you can go for quite some time messing around without creating any undo states you can go back to.

## Help + TODO

See in-app Help and TODO windows accessible from the Options window.
