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
<span class="step-count"> Step 3 of 3</span>
</div>

<!-- CONTENT -->

<div class="step-title">Flush the memtable</div>

The *videos_by_tag* table has 5 rows. For now, the data is stored in the *memtable* until the data is flushed to disk.

✅ Run *nodetool* with the `flush` command to write the memtable(s) to disk:
```
./nodetool flush
```

✅ Run *nodetool* with the `tablestats killrvideo` command again:
```
./nodetool tablestats killrvideo
```

You should see that the SSTable count is now 1 and the number of Memtable cells is now 0.

✅ Explore some other commonly used *nodetool* commands:
```
./nodetool help tpstats
```
```
./nodetool tpstats
```
```
./nodetool help netstate
```
```
./nodetool netstats
```
```
./nodetool help repair
```

<!-- NAVIGATION -->
<div id="navigation-bottom" class="navigation-bottom">
  <a href='command:katapod.loadPage?[{"step":"step2"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
</div>
