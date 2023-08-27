---
title: Journeying into the Cryptographic Wonderland - Secure Multi-Party Computation Unveiled
published: true
---

Hello, dear cypherpunks, tech nerds, and curious onlookers! Today, I'm going to take you on a captivating journey through the labyrinth of Secure Multi-Party Computation (MPC). If that sounds like a mouthful, don't worry! By the end of this read, you'll be casually dropping MPC references at your next dinner party (or Zoom call).

## Introduction

In the vast expanse of cryptography, [MPC](https://en.wikipedia.org/wiki/Secure_multi-party_computation) shines brightly. At its heart, MPC, a cryptographic technique, allows multiple parties to compute functions over their inputs, ensuring each party's input remains private.

<div style="text-align:center">
  <img src="/assets/images/secure-mpc/mpc-basic.png" alt="MPC basic diagram" style="width:70%; height:auto;">
</div>


Picture this: You and a bunch of friends want to find out who's the richest without actually revealing your bank balances. Awkward, right? But with MPC, you can do just that. It's the art of computing a function over everyone's input without revealing any individual input. It's like each of you whispers a secret into the wind, the wind does some magic, and then it whispers back the answer. The original secrets? They remain secrets.

## A Step Back in Time: The Genesis of MPC

The world of cryptography was set ablaze in the 1980s. Beyond the big hair and catchy tunes, this decade was about cryptographic epiphanies. The seeds of MPC were sown during this vibrant period. Visionaries like [Shafi Goldwasser](https://en.wikipedia.org/wiki/Shafi_Goldwasser), [Silvio Micali](https://en.wikipedia.org/wiki/Silvio_Micali), and [Charles Rackoff](https://en.wikipedia.org/wiki/Charles_Rackoff) were at the forefront, introducing the world to the groundbreaking [GMW protocol](https://eprint.iacr.org/2004/136.pdf).

But no history of MPC would be complete without acknowledging another giant: [Andrew Yao](https://en.wikipedia.org/wiki/Andrew_Yao). It was Yao who first dreamt of a world where two parties could engage in computations on private data, a dream he articulated in his [seminal paper](https://dl.acm.org/doi/10.1145/800057.808675). This idea, which came to be known as "Yao's Millionaires' Problem," was the spark that would ignite the MPC revolution.

As the calendar pages turned, the 90s and 2000s bore witness to MPC's evolution. This era was marked by the creation of more streamlined protocols, fueled by theoretical breakthroughs and the unstoppable march of computational prowess. Fast-forward to today, with data multiplying like never before and privacy concerns reaching fever pitch, MPC stands tall. It's a testament to the vision of its pioneers and the relentless refinement of subsequent generations. We're now in an age where MPC's capabilities reach efficiency and security heights that once lived only in the realm of cryptographic fantasy.

<div style="text-align:center">
  <img src="/assets/images/secure-mpc/mpc-speed.png" alt="MPC improvements" style="width:66%; height:auto;">
</div>
<br />

## Unmasking the Enigma: How does MPC Work?

At MPC's core lies the principle of 'divide and conquer'. Inputs are divided, or 'secret-shared', among participants. Computations occur on these divided inputs. The results, when combined, mirror what you'd get with the original inputs, but here's the kicker - the original inputs always remain concealed!

## The Grand Scripts: Protocols Powering MPC

MPC's prowess is orchestrated by several pivotal protocols:

- **Yao's Garbled Circuits**: Yao’s method involves one party (the "garbler") preparing a "garbled" version of a function, while the other party (the "evaluator") computes on this obscured function using specially prepared input. The magic lies in the evaluator obtaining the output without ever truly understanding the function's internals or the garbler's input.

- **BGW & CCD Protocols**: Named after their inventors ([Ben-Or, Goldwasser & Wigderson](https://dl.acm.org/doi/10.1145/28395.28420) and [Chaum, Crépeau & Damgård](https://link.springer.com/chapter/10.1007/0-387-34805-0_22) respectively), these protocols are designed for the multi-party setting. They operate on the principle of polynomial secret sharing and are resilient against a minority of malicious parties.

- **Shamir's Secret Sharing**: The brainchild of [Adi Shamir](https://en.wikipedia.org/wiki/Adi_Shamir), this method divides data into parts. It ensures that only a predetermined subset of these parts, called shares, can reconstruct the original data. While it forms the foundation of many MPC protocols, its beauty lies in its simplicity and mathematical elegance.

- **SPDZ (Speedz)**: Pronounced as "speeds", this is a more modern protocol. It combines the best of both worlds: the efficiency of Yao's Garbled Circuits and the robustness of Shamir's Secret Sharing. It also incorporates advanced cryptographic constructs like [Somewhat Homomorphic Encryption](https://en.wikipedia.org/wiki/Homomorphic_encryption#Somewhat_homomorphic_encryption) to enhance security and efficiency.

## Navigating Threats: The Realm of Adversaries

The world of MPC is like a mystical land, filled with treasures but also fraught with dangers. Two primary adversarial models are always lurking:

1. **Semi-Honest**: Imagine adversaries who play by the book, never breaking rules but always eavesdropping, hoping to gain some insights. They won't disrupt the protocol but will glean as much information as they can from accessible data.
2. **Malicious**: These are the tricksters of the MPC world. They can deviate from agreed protocols, introduce misleading data, or even attempt to corrupt the process. Defending against them requires rigorous cryptographic checks and validations.
3. **Covert**: Somewhere between semi-honest and malicious, these adversaries might cheat but only if they believe they won't get caught. This model is a pragmatic middle-ground, offering a balance between security and efficiency.

The choice of security model often forms a trade-off matrix: stronger security usually comes at the expense of efficiency. However, recent advancements, especially in the domain of [Zero-Knowledge Proofs](https://en.wikipedia.org/wiki/Zero-knowledge_proof) and [Homomorphic Encryption](https://en.wikipedia.org/wiki/Homomorphic_encryption), are narrowing this gap, allowing us to achieve robust security without compromising on computational performance.

## Applications: MPC in the Real World

- **Private Voting Systems**: Ensuring a person's vote remains confidential.
- **Secure Data Mining**: Extracting knowledge from databases without accessing raw data.
- **Private Benchmarking**: Companies compare metrics without revealing proprietary data.
- **Privacy-Preserving Medical Research**: Researchers access findings without seeing individual patient data.

## Now, Let's Get Personal for a Moment

In my startup, we've harnessed MPC's might to craft [zkSNARKs](https://en.wikipedia.org/wiki/Non-interactive_zero-knowledge_proof), ensuring no single party knows the full witness data. This not only ensures privacy but also cuts overheads traditionally associated with MPC.

<div style="text-align:center">
  <img src="/assets/images/secure-mpc/zkp-basic.png" alt="ZK Proof basic" style="width:50%; height:auto;">
</div>

zkSNARKs, or "Zero-Knowledge Succinct Non-Interactive Argument of Knowledge," are cryptographic proofs that allow one party to prove to another that they know a certain piece of information without revealing it. They are a marvel in the realm of privacy, enabling confidentiality in many decentralized applications. However, generating these proofs can be resource-intensive. Enter [**zkHub**](https://zkHub.dev). By utilizing Multi-Party Computation (MPC), we are decentralizing the proof generation process. This means we're splitting sensitive data across different servers, ensuring that as long as one server remains uncompromised, the data's privacy is intact. The result? Efficient and privacy-preserving generation of zkSNARKs, transforming the landscape of cryptographic proof generation.

## The Road Ahead

With the sheer depth and expanse of MPC, it's becoming clear that one blog post won't suffice. So, consider this a prologue. In subsequent posts, I'll dive "depth-first" into the intricacies of MPC, sharing insights, challenges, and the thrills of this cryptographic journey.

## Acknowledgments

A major shout-out to the book "[A Pragmatic Introduction to Secure Multi-Party Computation](https://securecomputation.org/docs/pragmaticmpc.pdf)". If this blog was an appetizer, consider the book a lavish 7-course meal, intricately detailing the world of MPC. It's this very read that spurred me to craft this blog series, sharing my take on the subject and its fascinating intricacies.
