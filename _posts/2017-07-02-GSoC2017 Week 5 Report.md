---
layout: post
title: GSoC2017 Week 5 Report 
date: 2017-07-02
tag: pgRouting 
---

The summer vacation began! I have much more time for GSoC.  
However I have to prepare for the upcoming 9 algorithm courses, the difference is that I am the teacher. :)

### Why did you extend Pgr_base_graph?

Suppose you have an undirected graph and there is an edge (st - ed, cost > 0 & reverse_cost > 0) in the graph.  
```Pgr_base_graph``` will add two edges to ```graph``` because of the following code ([Here](https://github.com/XJTUmg/pgrouting/blob/gsoc-component/include/cpp_common/pgr_base_graph.hpp#L814) is the member function in ```Pgr_base_graph```)  

{% highlight C++ %}

    if (edge.cost >= 0) {
        boost::tie(e, inserted) =
            boost::add_edge(vm_s, vm_t, graph);
        graph[e].cost = edge.cost;
        graph[e].id = edge.id;
    }

    if (edge.reverse_cost >= 0) {
        boost::tie(e, inserted) =
            boost::add_edge(vm_t, vm_s, graph);

        graph[e].cost = edge.reverse_cost;
        graph[e].id = edge.id;
    }

{% endhighlight %}

This characteristic leads to duplicates in the results table of ```pgr_biconnectedComponents```.  
Normally, users don't like duplicates. So I extended ```Pgr_base_graph``` to fix the duplicates.

### How did you do that?

I "overwrote" the following 4 functions.  

{% highlight C++ %}

 public:
     explicit Pgr_componentsGraph< G, T_V, T_E >(graphType gtype)
         : Pgr_base_graph< G, T_V, T_E >(gtype) {
         }

     template < typename T >
         void insert_edges(const T *edges, int64_t count) {
         }

     template <typename T >
         void insert_edges(const std::vector < T > &edges) {
         }

 private:
    template < typename T >
    void
    graph_add_edge(const T &edge) {
    }

{% endhighlight %}

[See Details](https://github.com/XJTUmg/pgrouting/blob/gsoc-component/include/components/pgr_componentsGraph.hpp).

### What did you get done this week?

- Extended Pgr_base_graph to fix duplicates.
- Wrote family page of components algorithms.
- Wrote documentation of my three functions.

Details can be found in [here](https://github.com/pgRouting/pgrouting/wiki/GSoC-2017-Connected-Components#week-5).  
Set of pull requests can be found in [here](https://github.com/pgRouting/pgrouting/pulls?q=is%3Apr+author%3AXJTUmg+is%3Aclosed).

### What do you plan on doing next week?

- Improve documentation of components algorithms.
- Lint the code of components algorithms.
- Create pgTAP unit tests for my functions.

### Are you blocked on anything?

No, at the moment I’m not blocked.  

The wiki page can be found in [here](https://github.com/pgRouting/pgrouting/wiki/GSoC-2017-Connected-Components).  
The repository can be found in [here](https://github.com/pgRouting/pgrouting/tree/gsoc-component).
