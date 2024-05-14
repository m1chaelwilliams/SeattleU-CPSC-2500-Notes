[< Outline](UNIT-5/README.md)

# Datapath
[Go to Definition](Terms#^e05a11)

## Datapath Assumptions

- #### __Omits__ the following instructions:
	- `jalr`: left as an exercise
	- `in`, `out`: requires special __I/O__ hardware
- #### __Ignores Startup__:
	- Assumes __registers__, __memory__, and __PC__ have been properly initialized.
- #### __Initial datapath__ will be __single cycle__: ^75b372
	- Each instruction takes __one__ cycle.
___
## ALU

![[Screen Shot 2024-05-13 at 1.36.50 PM.png | 200]]

| Function | Operation   |
| -------- | ----------- |
| 000      | add         |
| 001      | sub         |
| 010      | and         |
| 011      | or          |
| 100      | not         |
| 101      | shf         |
| 110      | lli         |
| 111      |  lui        |

>[!Note]
>#### For `lui` instructions:
>- `IN1` contains current value of `Rd` (lower 8 bits)
>- `IN2` contains immediate value
>#### For `lli` instructions:
>- `IN1` is ignored (zeroed)
>- `IN2` contains immediate value

___
## Compute Building Blocks
- __Adder__ *only* adds numbers
- __Sign extension__ converts a smaller number in 16-bit number by extending the sign. (0101 0101 $\to$ 0000 0000 0101 0101).
- __Branch detection__ determines whether a branch should be taken or not based on a boolean value (1 $\to$ branch taken, 0 $\to$ branch not taken).

| Branch Type | Operation |
| ----------- | --------- |
| 000         | No branch |
| 001         | Not used  |
| 010         | `beq`     |
| 011         | `bne`     |
| 100         | `bgt`     |
| 101         | `bge`     |
| 110         | `blt`     |
| 111         | `ble`     |
## Register File

![[Screen Shot 2024-05-13 at 1.45.20 PM.png | 200]]

- Contains __8__ registers.
	- Each register is __16 bits__
- __Two__ read ports (Src1, Src2) and __one__ write port (D).
	- Contains the register number.
- __Always Enabled__