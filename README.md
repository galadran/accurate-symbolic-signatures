# README

This repository contains the models and case studies for the paper: 

```
Seems Legit: Automated Analysis of Subtle Attacks on Protocols that use Signatures
Dennis Jackson, Cas Cremers, Katriel Cohn-Gordon, and Ralf Sasse.
ACM Conference on Computer and Communications Security, CCS 2019. 
```

## Folder Layout

# sts-mac-variants
 - Trad Models (Unbounded)
 - EQN Models (Split into Bounded and Unbounded)
 - SVS Models (Split into Bounded and Unbounded)

# case-studies
 - ACME (Containing Trad, Eqn and SVS models of Let's Encrypt)
 - DRKey (Containing Trad, Eqn and SVS models of DRKey)
 - WS Security (Containing Trad, Eqn and SVS models of WS Security Mutual Auth with X.509 Certs)

# example-models
    - The full attack finding model
    - The full SVS model 

## Note on Bounded and Unbounded
All verification happens in the Unbounded setting, while for some attack finding we use the Bounded setting for faster run times.

## Loading Complete Proofs

Each file contains comments which note how to run the file, the expected
running time and so on. For long running case studies, e.g. DRKey, we provide
complete Tamarin proofs, which can be loaded into Tamarin as normal files, but
Tamarin will automatically follow the stored proof steps, allowing for speedy verification.

## Timing Info

These case studies were produced on a 32 core server with 512 GB of RAM. However, none of the case studies should
require significant computing power, except in case of automatically finding the DRKey attack, which requires
45 minutes of wall clock time on our server. We provide a saved copy of the proof which can be loaded into Tamarin
and consequently the proof can be inspected even on a very low power machine.

## Notes on using Tamarin:

These case studies were produced using the following Tamarin version (the latest development version as of submission date):

$ tamarin-prover --version
tamarin-prover 1.5.0, (C) David Basin, Cas Cremers, Jannik Dreier, Simon Meier, Ralf Sasse, Benedikt Schmidt, ETH Zurich 2010-2018
Git revision: 0df3d09fca76fd9d340bd37b0151d71dea6ad106, branch: develop

Note that any later version of Tamarin should be able to load and use these files, however earlier versions may not. Specifically, there was a breaking change made by a prior v1.5.0 version, Git revision: 44d5ecbc2097ee99a22a01876e445047f2a31c54. Note that older release versions will not work.

Instructions for installing Tamarin from source can be found at https://tamarin-prover.github.io/
