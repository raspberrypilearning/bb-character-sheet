## Switch on bonus dice

Turn the Prepared, Expert, and Teamwork buttons into switches that remember which bonus dice to roll.

> [!TASK]
>
> Make a variable called `prepared`{:class="block3variables"} **for all sprites**. Untick its checkbox so the helper value stays hidden.

> [!TASK]
>
> Make a hidden variable called `expert`{:class="block3variables"} **for all sprites**.

> [!TASK]
>
> Make a hidden variable called `teamwork`{:class="block3variables"} **for all sprites**.

> [!INFO]
>
> Each switch stores either `0` for off or `1` for on. This two-state value is sometimes called a **Boolean flag**.

> [!TASK]
>
> Select the `prepared` sprite. Start its setup script with a `when green flag clicked`{:class="block3events"} block.
>
> <p align="center"><img src="images/prepared-toggle.png" alt="The green Prepared button marked P." width="96"></p>
>
> ```blocks3
> when green flag clicked
> ```

> [!TASK]
>
> Add a block that sets the button to 30% size.
>
> ```blocks3
> when green flag clicked
> +set size to (30) %
> ```

> [!TASK]
>
> Reset `prepared`{:class="block3variables"} to `0` and switch to the red `button2` costume, so the value and the picture both begin off.
>
> ```blocks3
> when green flag clicked
> set size to (30) %
> +set [prepared v] to (0)
> +switch costume to (button2 v)
> ```

> [!TASK]
>
> Start a second script with a `when this sprite clicked`{:class="block3events"} block.
>
> ```blocks3
> when this sprite clicked
> ```

> [!TASK]
>
> Add an `if else`{:class="block3control"} block. When `prepared`{:class="block3variables"} is `0`, change it to `1`.
>
> ```blocks3
> when this sprite clicked
> +if <(prepared) = (0)> then
> set [prepared v] to (1)
> else
> end
> ```

> [!TASK]
>
> In the first branch, switch to `button1` and say `on`.
>
> ```blocks3
> if <(prepared) = (0)> then
> set [prepared v] to (1)
> +switch costume to (button1 v)
> +say [on] for (2) seconds
> else
> end
> ```

Click the **P** button when `prepared`{:class="block3variables"} is `0`. It should turn green and say `on`.

> [!TASK]
>
> Fill the `else`{:class="block3control"} branch. Set `prepared`{:class="block3variables"} to `0`, switch to `button2`, and say `off`.
>
> ```blocks3
> if <(prepared) = (0)> then
> set [prepared v] to (1)
> switch costume to (button1 v)
> say [on] for (2) seconds
> else
> +set [prepared v] to (0)
> +switch costume to (button2 v)
> +say [off] for (2) seconds
> end
> ```

Click **P** several times. It should alternate between on and off every time.

> [!TASK]
>
> Right-click the completed click script and choose **Duplicate**. Remove the `when this sprite clicked`{:class="block3events"} block from the copy.

> [!TASK]
>
> Put a `when p key pressed`{:class="block3events"} block on top of the copied switch code.
>
> ```blocks3
> when [p v] key pressed
> if <(prepared) = (0)> then
> set [prepared v] to (1)
> switch costume to (button1 v)
> say [on] for (2) seconds
> else
> set [prepared v] to (0)
> switch costume to (button2 v)
> say [off] for (2) seconds
> end
> ```

Press the P key. The Prepared switch should behave exactly as it does when clicked.

> [!TASK]
>
> Drag the green flag setup script onto the `teamwork2` sprite in the sprite list. In the copy, replace `prepared`{:class="block3variables"} with `expert`{:class="block3variables"}.

> [!INFO]
>
> The starter sprite named `teamwork2` is the **Expert** button marked E. The sprite named `teamwork` is the **Teamwork** button marked T.

> [!TASK]
>
> Drag the green flag setup script onto the `teamwork` sprite. In this copy, replace `prepared`{:class="block3variables"} with `teamwork`{:class="block3variables"}.

Click the green flag. All three switches should be red and their hidden values should be `0`.

> [!TASK]
>
> Drag the Prepared click script onto `teamwork2`. In the copied script, replace every `prepared`{:class="block3variables"} with `expert`{:class="block3variables"}.
>
> <p align="center"><img src="images/expert-toggle.png" alt="The green Expert button marked E." width="96"></p>
>
> ```blocks3
> when this sprite clicked
> if <(expert) = (0)> then
> set [expert v] to (1)
> switch costume to (button1 v)
> say [on] for (2) seconds
> else
> set [expert v] to (0)
> switch costume to (button2 v)
> say [off] for (2) seconds
> end
> ```

> [!TASK]
>
> Drag the Prepared keyboard script onto `teamwork2`. Change its key to `e`{:class="block3sensing"} and replace every `prepared`{:class="block3variables"} with `expert`{:class="block3variables"}.

Click the **E** button, then press the E key. Both should switch Expert between on and off.

> [!TASK]
>
> Drag the Prepared click script onto `teamwork`. Replace every `prepared`{:class="block3variables"} with `teamwork`{:class="block3variables"}.
>
> <p align="center"><img src="images/teamwork-toggle.png" alt="The green Teamwork button marked T." width="96"></p>

> [!TASK]
>
> Drag the Prepared keyboard script onto `teamwork`. Change its key to `t`{:class="block3sensing"} and replace every `prepared`{:class="block3variables"} with `teamwork`{:class="block3variables"}.

Try each button and keyboard shortcut. P, E, and T should now independently remember whether the character is Prepared, an Expert, or receiving Teamwork.

> [!TIP]
>
> In the game, being prepared means having the right tool or plan. Relevant expertise adds another die, and a successful helper can add the Teamwork die.
