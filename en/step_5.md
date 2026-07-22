## Create your own character

Let players type their own character details when they press the space key.

> [!TASK]
>
> Select the `Stage`. Start a new script that asks whether the player wants to make their own character.
>
> ```blocks3
> when [space v] key pressed
> ask [Make your own character? Y/N?] and wait
> ```

Press the space key. Scratch should ask the question without changing any fields yet.

> [!TASK]
>
> Add an `if`{:class="block3control"} block that continues after either `yes` or `Y`.
>
> ```blocks3
> when [space v] key pressed
> ask [Make your own character? Y/N?] and wait
> +if <<(answer) = [yes]> or <(answer) = [Y]>> then
> end
> ```

> [!TASK]
>
> Inside the `if`{:class="block3control"} block, ask for a first name and store the answer in `name`{:class="block3variables"}.
>
> ```blocks3
> if <<(answer) = [yes]> or <(answer) = [Y]>> then
> +ask [What's your first name?] and wait
> +set [name v] to (answer)
> end
> ```

> [!TASK]
>
> Ask for the character's last name and store it in `name2`{:class="block3variables"}.
>
> ```blocks3
> set [name v] to (answer)
> +ask [What's your last name?] and wait
> +set [name2 v] to (answer)
> ```

Press space, answer `Y`, and enter both names. The two name readouts should update.

> [!TASK]
>
> Ask for a word that describes the character's vibe and store it in `style`{:class="block3variables"}.
>
> ```blocks3
> set [name2 v] to (answer)
> +ask [What's your style? What word describes your vibe?] and wait
> +set [style v] to (answer)
> ```

> [!TASK]
>
> Ask what the character does aboard the ship and store the answer in `role`{:class="block3variables"}.
>
> ```blocks3
> set [style v] to (answer)
> +ask [What's your role? What do you do aboard the ship?] and wait
> +set [role v] to (answer)
> ```

> [!TASK]
>
> Ask for a short character concept and store the answer in `concept`{:class="block3variables"}.
>
> ```blocks3
> set [role v] to (answer)
> +ask [What's your concept? Describe your character in one short sentence.] and wait
> +set [concept v] to (answer)
> ```

> [!TASK]
>
> Ask for a core number and explain what high and low values mean.
>
> ```blocks3
> set [concept v] to (answer)
> +ask [What's your core number (2–5)? High favours Logic; low favours Instinct.] and wait
> ```

> [!INFO]
>
> Checking both boundaries is **input validation**. It stops values outside the game's allowed 2–5 range from reaching the character sheet.

> [!TASK]
>
> Add a `repeat until`{:class="block3control"} loop after the question. It should stop only when the answer is greater than 1 **and** less than 6. Inside the loop, ask the player to try again.
>
> ```blocks3
> ask [What's your core number (2–5)? High favours Logic; low favours Instinct.] and wait
> +repeat until <<(1) < (answer)> and <(answer) < (6)>>
> ask [Please enter a number from 2 to 5.] and wait
> end
> ```

> [!TASK]
>
> After the loop, store the valid answer in `core#`{:class="block3variables"}.
>
> ```blocks3
> ask [What's your core number (2–5)? High favours Logic; low favours Instinct.] and wait
> repeat until <<(1) < (answer)> and <(answer) < (6)>>
> ask [Please enter a number from 2 to 5.] and wait
> end
> +set [core# v] to (answer)
> ```

Press space and make a character. Try entering `1` or `6` for the core number: Scratch should ask again. Enter 2, 3, 4, or 5 and the finished character should appear on the sheet.
