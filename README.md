# TopoGeoScore: Implementation Scope and Current Project Status
TopoGeoScore Research and Experiment.

Abstract:

Out-of-distribution (OOD) robustness is difficult to diagnose when target-domain labels are unavailable. We consider a more restrictive source-only variant of unsupervised accuracy estimation: selecting robust checkpoints using only source-domain representations, with no target samples or target labels. We propose TopoGeoScore, a source-only geometric scorer for label-free OOD checkpoint selection. Given a trained checkpoint, we construct class-conditional mutual k-nearest-neighbour graphs from source embeddings and extract three interpretable signals: a torsion-inspired reduced Laplacian log-determinant for global class-manifold complexity, Ollivier--Ricci curvature for local neighbourhood regularity, and higher-order topological summaries for fragmented connectivity, loops, and global--local inconsistency. Instead of fixing their weights by hand, TopoGeoScore learns a non-negative linear score through a self-supervised objective that enforces invariance under approximately geometry-preserving embedding views and separation from structure-breaking views. The score remains interpretable and uses no target-domain samples or labels. Results across CIFAR-based corruption and distribution-shift benchmarks, ImageNet-C, MNLI→HANS transfer, and OGBN-Arxiv suggest that source representations contain measurable global--local--topological evidence of robustness, supporting practical checkpoint selection before deployment under distribution shift.


1. Project overview

TopoGeoScore studies whether the geometry and topology of learned representations can identify robust neural-network checkpoints without using target-domain data or OOD labels during selection.

The project evolved through three stages:

TorRicc: an initial study of two complementary representation-graph signals:

global spectral complexity, represented by a reduced Laplacian log-determinant or “torsion proxy”;

local regularity, represented by Ollivier–Ricci curvature.

TopoGeoScore: an extension that added persistent and Hodge-theoretic topology, source-conditioned representation views, and non-negative score learning.


The central scientific question is:

Can source-side representation structure predict which checkpoint will generalize best under distribution shift?




