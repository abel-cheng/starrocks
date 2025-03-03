# HLL_UNION_AGG

## Description

HLL is an engineering implementation based on the HyperLogLog algorithm, which is used to save the intermediate results of HyperLogGog calculation process.

It can only be used as the value column of a table and reduce the amount of data through aggregation to achieve the purpose of speeding up the query.

An estimated result with an error of about 1% based on HLL. The HLL column is generated by other columns or based on data loaded into the table.

During loading, the [hll_hash](../aggregate-functions/hll_hash.md) function is used to specify which column is used to generate the HLL column. It is often used to replace Count Distinct, and to calculate UVs quickly in business by combining rollup.

## Syntax

```Haskell
HLL_UNION_AGG(hll)
```

## Examples

```plain text
MySQL > select HLL_UNION_AGG(uv_set) from test_uv;
+-------------------------+
| HLL_UNION_AGG(`uv_set`) |
+-------------------------+
| 17721                   |
+-------------------------+
```

## keyword

HLL_UNION_AGG,HLL,UNION,AGG
