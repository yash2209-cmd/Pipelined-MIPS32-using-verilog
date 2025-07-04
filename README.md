# Pipelined-MIPS32-using-verilog
Designing a 5 stage pipelined MIPS 32-bit RISC processor using Verilog.  
# Approach
To achieve this design, the components used were:
1. ALU
2. PC
3. INSTRUCTION MEMORY
4. DATA MEMORY
5. REGISTER BANK
6. MULTIPLEXER
7. LATCHES 
# Pipelining
Implemented the classic 5-stage pipelining used in many RISC architectures:
1. IF (Instruction Fetch)- Fetche the instruction from memory using PC.
2. ID (Instruction Decode)- Decode the instruction, read source register simultaneously, and generate control signals.
3. EX (Execute)- Perform ALU calculation or compute memory address for load/store.
4. MEM (Memory Access)- Access data memory (for load/store instruction).
5. WB (Write Back)- Write the result back to the register bank.
# The Instruction Set
The 32-bit instruction register is used as follows.  

      <--[31:26]--><--[25:21]--><--[20:16]--><--[15:11]--><--[10:0]-->     IR 
      <--op code--><--  rd   --><--  rs1  --><--  rs2  --><--unused-->     for register mode  
      <--op code--><--  rd   --><--  rs1  --><--  immediate data   -->     for immediate mode  
      
This particular processor supports R-type, I-type, Store/Load-type, and Branch-type instructions. The list is given below.  
opcode    -    instruction  
000000    -      add  
000001    -      sub  
000010    -      and   
000011    -      or  
000100    -      slt  
000101    -      mul  
111111    -      hlt  
001000    -      lw   
001001    -      sw  
001010    -      addi  
001011    -      subi  
001100    -      slti  
001101    -      bneqz  
001110    -      beqz  

  # Waveform for the testbench output
<img width="1033" alt="Screenshot 2025-06-30 at 10 32 21 AM" src="https://github.com/user-attachments/assets/68093b1e-c28a-4809-8cb2-6e474038d65b" />
Processor stops all operations after HALTED is executed.
  
