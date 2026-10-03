# Computer System Architecture: CPU Sim Lab

Simulating Mano's Basic Computer in CPU Sim 4.0.11.

## How to run
1. File → Open machine → `BasicComputer.cpu`
2. File → Open text → the program file
3. Ctrl+2 (Assemble & load), then Ctrl+R (Run)
4. When the console turns yellow, type a number and press Enter

---

## Practical 3: ADD two user-entered numbers

**Aim:** Read two numbers, add them and display the sum.

**Theory:** `INP` reads a number into AC. `STA A` saves it because the next `INP` overwrites AC. `ADD A` does AC ← AC + M[A]. `OUT` displays AC, `HLT` stops.

**Program**
```
INP
STA A
INP
ADD A
STA SUM
OUT
HLT
A:   .data 1 0
SUM: .data 1 0
```

**Memory map:** `F800 3007 F800 1007 3008 F400 7001 0000 0000`

**Output screenshots** (add your images to the `screenshots` folder)


![P3 program](screenshots/p03_program.png)




![P3 memory](screenshots/p03_memory.png)




![P3 output](screenshots/p03_output.png)



| Inputs | Output |
|---|---|
| 25, 17 | 42 |
| -40, 15 | -25 |
| -1, 1 | 0 |
| 30000, 10000 | -25536 (overflow) |

**Result:** 25 + 17 = 42.

---

## Practical 4: SUBTRACT two user-entered numbers

**Aim:** Read A and B and display A − B.

**Theory:** The Basic Computer has no SUB instruction. A − B = A + (B′ + 1). `CMA` gives B′, `INC` adds 1 to make −B, and `ADD A` adds A.

**Program**
```
INP
STA A
INP
CMA
INC
ADD A
STA DIFF
OUT
HLT
A:    .data 1 0
DIFF: .data 1 0
```

**Memory map:** `F800 3009 F800 7200 7020 1009 300A F400 7001 0000 0000`

**Output screenshots**


![P4 program](screenshots/p04_program.png)




![P4 memory](screenshots/p04_memory.png)




![P4 output](screenshots/p04_output.png)



| Inputs | Output |
|---|---|
| 18, 50 | -32 |
| 50, 18 | 32 |
| -7, -7 | 0 |
| 0, 1 | -1 |

**Result:** 18 − 50 = −32.
