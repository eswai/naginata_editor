<script>
  export let press = false;
  export let legend = [""];
  export let size = "key1u";

  $: css = press ? "keyon" : "keyoff"
</script>

<div class="{size} {css}">
  {#each legend as a}
  <div>{a}</div>
  {/each}
</div>

<style>

  .key1u {
    /* float: left; */
    margin: 2px;
    height:40px;
    width:40px;
    background-color:#ffffff;
    border:1px solid #bebebe;
    border-radius:4px;
    display: grid;
    grid-template-rows: 18px 18px;
    grid-template-columns: 20px 20px;
    font-size: 14px;
    /* align-items: baseline; */
  }

  .key4u {
    float: left;
    margin: 2px;
    height:40px;
    width:178px;
    background-color:#ffffff;
    border:1px solid #bebebe;
    border-radius:4px;
    display: grid;
    grid-template-rows: 18px 18px;
    grid-template-columns: 170px;
    font-size: 14px;
  }
  
  .keyon {
    background-color:#caffbd;
  }

  .keyoff {
    background-color:#ffffff;
  }

</style>