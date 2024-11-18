**Different options to model changing data**  

- Latest Snapshot
Store the latest value, don't store history. This will make the downstream pipelines non-idempotent

- Daily/ Monthly/ Yearly snapshot
Instead of latest snapshot, use periodic snapshots of data. This stores history (but not all changes) depending on the level of the snapshotting

- SCD (type 2)
Keep every change with eff_from and eff_to date (and optionally a Is_Active flag for the latest record). Downstream pipelines can be idempotent when they use these dimensions

- SCD Type 3
You only store only Original and latest. Benefits is you only have 1 row so your table size is manageable. But you lose the history between original and latest. This will make the downstream pipelines non-idempotent  
