# Rethinking Facial Deformation Representation for Speech-Driven 3D Facial Animation

> 📝 **Under review at IEEE TCSVT**

[Hyung Kyu Kim](https://github.com/kimhyungkyu-1208)<sup>1</sup>, Byungchan Hwang<sup>2</sup>, [Hak Gu Kim](https://www.irislab.cau.ac.kr)<sup>2</sup>

<sup>1</sup> Department of Imaging Science and Arts, Chung-Ang University, South Korea
<sup>2</sup> Department of Metaverse Convergence, Chung-Ang University, South Korea

📄 [Project Page](https://cau-irislab.github.io/TCSVT26-Rethinking/) | 📝 Paper (coming soon) | 💻 Code (coming soon)

## Overview

Most speech-driven 3D facial animation frameworks encode facial motion by flattening per-vertex displacements into a 1-d vector and projecting it through a fully connected layer — discarding the geometric relationships among vertices. We revisit this design and propose **Facial Spectral Projection (FSP)**, a geometry-aware spectral representation that encodes facial deformation with respect to the eigenbasis of a **deformation-aware Laplacian** defined on the facial mesh.

## Method

1. **Deformation Dynamics** — Per-vertex temporal variation of the deformation field is measured over training sequences and converted into edge deformation dynamics scores, which concentrate on the lips and jaw.
2. **Deformation-Aware Laplacian** — The scores modulate cotangent edge weights, yielding a Laplacian **L**<sub>D</sub> whose leading eigenvectors emphasize articulation-critical regions while preserving facial geometry.
3. **Facial Spectral Projection (FSP)** — Facial deformation is projected onto the first *K* eigenvectors (parameter-free) and mapped to the downstream feature space. FSP is a drop-in replacement for the conventional vertex-wise linear projection.

## Results

- Consistent articulation-accuracy improvements (FVE, LVE, LDTW) across four backbones — FaceFormer, CodeTalker, Mimic, StreamingTalker — on VOCASET and BIWI.
- Projection parameters reduced by **20×** on VOCASET (15.4M → 0.79M) and **91×** on BIWI (71.8M → 0.79M), decoupling model size from mesh resolution.
- Spectral analyses show articulatory deformation concentrates in the low- and mid-frequency components of the deformation-aware basis, generalizing across FLAME, BIWI, and ARKit topologies.

## Citation

```bibtex
@article{kim2026rethinking,
  author  = {Kim, Hyung Kyu and Hwang, Byungchan and Kim, Hak Gu},
  title   = {Rethinking Facial Deformation Representation for Speech-Driven 3D Facial Animation},
  note    = {Under review at IEEE Transactions on Circuits and Systems for Video Technology},
  year    = {2026}
}
```
