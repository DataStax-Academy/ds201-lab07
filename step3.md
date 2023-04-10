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
 <a href='command:katapod.loadPage?[{"step":"step2"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
   <a href='command:katapod.loadPage?[{"step":"step4"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
<span class="step-count"> Step 3 of 4</span>
</div>

<!-- CONTENT -->

<div class="step-title">Recreate the tables from the previous exercises</div>

In this step you will recreate the tables from the prvious exercises. This time the data will be distributed across our two-node cluster.

✅ Run *cqlsh* to connect to the cluster:
```
/workspace/ds201-lab06/node1/bin/cqlsh
```
---
**Note:** You could run *cqlsh* from either the `node1` or `node2` directory. You could also specify to which server (by IP) it should connect. Since all Casandra nodes are peers, it doesn't matter where inthe cluster you connect.

---

✅ Recreate the two tables we made in the previous exercises and import their data:
```
CREATE KEYSPACE killrvideo 
WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1 };

USE killrvideo;

CREATE TABLE videos (
  id uuid,
  added_date timestamp,
  title text,
  PRIMARY KEY ((id))
);

COPY videos(id, added_date, title) 
FROM '/workspace/ds201-lab06/data-files/videos.csv' 
WITH HEADER=TRUE;

CREATE TABLE videos_by_tag (
  tag text,
  video_id uuid,
  added_date timestamp,
  title text,
  PRIMARY KEY ((tag), added_date, video_id))
  WITH CLUSTERING ORDER BY(added_date DESC, video_id ASC);

COPY videos_by_tag(tag, video_id, added_date, title) 
FROM '/workspace/ds201-lab06/data-files/videos-by-tag.csv' 
WITH HEADER=TRUE;
```

You should see that the SSTable count is now 1 and the number of Memtable cells is now 0.

✅ Examine the data in the *videos* table:
```
SELECT * FROM videos;
```
✅ Examine the data in the *videos_by_tag* table:
```
SELECT * FROM videos_by_tag;
```
<!-- NAVIGATION -->
<div id="navigation-bottom" class="navigation-bottom">
  <a href='command:katapod.loadPage?[{"step":"step2"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
   <a href='command:katapod.loadPage?[{"step":"step4"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
</div>
