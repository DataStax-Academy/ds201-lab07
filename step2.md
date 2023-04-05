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
<span class="step-count"> Step 2 of 4</span>
</div>

<!-- CONTENT -->

<div class="step-title">Start the nodes in the cluster</div>


✅ Start *node1*
```
/workspace/ds201-lab06/node1/bin/cassandra
```
---
**Note:** You may see a `java.net.ConnectionError`, this is because this server is looking for a seed node but it is the first node in the cluster so there are none available. This is expected behavior.

---


Use `nodetool` to verify that node1 is running. (You may need to run this command multiple times.)

✅ Verify that Cassandra is running.
```
/workspace/ds201-lab06/node1/bin/nodetool status
```

✅ Once the first node is running, start the second node:
```
/workspace/ds201-lab06/node2/bin/cassandra
```

Use `nodetool` to verify that both nodes are  running. (You may need to run this command multiple times.)

✅ Verify that Cassandra is running.
```
/workspace/ds201-lab06/node1/bin/nodetool status
```

* Both nodes should be *Up* and *Normal*.
* The *Owns* shows 100% for both nodes because no (non-system) keyspaces have been created yet.



<img src="https://katapod-file-store.s3.us-west-1.amazonaws.com/ds201/lab06-image01.png" />

<!-- NAVIGATION -->
<div id="navigation-bottom" class="navigation-bottom">
  <a href='command:katapod.loadPage?[{"step":"step1"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
  <a href='command:katapod.loadPage?[{"step":"step3"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
</div>
