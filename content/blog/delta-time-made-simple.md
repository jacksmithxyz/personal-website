+++
title = "Delta time made simple"
date = 2025-03-10
+++

delta time = time elapsed since the last frame of execution.
simple! pack it up boys!

Really, though, it is a bit more complicated than that.

Delta time is a way to make behaviour consistent across different framerates in games. This can be difficult to visualize, or wrap your head around at first. so let’s look at an example.

## Computers running at different frame rates

Let’s say you have a computer running at 60 FPS.

You want to move your character from the bottom to the top of the screen, and when the arrow up key is pressed, your character moves 10 pixels up. the screen is 100 pixels tall.

Let’s do some math - i’ll try my best to keep this very simple.

Every second, our game updates 60 times (60 fps).

This means that there is a new frame every 1 (second) / 60 (frames) = 0.01667 seconds.

A user presses a key -> character goes 10 pixels up. one frame passes (0.01667 seconds), and the user is still pressing the key, so the character goes up.

This repeats until it hits the top of the screen - aka after 10 * 0.01667 = 0.1667 seconds.

Now let’s do the same calculation with a game running at 30 FPS.

This game is running slower, as every second, our game only updates 30 times (30 fps).

This means that there is a new frame of gameplay every 1 (second) / 30 (frames) = 0.03333 seconds.

The same happens again - a user presses a key to go up the same amount of pixels, but it takes them 0.3333 seconds to go up 10 pixels.

This repeats until the character hits the top of the screen - aka after 10 * 0.03333 = 0.3333 seconds.

So this means for a character to travel the same amount of distance on screen, it actually takes *double* the time on the slower computer.

This isn’t good as we want our gameplay to be consistent no mater what the frame rate is.

## So where does delta time come into this?

Delta time is simply the time between each frame - on computer one it will be the 0.01667 seconds we calculated, on computer 2 it will be 0.03333 seconds.

We then use this to create consistent behaviour.

Going back to our movement example, our implementation is now wrong.

We cannot move a character a flat amount of pixels across the screen if we want continuous movement.

So to solve this, we set an arbitrary number, say 200, and multiply this by delta time to create our own movement "amount".

So instead of a flat "move 10 pixels when the key is pressed", we say "move 200 * delta time when the key is pressed". So for computer 1, this would be 200 x 0.01667 = 3.34 *pixels* per frame upwards. For computer 2, this would be 200 x 0.03333 = 6.666 pixels per frame.

Now, each character will reach the top of the screen at the same time. As the faster computer executes more frequently it moves a smaller distance, while computer 2 moves a larger distance as it executes more slowly.

It also means if a game's frame rate changes, gameplay will still remain consistent, as it will just pull the delta time since the last frame.
