---
title: "Computer Architecture"
date: 2020-12-31 11:26:28 -0400
categories: Computer Architecture
---

# Machine Instruction
* Native language of processor
* Group of bits that tells computure to perform specific operation

# Register
* CPU에 있음
* 데이터/instruction의 임시 저장 공간
* 메인 메모리에 비해 빠르지만 비쌈

* 종류
1. General Purpose
>> 연산을 위해 사용
2. Special Purpose
>> Program Counter(다음 instruction의 주소를 저장하는 레지스터), Accumulator(연산의 결과를 저장), Instruction Register(메모리에서 불러온 지시 사항을 저장)

# ISA(Instruction Set Architecture)
* interface between hardware and low-level software
* 프로세서와 상호 작용을 하기 위한 정보

1. Processor's Instruction Set
2. Accessible Register Within Processor
3. Information necessary to interact with memory
4. How Processor reacts to interrupts from the programming view point

# Instruction
1. Opcode: operation to be performed
2. Operand: data's address

# Number of Operand
* Three
```
ADD A, B, C
A <- B + C
```

* Two
```
ADD A, B
A <- A + B
```

* One
```
ADD A
AC <- AC + A
```

* Zero
Push, Pop

# Addressing Mode
* Ways to specify location where an operand resides in memory or register

# Effective Address
* Actual address containing the referenced operand

1. Implied Mode: No explicit Address
2. Immediate Mode: Operand field contains the actual operand value
> ADD r3, r3, #4
3. Register Mode

--> Addressing Mode 다시 볼것

# Completeness
A computer should have a set of
instructions so that the user can construct machine
language programs to evaluate any function that is
known to be computable

Instruction Orthogonality: Do not overlap or perform same function

Instruction Type
1. Arithmetic/Logic - Modify data
2. Data Transfer - Copy data
3. Control Transfer (Program Control) - jump or branch

Arithmetic/Logic
- Integer Arithmetic Operation - add/subtract/divide/multiply/increment/decrement
- Logical Operation - Bitwise and, bitwise or, complement
- Shift - logic shift, arithmetic shift, rotate
- Floating point arithmetic operation

Data Transfer
- Memory -> Processor(Register)
- Processor(Register) -> Memory
- Register -> Register
- Between I/o Device and Register
- Memory -> Memory
- Between memory and I/O Device