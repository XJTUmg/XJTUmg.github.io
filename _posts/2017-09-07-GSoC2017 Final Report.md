---
layout: post
title: GSoC2017 Final Report
date: 2017-09-07
tag: pgRouting 
---

I am extremely happy to announce that I have successfully completed my GSoC project!

Time flies, it's my final report for GSoC2017. I learnt a lot from my organization over the last few months. So much fun I've get, I would like to keep contributing to open source world. Great experience indeed.

Most importantly, I would like to thank my mentor **Vicky Vergara** (cvvergara) for the tremendous help she offered me, ever since my first contact with the pgRouting. As a matter of fact, without her ideas and invaluable guidance, completing the project would have been an impossible task.

### Abstract

I implemented 5 functions:

- pgr_connectedComponents - Return the connected components of an undirected graph.
- pgr_strongComponents - Return the strongly connected components of a directed graph.
- pgr_biconnectedComponents - Return the biconnected components of an undirected graph.
- pgr_articulationPoints - Return the articulation points of an undirected graph.
- pgr_bridges - Return the bridges of an undirected graph.


### The state of the project before my GSoC

pgRouting didn't have those functionalities before my GSoC.

### The addition that my project brought to pgRouting

The deliverables are code, full documentation, documentation tests of those five funtions.

### Future directions

- Optimize pgr_bridges. pgr_bridges uses a algorithm with O(E * (V + E)) complexity. Tarjan's algorithm can solve it in O(V + E).
- Create unit tests(pgTAP) for those five funtions.
- Implement incremental connected components (include disjoint-set) for pgRouting by BGL.


### Links to the code and documentation

- **src** files: https://github.com/pgRouting/pgrouting/tree/develop/src/components/src
- **include** files: https://github.com/pgRouting/pgrouting/tree/develop/include/components
- documentation: https://github.com/pgRouting/pgrouting/tree/develop/doc/components
- wiki: https://github.com/pgRouting/pgrouting/wiki/GSoC-2017-Connected-Components

### Slides

https://github.com/pgRouting/pgrouting/wiki/GSoC-2017-Connected-Components#slides

