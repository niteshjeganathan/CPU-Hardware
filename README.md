# CPU-Hardware
## Components
### Control and Coordination Units
Control Unit 
  * Directs the flow of data, fetches instructions, decodes them, and controls execution.
  * Without CU, a CPU cannot function; it acts as the "brain" of the processor.
  * Manages instruction execution cycles in all modern CPUs.
Instruction Decoder
  * Decodes binary machine instructions into control signals.
  * Converts raw instructions into executable operations.
  * Used in CISC CPUs (x86) where instructions are complex.
Program Counter / Instruction Pointer
  * Holds the address of the next instruction.
  * Ensures sequential execution of instructions.
Instruction Register
  * Stores the currently fetched instruction
  * Holds instruction before execution
Microcode ROM
  * Stores low-level sequences for complex instructions.
  * Allows CPUs to execute CISC instructions.

### Execution and Processing Units
Arithmetic Logic Unit
  * Performs integer arithmetic and logic operations
  * Core computation unit
Floating Point Unit
  * Performs floating point arithmetic
  * Essential for scientific computing, 3D rendering
SIMD Unit / Vector Processing Unit (VPU)
  * Handles SIMD instructions
  * Enables parallel processing
Integer Execution Units
  * Dedicated Unit for integer operations
  * Offloads work from ALU
Scalar Processing Unit
  * Executes single-instruction, single-data
  * Core unit for standard instructions
Integer Multiply-Accumulate Unit (IMAC)
  * Performs multiply-add (MAC) operations
  * Boosts DSP (Digital Signal Processing) and AI
Tensor Processing Unit / Neural Processing Unit
  * Accelerates deep learning and AI workloads
  * Essential for AI workloads
Cryptographic Acceleration Unit
  * Handles encryption and decryption
  * Provides secure encryption with minimal CPU load
 
### Registers
General Purpose Registers (GPRs)
  * Hold temporary operands and data
  * Reduces memory access time
Vector Registers (SIMD Registers)
  * Store multiple data elements for SIMD execution
  * Enables parallel execution
Status Registers (Flags Registers)
  * Stores operation results (zero, carry, overflow)
  * Controls branching, comparisons
  * Used in ALU operations

### Caching and Memory Management
L1, L2, L3 Cache
  * Stores frequently accessed data
  * Improves memory access speed
Translation Lookaside Buffer (TLB)
  * Maps virtual to physical memory
  * Reduces memory lookup time
  * Used in virtual memory systems
Memory Management Unit
  * Handles virtual memory translation
  * Required for modern OS-based systems

### Execution Pipeline and Optimizations
Instruction Pipeline
  * Executes instruction in stages
  * Speeds up instruction throughput
Out of Order Execution
  * Executes instructions in a different order
  * Optimizes CPU cycles
Branch Predictor
  * Predicts if-else outcomes to avoid stalls
  * Improves CPU efficiency

### System Bus and Data Transfer
Data Bus
  * Transfers data between CPU and memory
Address Bus
  * Transfers memory addresses
    
### Power Management and Thermal Control
Power Gating
  * Shuts down unused parts of CPU
  * Saves power
Dynamic Frequency Scaling (DVFS)
  * Adjusts CPU frequency dynamically
Thermal Sensors
  * Detects CPU overheating
 
### Security and Virtualization
Secure Boot
  * Prevents unauthorized OS modifications
Hardware Virtualization (VT-x, AMD-V)
  * Allows running virtual machines
    
### Debugging and Performance Monitoring
JTAG Interface
  * Provides low-level debugging
  * Used by hardware engineers
Performance Monitoring Unit (PMU)
  * Tracks CPU performance metrics

## Miscelleanous 
### SIMD
* Single Instruction, Multiple Datapoints
* Parallel processing technique
* Performs same operation on multiple data points simultaneously
* Often implemented using vector registers, which store multiple data elements

```c++
// Without SIMD
for (int i = 0; i < 4; i++) {
  result[i] = a[i] + b[i];
}

// With SIMD
result = a + b
```

### TLB (Translation Lookup Buffer)
* Special cache used in the memory management unit
* Speed up virtual-to-physical address translation
* Stores recent mappings of virtual page numbers to physical frame numbers, reducing the need to access the page table in the main memory
* How it works
  * CPU generates a virtual address
  * MMU checks if page number is in TLB
    * TLB Hit: Corresponding physical address is present
    * TLB Miss: System must fetch the mapping from page table in RAM, update TLB and proceed. If not present, page fault.
    * Page Fault: After page table walk, if not found. It must be loaded from disk, causing more delay.

