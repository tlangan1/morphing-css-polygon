## Notes

- This project demonstrates animation by referencing only custom @property CSS properties in the keyframes definition.
- In this implementation there is a single custom @property, `--side-count`.
- An ad hoc custom CSS property cannot accomplish this because without an @property definition the browser would have no way of ascertaining the `type` of the property and, hence, not know `the continuum through which the property should change`.
- Since the polygon function of the clip-path property takes a fixed number of coordinates one might think that implies a fixed number of sides but that is not true. Different shapes can be created by placing multiple points on the same line or at the same vertex.
- The CSS `max` function in the calc is a way to group coordinates together at a certain point.

  ```
  --x-1: calc(
      calc(
          sin(
              calc(max(var(--side-count) - (var(--max-sides) - 1), 0)) * 2 * pi /
                  var(--side-count)
              ) * var(--width) / 2
          ) + var(--width) / 2
  );
  --y-1: calc(
      calc(
          cos(
              calc(max(var(--side-count) - (var(--max-sides) - 1), 0)) * 2 * pi /
                  var(--side-count)
          ) * var(--width) / 2
      ) + var(--width) / 2
  );

  ```

- The only difference between this coordinate and the others is the `- 1` in the max function, `max(var(--side-count) - (var(--max-sides) - 1), 0)`. This is coordinate one. In coordinate 2 the `- 1` is replaced with `- 2`. In the nth coordinate it is replaced with `- n`.
