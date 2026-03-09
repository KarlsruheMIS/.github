# KarlsruheMIS -- Maximum Independent Sets at Scale

We develop scalable algorithms for the **Maximum Independent Set (MIS)** and **Maximum Weight Independent Set (MWIS)** problems on large sparse graphs.

---

## The Problem

An **independent set** of a graph is a set of vertices with no two vertices adjacent. The **Maximum Independent Set (MIS)** problem asks for the largest such set; the **Maximum Weight Independent Set (MWIS)** problem generalizes this by assigning weights to vertices and maximizing total weight.

Both problems are NP-hard, and among the hardest in practice -- they do not admit a constant-factor approximation unless P = NP. Large sparse graphs with millions of vertices, as they arise in network analysis, computational biology, and route planning, make exact and near-exact solutions especially challenging.

**Applications** include map labeling, computer vision, combinatorial auctions, coding theory, molecular docking, facility location, and any setting that reduces to finding a maximum conflict-free selection.

---

## Projects

| Repository | Description |
|:-----------|:------------|
| [KaMIS](https://github.com/KarlsruheMIS/KaMIS) | Flagship framework: branch-and-reduce, evolutionary, and local search solvers for MIS and MWIS |
| [LearnAndReduce](https://github.com/KarlsruheMIS/LearnAndReduce) | GNN-guided reduction preprocessing for MWIS |
| [CHILS](https://github.com/KarlsruheMIS/CHILS) | Concurrent local search heuristic for MWIS |
| [DataReductions](https://github.com/KarlsruheMIS/DataReductions) | Reference implementation of data reduction rules for MWIS |
| [HyperMIS](https://github.com/KarlsruheMIS/HyperMIS) | Maximum independent sets on hypergraphs |
| [red2pack](https://github.com/KarlsruheMIS/red2pack) | Scalable solver for the 2-packing set problem |
| [pace-2019](https://github.com/KarlsruheMIS/pace-2019) | Winning solver of the PACE 2019 Challenge (vertex cover track) |

---

## Quick Start

```bash
brew tap KarlsruheMIS/kamis
brew install kamis
```

Or build from source:

```bash
git clone https://github.com/KarlsruheMIS/KaMIS.git
cd KaMIS
git submodule update --init --recursive
./compile_withcmake.sh
# binaries are in deploy/
```

---

## Papers

- S. Lamm, P. Sanders, C. Schulz, D. Strash, R. F. Werneck. **Finding Near-Optimal Independent Sets at Scale.** ALENEX 2016. [(PDF)](https://doi.org/10.1137/1.9781611974317.12)
- D. Hespe, C. Schulz, D. Strash. **Scalable Kernelization for Maximum Independent Sets.** ALENEX 2018. [(PDF)](https://doi.org/10.1137/1.9781611975055.16)
- S. Lamm, C. Schulz, D. Strash, R. Williger, H. Zhang. **Exactly Solving the Maximum Weight Independent Set Problem on Large Real-World Graphs.** ALENEX 2019. [(PDF)](https://doi.org/10.1137/1.9781611975499.11)
- D. Hespe, S. Lamm, C. Schulz, D. Strash. **WeGotYouCovered: The Winning Solver from the PACE 2019 Challenge.** CSC 2020. [(PDF)](https://doi.org/10.1137/1.9781611976229.1)
- S. Lamm, P. Sanders, C. Schulz. **Graph Partitioning for Independent Sets.** SEA 2015. [(PDF)](https://doi.org/10.1007/978-3-319-20086-6_6)

A full list of references is available in the [KaMIS documentation](https://karlsruhemis.github.io).

---

## Contact

**Heidelberg University, Institute of Computer Science**
https://karlsruhemis.github.io
