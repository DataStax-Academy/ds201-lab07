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
<span class="step-count"> Step 1 of 4</span>
</div>

<!-- CONTENT -->

<div class="step-title">Edit <i>cassandra.yaml</i> and set the token range</div>

In this exercise there is a two-node Cassandra cluster. The root directories for the nodes are: `./node1` and `./node2`. You are going to edit the configuration file (`cassandra.yaml`) for *node2*. You are going to assign an `initial_token` value of `-9223372036854775808`


✅ Open `/workspace/ds201-lab07/node2/conf/cassandra.yaml` in a *nano* or the text editor of your choice.
```
nano /workspace/ds201-lab07/node2/conf/cassandra.yaml
```

In the file find:

`# initial_token:`

Un-comment and change `initial_token` value setting it to `-9223372036854775808`. This will allow *node2* to manage half of the token range – all of the positive tokens and one negative token of `-9223372036854775808`

The new entry should look like:

`initial_token: -9223372036854775808`

Save and exit the editor.

<!-- NAVIGATION -->
<div id="navigation-bottom" class="navigation-bottom">
 <a href='command:katapod.loadPage?[{"step":"intro"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
   <a href='command:katapod.loadPage?[{"step":"step2"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
</div>
