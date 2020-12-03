# Enumeration: SearchConsistency

## Enumeration members

###  GLOBAL

• **GLOBAL**:

Operations performed by any client of the Couchbase Server up to the
  time of the queries dispatch will be reflected in any index results.
  This is the slowest of all consistency levels as it requires that the
  server synchronize its indexes to the current key-value state prior to
  execution of the query.

___

###  LOCAL

• **LOCAL**:

Operations performed by this ottoman instance will be reflected
  in queries performed by this particular ottoman instance.  This
  type of consistency will be slower than no consistency, but faster
  than GLOBAL as the index state is tracked internally rather than
  requested from the server.

___

###  NONE

• **NONE**:

No degree consistency required