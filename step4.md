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
The <i>video_id</i> column is the primary key.
</p>
</details>
<br>



✅ Exit from *cqlsh*:
```
exit
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
</div>
