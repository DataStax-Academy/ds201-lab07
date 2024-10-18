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
 <a href='command:katapod.loadPage?[{"step":"step1"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
  <a href='command:katapod.loadPage?[{"step":"step3"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
<span class="step-count"> Step 2 of 4</span>
</div>

<!-- CONTENT -->

<div class="step-title">Configure and start a node to join the cluster</div>

In this step you will configure a new node to join the cluster. The new node will not use *vnodes*. Disable *vnodes* by setting `num_tokens` to `1` and defining an `initial_token` in `cassandra.yaml1

✅ Open `/workspace/ds201-lab07/node2/conf/cassandra.yaml` in a *nano* or the text editor of your choice.
```
nano /workspace/ds201-lab07/node2/conf/cassandra.yaml
```

In the file find:

`num_tokens`

Set the value to `1` so the new does not use *vnodes*.

In the same file find:

`# initial_token:`

Un-comment and change `initial_token` value setting it to `-9223372036854775808`. Since node1 has 16 *vnodes* and node2 has 1 node,  This will allow *node2* to manage half of the token range – all of the positive tokens and one negative token of `-9223372036854775808`

The new entry should look like:

`initial_token: -9223372036854775808`

Save and exit the editor.

✅ Start the new node:
```
/workspace/ds201-lab07/node2/bin/cassandra
```

Use `nodetool` to verify that both nodes are running. You may need to run this command multiple times.

✅ Verify that the clustered servers are running.
```
/workspace/ds201-lab07/node1/bin/nodetool status
```

* Both nodes should be *Up* and *Normal*.
* The node listening at `127.0.0.1` should have 16 tokens
* The node listening at `127.0.0.2` should have 1 token* 

<img src="https://katapod-file-store.s3.us-west-1.amazonaws.com/ds201/lab07-image01.png" />

<!-- NAVIGATION -->
<div id="navigation-bottom" class="navigation-bottom">
  <a href='command:katapod.loadPage?[{"step":"step1"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
  <a href='command:katapod.loadPage?[{"step":"step3"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
</div>
