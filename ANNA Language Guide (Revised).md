
The ANNA Guide provided by the school is subpar. Let's make something better.

# Keywords

- `and`
- `or`
- `add` adds the values in 2 registers and stores it in the target register. Overflow is not detected.
- `in` asks the user for a 16-bit numerical input. (-32,768 to 32,767)

# Example Uses
## `add`
```asm
in r1
in r2
add r3 r1 r1 ; add r1 and r1 and store value in r3
```
# Instruction General Layout

| Optcode      | Destination | Target 1 | Target 2 | Function Code |
| ------------ | ----------- | -------- | -------- | ------------- |
| `add` (0000) | `r1`        | `r2`     | `r3`     | 000           |
