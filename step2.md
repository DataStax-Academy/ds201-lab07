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
 <a href='command:katapod.loadPage?[{"step":"step1"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
  <a href='command:katapod.loadPage?[{"step":"step3"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
<span class="step-count"> Step 2 of 3</span>
</div>

<!-- CONTENT -->

<div class="step-title">Explore nodetool commands</div>


✅ Run *nodetool* with the `help` command and take your time to learn about various available commands:
```
./nodetool help
```

✅ Run *nodetool* with the `describecluster` command to display high-level information about the cluster
```
./nodetool describecluster
```

You should see information about the cluster. 

**Question:** What is the name of the cluster?

<details><summary><b>Answer</b></summary>
<p>
The cluster is called <i>Test Cluster</i>.
</p>
</details>
<br>

**Question:** How many nodes are in the cluster?

<details><summary><b>Answer</b></summary>
<p>
The cluster has 1 node.
</p>
</details>
<br>


✅ Run *nodetool* with the `info` command to display information about this node:
```
./nodetool info
```

**Question:** What is the name of the data center?

<details><summary><b>Answer</b></summary>
<p>
The data center is called <i>datacenter1</i>.
</p>
</details>
<br>

**Question:** Is *gossip* active in this node?

<details><summary><b>Answer</b></summary>
<p>
Yes, <i>gossip</i> is active in this node.
</p>
</details>
<br>

You should see information about the node.

✅ Run *nodetool* with the `help tablestats` command to display help about the `tablestats` command:
```
./nodetool help tablestats
```

✅ Run *nodetool* with the `tablestats killrvideo` command to display statistics on tables in the *killrvideo* namespace
```
./nodetool tablestats killrvideo
```

Answer these questions about the *killrvideo* keyspace:

**Question:** How many SSTables are there?

<details><summary><b>Answer</b></summary>
<p>
There are no SSTables because the data is still in the memtable (and commit log) and has not been flushed to disk.
</p>
</details>
<br>

**Question:** How many cells are in the memtable?

<details><summary><b>Answer</b></summary>
<p>
There are 2 cells in the memtable.
</p>
</details>
<br>

<!-- NAVIGATION -->
<div id="navigation-bottom" class="navigation-bottom">
  <a href='command:katapod.loadPage?[{"step":"step1"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
  <a href='command:katapod.loadPage?[{"step":"step3"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
</div>
