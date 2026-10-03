# Basic-computer-CPU-Sim-
# Practical 1: Creation of Machine Based on Basic Computer Architecture

## Objective
To design, configure, and verify the hardware modules, instruction formats, and micro-operations of M. Morris Mano's Basic Computer architecture in CPU Sim 4.0.11.

---

## Hardware Specifications
- **Word Length:** 16 bits
- **RAM Size:** 4096 words (Cell size: 16 bits)
- **Address Bus Width:** 12 bits
- **Registers Defined (8 Total):**
  - `PC` (12 bits) - Program Counter
  - `AR` (12 bits) - Address Register
  - `IR` (16 bits) - Instruction Register
  - `AC` (16 bits) - Accumulator
  - `DR` (16 bits) - Data Register
  - `TR` (16 bits) - Temporary Register
  - `INPR` (8 bits) - Input Register
  - `OUTR` (8 bits) - Output Register
- **Condition Bits / Flags:**
  - `E` (1 bit) - Extension/Carry bit
  - `S` (1 bit) - Start/Halt flag

---

## Implementation Steps & Screenshots

### Step 1: Hardware Modules Setup
*Configured the 8 registers, single-bit flags, and 4096-word RAM.*

<img width="1366" height="768" alt="Screenshot (16)" src="https://github.com/user-attachments/assets/b1b4743b-aca1-4600-8c97-e2255637d3b7" />
<img width="1366" height="768" alt="Screenshot (17)" src="https://github.com/user-attachments/assets/2db68c0b-3a72-4505-a470-3f745fcff1ce" /><img width

[Creating Registers] <img width="1366" height="768" alt="Screenshot (8)" src="https://github.com/user-attachments/assets/6d4522d2-80ed-456b-bee9-a922530c96a4" />
[RAM and flag setup] <img width="1366" height="768" alt="Screenshot (10)" src="https://github.com/user-attachments/assets/56ba8858-cc1e-443c-b548-d8609963f17a" />
 <img width="1366" height="768" alt="Screenshot (9)" src="https://github.com/user-attachments/assets/08b0e9f3-10b4-402f-a523-b95c2c600de4" />
 
---

### Step 2: Microinstructions & Instruction fields .
Configure the low-level register-transfer operations for the machine architecture.

* **Open Dialog:** Navigate to the top menu bar and choose Modify -> Microinstructions to open the execution logic window.
* **Select Classes:** Access the Type of Microinstruction dropdown menu to choose between operational categories.
* **Generate Fields:** Click the New button to add distinct configuration rows for TransferRtoR, Arithmetic, Logical, Shift, Increment, and MemoryAccess instruction classes.
* **Map Operations:** Fill out the data columns for each row to define the source registers, destination registers, and bit widths.
* **Save Configurations:** Click OK. 

<img width="1366" height="734" alt="Screenshot (19)" src="https://github.com/user-attachments/assets/8195b599-f9b2-4533-afc9-508e9f7a49fa" />
<img width="1366" height="768" alt="Screenshot (11)" src="https://github.com/user-attachments/assets/0bdcdf39-da2d-4d47-9d20-41fad516c368" />
<img width="1366" height="768" alt="Screenshot (12)" src="https://github.com/user-attachments/assets/ab43ec53-558e-4a27-b8a3-3e76a4234e04" />

*Defined fields (`opcode`, `addr`, `op`) and constructed instruction formats:*
- **Memory-Reference:** `[ opcode | addr ]` (4-bit opcode, 12-bit address)
- **Register-Reference:** `[ op ]` (16-bit register opcode field)
  Instruction fields
<img width="1366" height="734" alt="Screenshot (21)" src="https://github.com/user-attachments/assets/7c1649d3-2c3a-4c44-81bc-2ab51d2f67b2" />
<img width="1366" height="768" alt="Screenshot (18)" src="https://github.com/user-attachments/assets/cb5a2716-7aa3-4380-96cf-bb6443531639" />
<img width="1366" height="768" alt="Screenshot (22)" src="https://github.com/user-attachments/assets/0f0c9555-29ed-4ee3-953b-49139e8650d4" />


---

### Step 3: Machine Instructions Configuration
*Defined all 20 instructions across Memory-Reference, Register-Reference, and I/O categories along with their respective micro-operation sequences.*

Machine Instructions Setup
<img width="1366" height="713" alt="Screenshot (23)" src="https://github.com/user-attachments/assets/60bf68c8-c166-4a02-9cab-2ebcd823193d" />
<img width="959" height="678" alt="Screenshot (3)" src="https://github.com/user-attachments/assets/506a9d6a-284d-4b0b-bd77-5c0cff1110af" />
<img width="1366" height="768" alt="Screenshot (4)" src="https://github.com/user-attachments/assets/81f2b350-de87-4218-8eec-37eeedc67d8d" />
<img width="1366" height="768" alt="Screenshot (15)" src="https://github.com/user-attachments/assets/094005f5-4930-4404-9888-49fe8a25bfe1" />
<img width="1366" height="768" alt="Screenshot (5)" src="https://github.com/user-attachments/assets/6baf0917-f7b0-42ef-8573-8a0682ea393d" />
<img width="1366" height="768" alt="Screenshot (13)" src="https://github.com/user-attachments/assets/34f990ac-444c-44a5-998f-c8ea25a42685" />
<img width="1366" height="768" alt="Screenshot (14)" src="https://github.com/user-attachments/assets/a77fec15-6c23-48c4-bde2-728b32f5700e" />



---

### Step 4: Fetch Sequence & Program Counter Configuration
*Configured the common Fetch-Decode sequence (AR<-PC, IR<- M[AR],PC<-PC + 1) and set `PC` as the main instruction counter in options.*

[Fetch Sequence Setup]
<img width="1302" height="730" alt="Screenshot (26)" src="https://github.com/user-attachments/assets/ec5766a9-e2ab-4cb2-bc69-b1168b1c3313" />
<img width="1366" height="717" alt="Screenshot (27)" src="https://github.com/user-attachments/assets/0d1f160d-f46f-4ca2-846b-4d26e1c19a10" />


---

### Step 5: Testing & Verification
*Tested the machine file by loading a test file (basic assembly code) using `Ctrl + 2`. Verified that machine code correctly populated in the RAM window.*
<img width="1366" height="768" alt="Screenshot (28)" src="https://github.com/user-attachments/assets/fc089148-950b-4e4a-9a20-170ee6af7bb9" />
[RAM Verification Output]
<img width="1366" height="717" alt="Screenshot (6)" src="https://github.com/user-attachments/assets/a562dd14-68fa-4fcb-aa1a-914b12490e9c" />



---

## Results
The `BasicComputer.cpu` machine architecture file was successfully created with 8 hardware registers, condition bits, 4096-word RAM, fetch logic, and all 20 machine instructions. The machine structure was verified and saved.


# Practical 2: Fetch Routine

Short reference guide for the instruction cycle hardware sequence.

---

##  Step 1: Configure Fetch Sequence
* Click **Modify** -> **Fetch Sequence...**
* Drag these items to the left pane in this exact order:
  1. `PC->AR` (from transferRtoR)
  2. `M[AR]->IR` (from memoryAccess)
  3. `PC+1->PC` (from increment)
  4. `IR(0-11)->AR` (from transferRtoR)
  5. `decode-IR` (from decode)
* Click **OK**.
* Click **File** -> **Save machine**.

---

##  Step 2: Microinstruction Parameters
* Click **Modify** -> **Microinstructions...**
* Locate `IR(0-11)->AR` under *TransferRtoR* and verify:
  * **`srcStartBit`**: `0`
  * **`destStartBit`**: `0`
  * **`numBits`**: `12`

---

## Step 3: Verification Trace Table
* Open code file (`P1.a`) and press **Ctrl + 2** to load it into RAM.
* Set Registers data selector to **Unsigned Dec**.
* Press **Ctrl + D** to enter Debug Mode.
* Click **Step by Micro** exactly **5 times** slowly to trace the register values:

| Click | Action | AR Register | PC Register | IR Register |
| :---: | :--- | :---: | :---: | :---: |
| **0** | Initial State | 0 | 0 | 0 |
| **1** | `PC -> AR` | 0 | 0 | 0 |
| **2** | `M[AR] -> IR` | 0 | 0 | 63488 |
| **3** | `PC + 1 -> PC` | 0 | 1 | 63488 |
| **4** | `IR(0-11) -> AR` | **2048** | 1 | 63488 |
| **5** | `decode-IR` | 2048 | 1 | 63488 |

---

##  Step 4:  Screenshots
*Fetch Sequence Configuration*
<img width="1366" height="768" alt="Screenshot (29)" src="https://github.com/user-attachments/assets/43da3e72-dcd7-4341-9607-edc00bbbe87a" />
<img width="1366" height="768" alt="Screenshot (30)" src="https://github.com/user-attachments/assets/a2d752f8-531d-4909-b20d-2881fe882bde" />
<img width="1366" height="768" alt="Screenshot (31)" src="https://github.com/user-attachments/assets/4143a441-7ded-4d40-9da1-cfb50d0030b0" />
<img width="1366" height="768" alt="Screenshot (32)" src="https://github.com/user-attachments/assets/c8496e2d-43a2-42a2-aa59-b04a6db3a403" />
<img width="1366" height="768" alt="Screenshot (34)" src="https://github.com/user-attachments/assets/148dcdf3-45ce-4a72-9ca0-223ca42718d6" />

*Register State Output Screen*
<img width="1366" height="768" alt="Screenshot (37)" src="https://github.com/user-attachments/assets/5aa1a93b-50bd-42c6-8b8d-4ffce70704c7" />

# Practical 3 & 4.


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
