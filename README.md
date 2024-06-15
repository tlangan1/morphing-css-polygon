## Notes

- This effort is to determine if I can control the animation using just custom @property css properties in the keyframes.
- Upon reflection, I believe this is asking for a conditional in css which is not really a thing so I will use a minimal amount of javascript to accomplish this.
- The initial idea is to change the --side-count with a timer.
- Wait a minute, I can use max in a calc which is a kind of conditional. See max-in-calc.html.

  - To Be Determined: If it works see the workbook for the calculations used in css formulas to abstract away the hardcoded `point` numbers as shown below:

    ```
    --x-1: calc(
        calc(sin(0 * 2 * pi / var(--side-count)) * var(--width) / 2)
        + var(--width) / 2
    );

    ```

    In this calculation the `0` in `sin(0 * 2 * pi / var(--side-count))` should be replaced with `???`
