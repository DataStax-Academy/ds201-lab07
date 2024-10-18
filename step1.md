<!-- TOP -->
<div class="top">
  <img class="scenario-academy-logo" src="https://datastax-academy.github.io/katapod-shared-assets/images/ds-academy-2023.svg" />
  <div class="scenario-title-section">
    <span class="scenario-title">Ring</span>
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
<span class="step-count"> Step 1 of 3</span>
</div>

<!-- CONTENT -->

<div class="step-title">Create a <i>keyspace</i>, <i>tables</i>, and load data</div>

In this exercise you will start with a single Cassandra node. When the node is up and running, you will create keyspace and two tables. Next, you will load data into the tables.

Once you have loaded data in the tables you will configure a second node. This node will join the first node to form a cluster. For this second node you will set the `num_tokens` value to `1` and set a value for `initial_token`. 

You will then examine the data and tokens in the cluster.

Use `nodetool` to verify that node1 is running. (You may need to run this command multiple times.)

✅ Verify that Cassandra is running.
```
nodetool status
```

Once Cassandra is up and running, you will recreate the tables from the prvious exercises. 

✅ Run *cqlsh* to connect to the node:
```
/workspace/ds201-lab07/node1/bin/cqlsh
```

✅ Recreate the keyspace and tables you used in the previous:
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

CREATE TABLE videos_by_tag (
  tag text,
  video_id uuid,
  added_date timestamp,
  title text,
  PRIMARY KEY ((tag), added_date, video_id))
  WITH CLUSTERING ORDER BY(added_date DESC, video_id ASC);
```


✅ Load data into the tables:
```
COPY videos(id, added_date, title) 
  FROM '/workspace/ds201-lab07/data-files/videos.csv' 
  WITH HEADER=TRUE;

COPY videos_by_tag(tag, video_id, added_date, title) 
  FROM '/workspace/ds201-lab07/data-files/videos-by-tag.csv' 
  WITH HEADER=TRUE;
```

✅ Examine the data in the *videos* table:
```
SELECT * FROM videos;
```
✅ Examine the data in the *videos_by_tag* table:
```
SELECT * FROM videos_by_tag;
```

✅ Exit *cqlsh*:
```
exit
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
