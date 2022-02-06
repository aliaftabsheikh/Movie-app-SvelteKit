<script>
    let count = 0;

    function incrementBtn (){
        count +=1
    }
</script>

<h1>Number : {count}</h1>
<button class="btn" on:click={incrementBtn}>Increment</button>
<!-- <p>Visit <a href="/about">kit.svelte.dev</a> to read the documentation</p> -->

<style>
  h1{
      font-size: 70px;
  }
</style>