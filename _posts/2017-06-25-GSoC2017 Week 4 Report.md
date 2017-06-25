---
layout: post
title: GSoC2017 Week 4 Report 
date: 2017-06-25
tag: pgRouting 
---

All final exams of this semester are done! :)  

### Fixed AppVoyer

I changed
{% highlight C++ %}
boost::strong_components(graph.graph, &components[0]);
{% endhighlight %}
to
{% highlight C++ %}
boost::strong_components(graph.graph,
        boost::make_iterator_property_map(components.begin(), get(boost::vertex_index, graph.graph)));
{% endhighlight %}

### About Sorting

- ```std::sort``` and ```std::stable_sort``` are useful
- A lambda expression is better than a comparison function
- A complicated lambda is not clear. Sometimes you can avoid this situation by using both of ```std::sort``` and ```std::stable_sort```  

Finally, I changed
{% highlight C++ %}
template < class G >
bool
Pgr_components< G >::sort_cmp(
        const pgr_componentV_t &a,
        const pgr_componentV_t &b) {
    if (a.component == b.component)
        return a.node < b.node;
    return a.component < b.component;
}

std::sort(results.begin(), results.end(), sort_cmp);
{% endhighlight %}
to
{% highlight C++ %}
std::sort(results.begin(), results.end(),
        [](const pgr_componentV_t &left, const pgr_componentV_t &right) {
        return left.node < right.node; });
std::sort(results.begin(), results.end(),
        [](const pgr_componentV_t &left, const pgr_componentV_t &right) {
        return left.component < right.component; });
{% endhighlight %}
By the way, I changed ```pgr_componentV_t``` to ```pgr_components_rt``` after the discussion with Vicky.

### What did you get done this week?

- Improved the code of ```pgr_connectedComponentsV``` & ```pgr_strongComponentsV```.
- Implemented ```pgr_biconnectedComponents```.
Details can be found in [here](https://github.com/pgRouting/pgrouting/wiki/GSoC-2017-Connected-Components#week-4).  
Set of pull requests can be found in [here](https://github.com/pgRouting/pgrouting/pulls?q=is%3Apr+author%3AXJTUmg+is%3Aclosed).

### What do you plan on doing next week?
- Plan to extend ```pgr_base_graph``` for my implementations because results table of ```pgr_biconnectedComponents``` has many duplicates.
- Start to implement the edge version of those functions.

### Are you blocked on anything?
No, at the moment I’m not blocked.  

The wiki page can be found in [here](https://github.com/pgRouting/pgrouting/wiki/GSoC-2017-Connected-Components).  
The repository can be found in [here](https://github.com/pgRouting/pgrouting/tree/gsoc-component).
