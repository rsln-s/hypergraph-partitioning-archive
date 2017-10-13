---
title: "Hypergraph Partitioning 101"
date: 2017-09-20T12:25:35-04:00
lastmod: 2017-09-20T12:25:35-04:00
draft: false
description: ""
tags: [hypergraph partitioning archive, benchmark]
author: "Ruslan Shaydulin"

# you can close something for this content if you open it in config.toml.
comment: false
toc: false
# you can define another contentCopyright. e.g. contentCopyright: "This is an another copyright."
contentCopyright: false
reward: false
mathjax: true
---

# Hypergraph partitioning archive 

Welcome to the Hypergraph partitioning archive.  The goal of this archive is to provide a benchmark for comparing the quality of hypergraph partitioning algorithms. This archive includes partitioning results by some of the most popular hypergraph partitioning packages. The researchers are welcome to submit their own partitionings to this archive.

## Problem definition

Let \\(H=(V,E)\\) be a hypergraph with a set of vertices \\(V\\) and the set of hypergredges \\(E\\). The goal of *k-way* hypergraph partitioning is to assign elements of \\(V\\) to mutually disjoint partitionings \\(P\_1, \ldots , P\_k\\) such that the partitionings are of mostly equal size and a metric on the cut is minimized. Here cut is a set of edges that span more than one partition: \\(E\_{cut}\subset E\\) such that for \\(e\in E\\) holds \\(e\in E\_{cut}\\) if and only if \\(\exists i, j\in \mathbb{N}: e\cap V_i \neq \emptyset, e\cap V_j\neq\emptyset\\) such that \\(i\neq j\\).

The constraint that partitionings should be of about the same size is called *imbalance constraint*. In this benchmark it is defined as follows: 

\\[ imbal=\dfrac{\sum\_{v\in V\_{max}}w(v)}{\frac{1}{k}\sum\_{v\in V}w(v)}\text{, where } V\_{max}: \sum\_{v\in V\_{max}}w(v) = \max\_i(\sum\_{v\in V\_{i}}w(v)) \\]

Cut metric used by this benchmark is the number of cut hyperedges (i.e. \\(|E\_{cut}|\\)) and all vertices and hyperedges have unit weight. However, in general hypergraph partitioning problem allows many cut metrics, as well as weighted vertices and hyperedges.

A quick introduction into the hypergraph partitioning problem can be found [here](http://blog.shaydul.in/post/hypergraph-partitioning-101/).

## How to submit your algorithm

In order to have you algorithm included in this benchmark, you'll have to download the hypergraphs from [here](https://clemson.box.com/s/r26tz74u6dlq87z9ukll80o66ur7lsje), compute you partitioning and submit it in the following format.

File with partitioning should be named `[graph name].[number of parts].[imbalance factor]`, where imbalance factor is an integer (number of percents). For example, file `lp_ken_07.2.10` should contain partitioning of the hypergraph lp\_ken\_07 into two parts with 10% imbalance factor.

Each line of file contains two integers: number of the vertex and number of the partition to which the vertex is assigned. For example, line `10 2` would indicate that the vertex 10 is assigned to the partition 2. Vertices and partitionings should be numbered from one (and not from zero).

The files should be sent to [rshaydu@g.clemson.edu](mailto:rshaydu@g.clemson.edu). 

## Results

Full table with the results is available [here]({{< ref "misc/hypergraph_partitioning_results_table.md" >}}) and [in csv](http://shaydul.in/misc/algebraic_distance_on_hypergraphs_results.csv).
