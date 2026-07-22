## Show every result

Move the dice roller button into the centre and show all four stored results in one line.

> [!TASK]
>
> Select the `dice roller` sprite. Start a new setup script with a `when green flag clicked`{:class="block3events"} block.
>
> ```blocks3
> when green flag clicked
> ```

> [!TASK]
>
> Add a block that switches the sprite to its `button3-a` costume.
>
> ```blocks3
> when green flag clicked
> +switch costume to (button3-a v)
> ```

> [!TASK]
>
> Return to the long click script. After the three bonus checks, wait 3 seconds so every active die has time to finish rolling.
>
> ```blocks3
> if <(teamwork) = (1)> then
> broadcast (teamwork v)
> end
> +wait (3) seconds
> ```

> [!TASK]
>
> Change to the next costume and move the sprite to `x: -100` and `y: -100`.
>
> ```blocks3
> wait (3) seconds
> +next costume
> +go to x: (-100) y: (-100)
> ```

> [!TASK]
>
> Add a `think`{:class="block3looks"} block for 5 seconds. Join the main result and Prepared result with a ` | ` separator.
>
> ```blocks3
> go to x: (-100) y: (-100)
> +think (join (roll) (join [ | ] (prepared roll))) for (5) seconds
> ```

Click **DICEROLL** with P off, then with P on. The second number in the thought bubble should be `0` when Prepared is off and a die result when it is on.

> [!TASK]
>
> Insert more `join`{:class="block3operators"} blocks so the thought bubble also includes `expert roll`{:class="block3variables"}.
>
> ```blocks3
> think (join (roll) (join [ | ] (join (prepared roll) (join [ | ] (expert roll))))) for (5) seconds
> ```

> [!TASK]
>
> Extend the joined text one last time to include `teamwork roll`{:class="block3variables"}.
>
> ```blocks3
> think (join (roll) (join [ | ] (join (prepared roll) (join [ | ] (join (expert roll) (join [ | ] (teamwork roll))))))) for (5) seconds
> ```

> [!TIP]
>
> The results always appear in the same order: main | Prepared | Expert | Teamwork. A `0` means that bonus die was switched off.

> [!TASK]
>
> After the thought bubble, change back to the button costume.
>
> ```blocks3
> think (join (roll) (join [ | ] (join (prepared roll) (join [ | ] (join (expert roll) (join [ | ] (teamwork roll))))))) for (5) seconds
> +next costume
> ```

> [!TASK]
>
> Finish by returning the button to `x: 223` and `y: 163`.
>
> ```blocks3
> next costume
> +go to x: (223) y: (163)
> ```

Try several switch combinations. After each roll, the dice roller should move into the sheet, show four results, then return to its top-right position.

> [!INFO]
>
> The sheet reports the dice rather than deciding success. For Logic, each die at or below the core number succeeds. For Instinct, each die at or above it succeeds.
