<!-- TOP -->
<div class="top">
  <img class="scenario-academy-logo" src="https://datastax-academy.github.io/katapod-shared-assets/images/ds-academy-2023.svg" />
  <div class="scenario-title-section">
    <span class="scenario-title">Node</span>
    <span class="scenario-subtitle">ℹ️ For technical support, please contact us via <a href="mailto:academy@datastax.com">email</a>.</span>
  </div>
</div>

<!-- CONTENT -->
<main>
  <br/>
  <div class="container px-4 py-2">
    <div class="row g-4 py-2 row-cols-1 row-cols-lg-1">
      <div class="feature col div-choice">
        <div class="scenario-description">Node</div>
          <ul>
            <li><span class="scenario-description-attribute">Difficulty</span>: Beginner</li>
            <li><span class="scenario-description-attribute">Time</span>: 10 minutes</li>
          </ul>
          <div class="scenario-objectives">In this hands-on lab, you will:</div>
            <ul>
              <li><span class="scenario-objective">Start a two-node Cassandra cluster</span></li>
              <li><span class="scenario-objective">Determine the token range ownership for nodes</span></li>
              <li><span class="scenario-objective">Find the corresponding node where partitions are stored</span></li>
            </ul>
          </div>
          <p>
            One of the keys to Cassandra’s performance is the use of a ring that keeps track of tokens. This token ring allows Cassandra to know exactly which nodes contain which partitions. The ring also helps to avoid single points of failure.
          </p>   
          <a href='command:katapod.loadPage?[{"step":"step1"}]' class="btn btn-primary btn-cassandra">
            Start the lab
          </a>
         </div>
      </div>
    </div>
  </div>
</main>