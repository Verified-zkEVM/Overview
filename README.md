# Overview

The [verified zk(E)VM project](https://verified-zkevm.org/) is an Ethereum Foundation project aiming to accelerate the use of formal verification in the context of RISC-V [zkVMs](https://github.com/rkdud007/awesome-zkvm), with the aim of making formally verified bug-free zk(E)VMs a possibility by 2027. This repository is intended to provide an overview of the work done as part of this project as it becomes public.

For more information about the project, including the availability of grants and bounties, please see the project [website](https://verified-zkevm.org/).

## zkVM Track

The zkVM track aims to formally verify the zkVM constraints, developing the following to achieve this.
- A Lean backend for [Sail](https://github.com/rems-project/sail), a language for defining ISAs, including the [formal specification of the RISC-V architecture](https://github.com/riscv/sail-riscv).
  This backend now exists, and the RISC-V specification can be extracted into Lean (see [here](https://github.com/opencompl/sail-riscv-lean-executable) and [here](https://github.com/opencompl/sail-riscv-lean)), with more prolishing and improvements expected.
  (See also this hand-written rewrite of the Sail RISC-V specification into pure bit vector only operations.)
  RISC-V are expected to be verified against a reliable RISC-V specification this way.
- [LLZK](https://github.com/Veridise/llzk-lib), a MLIR dialect for circuits, intended to serve as a unifying layer for circuits written in any of the many existing DSLs,
  from which SMT based tools (e.g. Picus) as well other security or performance tooling can be applied,
  as well as supporting interaction with proof assistants such as Lean (see [Lean-MLIR](https://github.com/opencompl/lean-mlir)) and other proof assistants.
- Lean circuit DSLs, such as [cLean](https://github.com/Verified-zkEVM/clean) (for AIR arithmetization, think plonky3) and [zkLean](https://github.com/GaloisInc/zk-lean) (for R1CS arithemtization, think Jolt),
  in which circuits can be formally reasoned about and proven sound, complete, and correct.

## EVM Track

The work on the EVM track focuses on establishing the correctness of the EVM running on a target zkVM.

The current focus of this track is the verification of revm against Runtime Verification's [KEVM semantics](https://github.com/runtimeverification/evm-semantics); see the related [zkEVM harness](https://github.com/runtimeverification/zkevm-harness).
In parallel to this, [the KEVM semantics are also being shown equivalent to Nethermind's Lean EVM model](https://github.com/runtimeverification/evm-equivalence), using a [Lean backend for K]([klean](https://github.com/runtimeverification/k/tree/master/pyk/src/pyk/klean)) developed as part of this project.

## Cryptography Track

The cryptography track focuses on [ArkLib](https://github.com/Verified-zkEVM/ArKLib), a library aiming to provide a modular and composable framework for formally verifying cryptographic proof systems (e.g. SNARKs) based on Interactive Oracle Proofs,
and [VCV-io](https://github.com/dtumad/VCV-io), a framework for reasoning about computations in Lean.

The current aim of this work is to
- Fomalize proof systems and their security theorems, producing exectuable specifications that are directly related to security proofs;
- Refine these executable specifications with optimisations which are applied to production code written in Rust;
- Verify the correctness of Rust implementations of verifiers against these executable specifications.

To this end, a Lean backend for [hax](https://github.com/cryspen/hax), a tool for high assurance translations of a large subset of Rust into formal languages is also being developed as part of this project.


