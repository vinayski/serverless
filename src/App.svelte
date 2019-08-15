<script>
  import { onMount } from "svelte";
  export let date;
  export let datep;

  onMount(async () => {
    const res = await fetch("/api/date");
    const resp = await fetch("/api/datep");
    const newDate = await res.text();
    const newDatep = await resp.text();
    date = newDate;
    datep = newDatep;
  });
</script>

<main>
  <h1>Svelte + Node.js + Python API</h1>
  <p>
    <a
      href="https://github.com/vinayski/svelte-functions"
      target="_blank"
      rel="noreferrer noopener">
      This project
    </a>
    is contains a serverless
    <a href="https://nodejs.org/en/">Node.js</a>
    function. See
    <a href="/api/date">
      <code>api/date</code>
      for the Date API with Node.js
    </a> 
    <a href="/api/datep">
      <code>api/datep</code>
      & with Python
    </a>.
  </p>
  <br />
  <h2>The date according to Node.js is:</h2>
  <p>{date ? date : 'Loading date...'}</p>
  <h2>The date from python api is:</h2>
  <p>{datep ? datep : 'Loading date...'}</p>  
</main>
