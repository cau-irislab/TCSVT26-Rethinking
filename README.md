# Rethinking Facial Deformation Representation for Speech-Driven 3D Facial Animation

[Hyung Kyu Kim](https://github.com/kimhyungkyu-1208)<sup>1</sup>, Byungchan Hwang<sup>2</sup>, [Hak Gu Kim](https://www.irislab.cau.ac.kr)<sup>2</sup>

<sup>1</sup> Department of Imaging Science and Arts, Chung-Ang University, South Korea
<sup>2</sup> Department of Metaverse Convergence, Chung-Ang University, South Korea

📄 [Project Page](https://cau-irislab.github.io/TCSVT26-Rethinking/) | 📝 Paper (coming soon) | 💻 Code (coming soon)

## Overview

Despite remarkable advances in temporal modeling, speech-driven 3D facial animation still relies on a conventional vertex-space representation that flattens facial deformation into a one-dimensional vector — ignoring the geometric structure of facial deformation. We rethink facial deformation representation from a geometric perspective and propose **Facial Spectral Projection (FSP)**, a plug-in module that replaces the conventional vertex-wise projection with a deformation-aware spectral representation, built from a **deformation-aware Laplacian** that jointly captures facial geometry and speech-related deformation dynamics.

## Method

1. **Deformation Dynamics** — Per-vertex temporal variation of the deformation field is measured over training sequences and converted into edge deformation dynamics scores, which concentrate on the lips and jaw.
2. **Deformation-Aware Laplacian** — The scores modulate cotangent edge weights, yielding a Laplacian **L**<sub>D</sub> whose leading eigenvectors emphasize articulation-critical regions while preserving facial geometry.
3. **Facial Spectral Projection (FSP)** — Facial deformation is projected onto the first *K* eigenvectors (parameter-free) and mapped to the downstream feature space. FSP is a drop-in replacement for the conventional vertex-wise linear projection.

## Results

- Consistent articulation-accuracy improvements (FVE, LVE, LDTW) across four backbones — FaceFormer, CodeTalker, Mimic, StreamingTalker — on VOCASET and BIWI.
- Projection parameters reduced by **20×** on VOCASET (15.4M → 0.79M) and **91×** on BIWI (71.8M → 0.79M), decoupling model size from mesh resolution.
- Spectral analyses show articulatory deformation concentrates in the low- and mid-frequency components of the deformation-aware basis, generalizing across FLAME, BIWI, and ARKit topologies.
