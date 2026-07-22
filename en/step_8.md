## Add the bonus dice

Connect the P, E, and T switches so each active bonus rolls one extra die.

> [!TASK]
>
> Make a hidden variable called `prepared roll`{:class="block3variables"} **for all sprites**.

> [!TASK]
>
> Make a hidden variable called `expert roll`{:class="block3variables"} **for all sprites**.

> [!TASK]
>
> Make a hidden variable called `teamwork roll`{:class="block3variables"} **for all sprites**.

> [!TASK]
>
> Select the `dice roller` sprite. Reset the three new results to `0` after the main `roll`{:class="block3variables"} reset and before the `broadcast roll`{:class="block3events"} block.
>
> ```blocks3
> when this sprite clicked
> set [roll v] to (0)
> +set [prepared roll v] to (0)
> +set [expert roll v] to (0)
> +set [teamwork roll v] to (0)
> broadcast (roll v)
> ```

> [!TIP]
>
> Resetting unused results to `0` makes it clear later that those dice were not rolled this time.

> [!TASK]
>
> After `broadcast roll`{:class="block3events"}, check whether `prepared`{:class="block3variables"} is `1`. If it is, broadcast a new `prepared` message.
>
> ```blocks3
> broadcast (roll v)
> +if <(prepared) = (1)> then
> broadcast (prepared v)
> end
> ```

> [!TASK]
>
> Add another check that broadcasts a new `expert` message when `expert`{:class="block3variables"} is `1`.
>
> ```blocks3
> if <(prepared) = (1)> then
> broadcast (prepared v)
> end
> +if <(expert) = (1)> then
> broadcast (expert v)
> end
> ```

> [!TASK]
>
> Add a final check that broadcasts a new `teamwork` message when `teamwork`{:class="block3variables"} is `1`.
>
> ```blocks3
> if <(expert) = (1)> then
> broadcast (expert v)
> end
> +if <(teamwork) = (1)> then
> broadcast (teamwork v)
> end
> ```

> [!TASK]
>
> On the `die` sprite, drag the long rolling script onto the `prepared die` sprite. Immediately change its hat block to `when I receive prepared`{:class="block3events"}.

> [!TASK]
>
> In the copied script, replace every `roll`{:class="block3variables"} variable block with `prepared roll`{:class="block3variables"}. Keep the `core#`{:class="block3variables"} comparison unchanged.
>
> ```blocks3
> set [prepared roll v] to (costume [number v])
> if <(prepared roll) = (core#)> then
> play sound (Win v) until done
> broadcast (laser focus v)
> say (costume [number v]) for (5) seconds
> hide
> else
> say (costume [number v]) for (5) seconds
> hide
> end
> ```

Turn only **P** on and click **DICEROLL**. The main die and Prepared die should both roll.

> [!TASK]
>
> Drag the long rolling script from `die` onto `expert die`. Change its hat to `when I receive expert`{:class="block3events"}.

> [!TASK]
>
> In the Expert copy, replace the `roll`{:class="block3variables"} variable blocks with `expert roll`{:class="block3variables"}.
>
> ```blocks3
> set [expert roll v] to (costume [number v])
> if <(expert roll) = (core#)> then
> play sound (Win v) until done
> broadcast (laser focus v)
> say (costume [number v]) for (5) seconds
> hide
> else
> say (costume [number v]) for (5) seconds
> hide
> end
> ```

Turn **E** on. The Expert die should now join the roll.

> [!TASK]
>
> Drag the long rolling script from `die` onto `teamwork die`. Change its hat to `when I receive teamwork`{:class="block3events"}.

> [!TASK]
>
> In the Teamwork copy, replace the `roll`{:class="block3variables"} variable blocks with `teamwork roll`{:class="block3variables"}.
>
> ```blocks3
> set [teamwork roll v] to (costume [number v])
> if <(teamwork roll) = (core#)> then
> play sound (Win v) until done
> broadcast (laser focus v)
> say (costume [number v]) for (5) seconds
> hide
> else
> say (costume [number v]) for (5) seconds
> hide
> end
> ```

Turn **T** on. All four dice should now animate together.

> [!TASK]
>
> Drag the short movement script from `die` onto `prepared die`. Change its hat to `when I receive prepared`{:class="block3events"}.

> [!TASK]
>
> Drag the movement script onto `expert die` and change its hat to `when I receive expert`{:class="block3events"}.

> [!TASK]
>
> Drag the movement script onto `teamwork die` and change its hat to `when I receive teamwork`{:class="block3events"}.

Test several combinations of P, E, and T. The main die should always roll, and only the switched-on bonus dice should appear beside it.
