# Overview
The [verified zk(E)VM project](https://verified-zkevm.org/) is an Ethereum Foundation project aiming to accelerate the use of formal verification in the context of RISC-V [zkVMs](https://github.com/rkdud007/awesome-zkvm), with the aim of making formally verified bug-free zk(E)VMs a possibility by 2027. This repository is intended to provide an overview of the work done as part of this project as it becomes public.

A zk(E)VM is a zkVM on which an EVM, compiled to the zkVM's underlying ISA (in our case, RISC-V), runs. To formally verify a zk(E)VM, work is divided into three tracks:
- The zkVM track, which aims to verify the implementation of the RISC-V CPU, the arithmetization and circuits. This track also includes verifying the precompiles that are essential to the zkVM's performance.
- The EVM track, which aims to verify that a chosen implementation of the EVM, compiled to RISC-V, correctly implements a formal EVM specification.
- The Cryptography track, which aims to verify the specifications and security proofs of the zkVM's proof systems, as well as their implementation. This track also includes verifying the Ethereum on-chain verifier.

For more information about the project, including the availability of grants and bounties, please see the project [website](https://verified-zkevm.org/).

# Repositories featuring work done as part of this project
- [Sail](https://github.com/rems-project/sail) is a language for defining the instruction-set architecture (ISA) semantics of processors. A Lean backend is under development by a joint team comprising of the [University of Cambridge](https://www.cst.cam.ac.uk/), [Galois](https://www.galois.com/), and [Lindy Labs](https://lindylabs.net/), as part of this project. This will be used to extract the [formal specification of the RISC-V architecture](https://github.com/riscv/sail-riscv) to Lean. (Coq, Isabelle, and HOL4 backends already exist.) The current state of the RISC-V semantics extracted to Lean can be found [here](https://github.com/opencompl/sail-riscv-lean/).
- [cLean](https://github.com/Verified-zkEVM/clean) is an embedded Lean DSL for writing zk circuits, targeting AIR arithmetization. It is being developped by [zkSecurity](https://zksecurity.xyz/).
- [zkLib](https://github.com/Verified-zkEVM/ZKLib) is a library aiming to provide a modular and composable framework for formally verifying cryptographic proof systems (e.g. SNARKs) based on Interactive Oracle Proofs. It is being developped by [Quang Dao](https://github.com/quangvdao), [Devon Tuma](https://github.com/dtumad), and [zkSecurity](https://zksecurity.xyz/). Related work is also taking place in [VCV-io](https://github.com/dtumad/VCV-io).
