[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/wFT7NEhx)
# Assignment 1: Wonky Button

Create a `WonkyButton.svelte` component that has the following behaviors:

1. The `WonkyButton` must accept a single (optional) prop named `value`.
    - The `value` must have a default value of `0`.
1. The text inside the `WonkyButton` must always depend on the latest `value`.
    - If the `value` is divisible by 3, the text must be `Fizz {value}`.
    - If the `value` is divisible by 5, the text must be `Buzz {value}`.
    - If the `value` is divisible by 3 and 5, the text must be `FizzBuzz {value}`.
    - Otherwise, the text must be `{value}`.
1. Whenever the button is clicked, the `value` is incremented by a random integer from `[0,10)`.
    - For debugging purposes, the generated random integer may be printed to the `console`.

> [!IMPORTANT]
> Please only edit the `src/routes/WonkyButton.svelte` file.
