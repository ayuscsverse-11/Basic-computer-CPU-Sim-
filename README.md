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

![Hardware Modules Setup](<img width="1366" height="768" alt="Screenshot (16)" src="https://github.com/user-attachments/assets/b1b4743b-aca1-4600-8c97-e2255637d3b7" />
)
![Registers Configuration] (<img width="1366" height="768" alt="Screenshot (17)" src="https://github.com/user-attachments/assets/2db68c0b-3a72-4505-a470-3f745fcff1ce" />
)
![Creating Registers] (<img width="1366" height="768" alt="Screenshot (8)" src="https://github.com/user-attachments/assets/6d4522d2-80ed-456b-bee9-a922530c96a4" />)
![RAM and flag setup] (<img width="1366" height="768" alt="Screenshot (10)" src="https://github.com/user-attachments/assets/56ba8858-cc1e-443c-b548-d8609963f17a" />
) (<img width="1366" height="768" alt="Screenshot (9)" src="https://github.com/user-attachments/assets/08b0e9f3-10b4-402f-a523-b95c2c600de4" />
)
---

### Step 2: Field & Instruction Formats
*Defined fields (`opcode`, `addr`, `op`) and constructed instruction formats:*
- **Memory-Reference:** `[ opcode | addr ]` (4-bit opcode, 12-bit address)
- **Register-Reference:** `[ op ]` (16-bit register opcode field)

![Instruction Formats]()

---

### Step 3: Machine Instructions Configuration
*Defined all 20 instructions across Memory-Reference, Register-Reference, and I/O categories along with their respective micro-operation sequences.*

![Machine Instructions Setup]()

---

### Step 4: Fetch Sequence & Program Counter Configuration
*Configured the common Fetch-Decode sequence ($AR \leftarrow PC$, $IR \leftarrow M[AR]$, $PC \leftarrow PC + 1$) and set `PC` as the main instruction counter in options.*

![Fetch Sequence Setup]()

---

### Step 5: Testing & Verification
*Tested the machine file by loading a test file (`P03_ADD.a` or basic assembly code) using `Ctrl + 2`. Verified that machine code correctly populated in the RAM window.*

![RAM Verification Output]()

---

## Results
The `BasicComputer.cpu` machine architecture file was successfully created with 8 hardware registers, condition bits, 4096-word RAM, fetch logic, and all 20 machine instructions. The machine structure was verified and saved.
