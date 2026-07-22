## Roll a random character

Use the starter project's idea lists to make a complete character at the click of a button.

> [!TASK]
>
> Select the `random` sprite. Start a new script that asks the player to confirm before replacing the current character.
>
> <p align="center"><img src="images/random-button.png" alt="The RANDOM button sprite." width="136" style="image-rendering: auto;"></p>
>
> ```blocks3
> when this sprite clicked
> ask [Roll a new character? Y/N?] and wait
> ```

Click **RANDOM**. Scratch should ask the question, but it should not change the character yet.

> [!TASK]
>
> Add an `if`{:class="block3control"} block that accepts either `yes` or a capital `Y`.
>
> ```blocks3
> when this sprite clicked
> ask [Roll a new character? Y/N?] and wait
> +if <<(answer) = [yes]> or <(answer) = [Y]>> then
> end
> ```

> [!TIP]
>
> The `or`{:class="block3operators"} block makes either answer valid. Any other answer leaves the current character unchanged.

> [!TASK]
>
> Inside the `if`{:class="block3control"} block, set `name`{:class="block3variables"} to a random item from the `name`{:class="block3variables"} list.
>
> ```blocks3
> when this sprite clicked
> ask [Roll a new character? Y/N?] and wait
> if <<(answer) = [yes]> or <(answer) = [Y]>> then
> +set [name v] to (item (pick random (1) to (length of [name v])) of [name v])
> end
> ```

Click **RANDOM** and answer `Y`. The first-name readout should change.

> [!TASK]
>
> Use the same pattern to pick `name2`{:class="block3variables"} from the `name2`{:class="block3variables"} list.
>
> ```blocks3
> if <<(answer) = [yes]> or <(answer) = [Y]>> then
> set [name v] to (item (pick random (1) to (length of [name v])) of [name v])
> +set [name2 v] to (item (pick random (1) to (length of [name2 v])) of [name2 v])
> end
> ```

> [!TASK]
>
> Add a block that picks the character's `style`{:class="block3variables"} from the `style`{:class="block3variables"} list.
>
> ```blocks3
> set [name2 v] to (item (pick random (1) to (length of [name2 v])) of [name2 v])
> +set [style v] to (item (pick random (1) to (length of [style v])) of [style v])
> ```

> [!TASK]
>
> Add a block that picks the character's `role`{:class="block3variables"} from the `role`{:class="block3variables"} list.
>
> ```blocks3
> set [style v] to (item (pick random (1) to (length of [style v])) of [style v])
> +set [role v] to (item (pick random (1) to (length of [role v])) of [role v])
> ```

Click **RANDOM** again. The character should now get a new full name, style, and role.

> [!TASK]
>
> Pick a random `concept`{:class="block3variables"} from the `concept`{:class="block3variables"} list.
>
> ```blocks3
> set [role v] to (item (pick random (1) to (length of [role v])) of [role v])
> +set [concept v] to (item (pick random (1) to (length of [concept v])) of [concept v])
> ```

> [!TASK]
>
> Finish the generator by setting `core#`{:class="block3variables"} to a random number from 2 to 5.
>
> ```blocks3
> set [concept v] to (item (pick random (1) to (length of [concept v])) of [concept v])
> +set [core# v] to (pick random (2) to (5))
> ```

Click **RANDOM** several times and answer `Y`. Every character should get two names, a style, a role, a concept, and a core number from 2 to 5.
