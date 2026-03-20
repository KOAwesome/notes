Structured Streaming supports three output modes:

Append: Writes only new rows since the last trigger.

Update: Writes only updated rows.

Complete: Writes the entire result table after every trigger execution.

For aggregations like groupBy().count(), only complete mode outputs the entire table each time.

Spark supports multiple broadcast joins in a single query plan, as long as each broadcasted DataFrame is small enough to fit under the configured threshold.

Watermarking in Structured Streaming defines how late a record can arrive based on event time before Spark discards it.

Behavior:

.withWatermark('event_time', '10 minutes')

This means Spark will keep state for 10 minutes beyond the maximum event time seen so far.

Any data arriving later than 10 minutes after the current watermark is ignored --- it will not be included in the aggregation or output.