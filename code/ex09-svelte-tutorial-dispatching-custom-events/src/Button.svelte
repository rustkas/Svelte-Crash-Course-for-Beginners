<script>
  export  let btnText = "Component Button";

  
</script>

<button on:click>{btnText}</button>

<div class="card" on:click|self>
  <!-- <span>Click to log</span> -->
  <button on:click|once>{btnText}</button>
</div>


<style>
  button {
    background-color: #667EEA;
    border-color: #4C51BF;
    border-width: 1px;
    border-style: solid;
    color: #FFF;
  }
  .card{
    padding: 12px;
    border-color: gray;
    border-width: 2px;
    border-style: solid;
    margin-bottom: 8px;
  }
</style>