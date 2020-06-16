<script>

  export let highlight = [];

  let keys = {
    "q": {"legend": "Q", "css": "keyoff"},
    "w": {"legend": "W", "css": "keyoff"},
    "e": {"legend": "E", "css": "keyoff"},
    "r": {"legend": "R", "css": "keyoff"},
    "t": {"legend": "T", "css": "keyoff"},
    "y": {"legend": "Y", "css": "keyoff"},
    "u": {"legend": "U", "css": "keyoff"},
    "i": {"legend": "I", "css": "keyoff"},
    "o": {"legend": "O", "css": "keyoff"},
    "p": {"legend": "P", "css": "keyoff"},
    "a": {"legend": "A", "css": "keyoff"},
    "s": {"legend": "S", "css": "keyoff"},
    "d": {"legend": "D", "css": "keyoff"},
    "f": {"legend": "F", "css": "keyoff"},
    "g": {"legend": "G", "css": "keyoff"},
    "h": {"legend": "H", "css": "keyoff"},
    "j": {"legend": "J", "css": "keyoff"},
    "k": {"legend": "K", "css": "keyoff"},
    "l": {"legend": "L", "css": "keyoff"},
    ";": {"legend": ";", "css": "keyoff"},
    "z": {"legend": "Z", "css": "keyoff"},
    "x": {"legend": "X", "css": "keyoff"},
    "c": {"legend": "C", "css": "keyoff"},
    "v": {"legend": "V", "css": "keyoff"},
    "b": {"legend": "B", "css": "keyoff"},
    "m": {"legend": "M", "css": "keyoff"},
    "n": {"legend": "N", "css": "keyoff"},
    ",": {"legend": ",", "css": "keyoff"},
    ".": {"legend": ".", "css": "keyoff"},
    "/": {"legend": "/", "css": "keyoff"},
    "shift": {"legend": "Shift", "css": "keyoff"},
    "-": {"legend": "-", "css": "keyoff"},
  };

  $: update(highlight);

  function update(hl) {
    console.log(hl);
    for (let ki in keys) {
      console.log([ki, hl]);
      if (hl.includes(ki)) {
        keys[ki].css = "keyon";
      } else {
        keys[ki].css = "keyoff";
      }
    }
  }

</script>

<style>

  .keyboard {
    margin: auto;
    text-align: center;
  }

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

  .row {
    display: flex;
  }

</style>


<div class="keyboard">
  <div class="row">
    <div class="key1u {keys["q"].css}">{keys["q"].legend}</div>
    <div class="key1u {keys["w"].css}">{keys["w"].legend}</div>
    <div class="key1u {keys["e"].css}">{keys["e"].legend}</div>
    <div class="key1u {keys["r"].css}">{keys["r"].legend}</div>
    <div class="key1u {keys["t"].css}">{keys["t"].legend}</div>
    <div class="key1u {keys["y"].css}">{keys["y"].legend}</div>
    <div class="key1u {keys["u"].css}">{keys["u"].legend}</div>
    <div class="key1u {keys["i"].css}">{keys["i"].legend}</div>
    <div class="key1u {keys["o"].css}">{keys["o"].legend}</div>
    <div class="key1u {keys["p"].css}">{keys["p"].legend}</div>
  </div >

  <div class="row">
    <div class="key1u {keys["a"].css}">{keys["a"].legend}</div>
    <div class="key1u {keys["s"].css}">{keys["s"].legend}</div>
    <div class="key1u {keys["d"].css}">{keys["d"].legend}</div>
    <div class="key1u {keys["f"].css}">{keys["f"].legend}</div>
    <div class="key1u {keys["g"].css}">{keys["g"].legend}</div>
    <div class="key1u {keys["h"].css}">{keys["h"].legend}</div>
    <div class="key1u {keys["j"].css}">{keys["j"].legend}</div>
    <div class="key1u {keys["k"].css}">{keys["k"].legend}</div>
    <div class="key1u {keys["l"].css}">{keys["l"].legend}</div>
    <div class="key1u {keys[";"].css}">{keys[";"].legend}</div>
  </div >

  <div class="row">
    <div class="key1u {keys["z"].css}">{keys["z"].legend}</div>
    <div class="key1u {keys["x"].css}">{keys["x"].legend}</div>
    <div class="key1u {keys["c"].css}">{keys["c"].legend}</div>
    <div class="key1u {keys["v"].css}">{keys["v"].legend}</div>
    <div class="key1u {keys["b"].css}">{keys["b"].legend}</div>
    <div class="key1u {keys["n"].css}">{keys["n"].legend}</div>
    <div class="key1u {keys["m"].css}">{keys["m"].legend}</div>
    <div class="key1u {keys[","].css}">{keys[","].legend}</div>
    <div class="key1u {keys["."].css}">{keys["."].legend}</div>
    <div class="key1u {keys["/"].css}">{keys["/"].legend}</div>
  </div >

  <div class="row">
    <div class="key1u"></div>
    <div class="key1u"></div>
    <div class="key1u"></div>
    <div class="key4u {keys["shift"].css}">{keys["shift"].legend}</div>
    <div class="key1u"></div>
    <div class="key1u"></div>
    <div class="key1u"></div>
  </div>
</div>

