---
layout: post
title: Field datatypes
category: Elasticsearch
tags:
- elasticsearch
---
## 1. Core datatypes
- string : text, keyword
- Numeric : long, integer, short, byte, double, float, half_float, scaled_float
- Date : date
- Date nanoseconds : date_nanos
- Boolean : boolean
- Binary :binary
- Range : integer_range, float_range, long_range, double_range, date_range, ip_range

## 2. Complex datatypes
- Object : object for single JSON objects
- Nested : nested for arrays of JSON objects

## 3. Geo datatypes
- Geo-point : geo_point for lat/lon points
- Geo-shape : geo_shape for complex shapes like polygons

## 4. Specialised datatypes
- IP : ip for IPv4 and IPv6 addresses
- Completion datatype : completion to provide auto-complete suggestions
- Token count : token_count to count the number of tokens in a string
- mapper-murmur3 : murmur3 to compute hashes of values at index-time and store them in the index
- mapper-annotated-text : annotated-text to index text containing special markup (typically used for identifying named entities)
- Percolator : Accepts queries from the query-dsl
- Join : Defines parent/child relation for documents within the same index
- Rank feature : Record numeric feature to boost hits at query time.
- Rank features : Record numeric features to boost hits at query time.
- Dense vector : Record dense vectors of float values.
- Sparse vector : Record sparse vectors of float values.
- Search-as-you-type : A text-like field optimized for queries to implement as-you-type completion
- Alias : Defines an alias to an existing field.
- Flattened : Allows an entire JSON object to be indexed as a single field.
- Shape : shape for arbitrary cartesian geometries.
- Histogram : histogram for pre-aggregated numerical values for percentiles aggregations.
- Constant keyword : Specialization of keyword for the case when all documents have the same value.

## Reference
- https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping-types.html#_complex_datatypes