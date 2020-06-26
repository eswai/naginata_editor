<script>
  export let press = false;
  export let legend = [""];
  export let size = "key1u";

  $: css = press ? "keyon" : "keyoff"
</script>

<div class="{size} {css}">
  {legend[0]}
</div>

<style>

  .key1u {
    float: left;
    margin: 2px;
    height:40px;
    width:40px;
    background-color:#ffffff;
    border:1px solid #bebebe;
    border-radius:4px;
  }

  .key4u {
    float: left;
    margin: 2px;
    height:40px;
    width:178px;
    background-color:#ffffff;
    border:1px solid #bebebe;
    border-radius:4px;
  }
  
  .keyon {
    background-color:#caffbd;
  }

  .keyoff {
    background-color:#ffffff;
  }

</style>