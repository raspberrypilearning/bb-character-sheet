## Celebrate Laser Focus

Animate Dot, the crew's space-dog sidekick, whenever any die matches the core number.

> [!TASK]
>
> Select the `Dot` sprite. Start a new setup script with a `when green flag clicked`{:class="block3events"} block.
>
> <p align="center"><img src="images/laser-focus.png" alt="Dot the space dog in an astronaut helmet." width="120"></p>
>
> ```blocks3
> when green flag clicked
> ```

> [!TASK]
>
> Add a `hide`{:class="block3looks"} block so Dot waits off-stage until Laser Focus happens.
>
> ```blocks3
> when green flag clicked
> +hide
> ```

Click the green flag. Dot should disappear while the character sheet stays visible.

> [!TASK]
>
> Start Dot's celebration with a `when I receive laser focus`{:class="block3events"} block.
>
> ```blocks3
> when I receive (laser focus v)
> ```

> [!TASK]
>
> Move Dot to the centre at `x: 0` and `y: 0`, then show the sprite.
>
> ```blocks3
> when I receive (laser focus v)
> +go to x: (0) y: (0)
> +show
> ```

> [!TASK]
>
> Play Dot's `LASER FOCUS` sound until it finishes.
>
> ```blocks3
> go to x: (0) y: (0)
> show
> +play sound (LASER FOCUS v) until done
> ```

> [!TASK]
>
> Add a loop that repeats 10 times. Inside it, move to the next costume and wait 0.2 seconds.
>
> ```blocks3
> play sound (LASER FOCUS v) until done
> +repeat (10)
> next costume
> wait (0.2) seconds
> end
> ```

> [!TASK]
>
> Inside the loop, change the colour effect by 25 after each wait.
>
> ```blocks3
> repeat (10)
> next costume
> wait (0.2) seconds
> +change [color v] effect by (25)
> end
> ```

> [!TASK]
>
> Make Dot grow during the celebration by changing size by 10 on every repeat.
>
> ```blocks3
> repeat (10)
> next costume
> wait (0.2) seconds
> change [color v] effect by (25)
> +change size by (10)
> end
> ```

> [!TASK]
>
> After the loop, hide Dot and reset the sprite to 100% size for the next celebration.
>
> ```blocks3
> repeat (10)
> next costume
> wait (0.2) seconds
> change [color v] effect by (25)
> change size by (10)
> end
> +hide
> +set size to (100) %
> ```

Set a core number, then keep rolling. When any active die matches it, Dot should appear, play the Laser Focus sound, change costume and colour, grow, and then hide again.
