<!-- TOP -->
<div class="top">
  <img class="scenario-academy-logo" src="https://datastax-academy.github.io/katapod-shared-assets/images/ds-academy-2023.svg" />
  <div class="scenario-title-section">
    <span class="scenario-title">Node</span>
    <span class="scenario-subtitle">ℹ️ For technical support, please contact us via <a href="mailto:academy@datastax.com">email</a>.</span>
  </div>
</div>

<!-- NAVIGATION -->
<div id="navigation-top" class="navigation-top">
 <a href='command:katapod.loadPage?[{"step":"intro"}]'
   class="btn btn-dark navigation-top-left">⬅️ Back
 </a>
   <a href='command:katapod.loadPage?[{"step":"step2"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
<span class="step-count"> Step 1 of 1</span>
</div>

<!-- CONTENT -->

<div class="step-title">Create the <i>videos_by_tag</i> table</div>

Use *nodetool* to verify that Cassandra is running. (You may need to run this command multiple times.)

✅ Verify that Cassandra is running.
```
cd apache-cassandra-4.1.0/bin
./nodetool status
```
✅ Start `cqlsh`:
```
./cqlsh
```

✅ Create a keyspace called *killrvideo*. Use `SimpleStrategy` for the replication class with a replication factor of one.
```
CREATE KEYSPACE killrvideo
WITH replication = {
  'class':'SimpleStrategy', 
  'replication_factor': 1
};
```

✅ *Use* the keyspace:
```
use killrvideo;
```

✅ Create the `videos_by_tag` table: 
```
CREATE TABLE videos_by_tag (
  tag TEXT,
  video_id TIMEUUID,
  added_date TIMESTAMP,
  title TEXT,
  PRIMARY KEY ((tag), video_id)
);

✅ Use the COPY command to import the `videos-by-tag.csv` data into your new table:
```
COPY videos_by_tag (tag, video_id, added_date, title)
FROM '/workspace/ds201-lab06/data-files/videos-by-tag.csv'
WITH HEADER = TRUE;
```

✅ Retrieve all rows from table *videos_by_tag* and verify that you get 5 rows as expected.
```
SELECT * FROM videos_by_tag;
```

<!-- NAVIGATION -->
<div id="navigation-bottom" class="navigation-bottom">
 <a href='command:katapod.loadPage?[{"step":"intro"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
   <a href='command:katapod.loadPage?[{"step":"step2"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
</div>
