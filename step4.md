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
<span class="step-count"> Step 4 of 4</span>
</div>

<!-- CONTENT -->

<div class="step-title">Examine partitioning and datadistribution in the cluster</div>

You should still be in *cqlsh*, if not start it again and connect to the cluster.

✅ Execute the following query to retrieve the tag partition key value for each row from the videos_by_tag table, along with its corresponding token:
```
SELECT tag, token(tag), title FROM videos_by_tag;
```
**Question:** How many unique tokens are in the table?

<details><summary><b>Answer</b></summary>
<p>
There are two unique tokens, one for each unique partition key.
</p>
</details>
<br>

✅ Exit from *cqlsh*:
```
exit
```

✅  Run the following command to refresh your memory as to which nodes own which token ranges.
```
/workspace/ds201-lab07/node1/bin/nodetool ring
```
✅  Execute the following commands to map the specific tags (`datastax` and `cassandra`) to endpoints/nodes.

---
**Note:** Note that we must also supply the keyspace and table name we are interested in since we set replication on a per-keyspace basis. There is more on replication to come later in this course.

---


```
/workspace/ds201-lab07/node1/bin/nodetool getendpoints killrvideo videos_by_tag 'datastax'

/workspace/ds201-lab07/node1/bin/nodetool getendpoints killrvideo videos_by_tag 'cassandra'
```

✅  Run `nodetool status` again to see the token range ownership percentages.
```
/workspace/ds201-lab07/node1/bin/nodetool status
```

**Question:** What do the *Owns* values mean?

<details><summary><b>Answer</b></summary>
<p>
The <i>Owns</i> fields are the percentage of tokens owned by each node in the cluster. The tokens may not be evenly distributed because there are such a small number. The *videos* table as 5 unique tokens and the *videos_by_tag* table has 2.
</p>
</details>
<br>

<!-- NAVIGATION -->
<div id="navigation-bottom" class="navigation-bottom">
  <a href='command:katapod.loadPage?[{"step":"step2"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
</div>
