<script>
  import Key from './Key.svelte';
  export let highlight = [];

  let keys = {
    "q": {"legend": ["Q"], "press": false},
    "w": {"legend": ["W"], "press": false},
    "e": {"legend": ["E"], "press": false},
    "r": {"legend": ["R"], "press": false},
    "t": {"legend": ["T"], "press": false},
    "y": {"legend": ["Y"], "press": false},
    "u": {"legend": ["U"], "press": false},
    "i": {"legend": ["I"], "press": false},
    "o": {"legend": ["O"], "press": false},
    "p": {"legend": ["P"], "press": false},
    "a": {"legend": ["A"], "press": false},
    "s": {"legend": ["S"], "press": false},
    "d": {"legend": ["D"], "press": false},
    "f": {"legend": ["F"], "press": false},
    "g": {"legend": ["G"], "press": false},
    "h": {"legend": ["H"], "press": false},
    "j": {"legend": ["J"], "press": false},
    "k": {"legend": ["K"], "press": false},
    "l": {"legend": ["L"], "press": false},
    ";": {"legend": [";"], "press": false},
    "z": {"legend": ["Z"], "press": false},
    "x": {"legend": ["X"], "press": false},
    "c": {"legend": ["C"], "press": false},
    "v": {"legend": ["V"], "press": false},
    "b": {"legend": ["B"], "press": false},
    "m": {"legend": ["M"], "press": false},
    "n": {"legend": ["N"], "press": false},
    ",": {"legend": [","], "press": false},
    ".": {"legend": ["."], "press": false},
    "/": {"legend": ["/"], "press": false},
    "[s]": {"legend": ["Shift"], "press": false},
    "-": {"legend": ["-"], "press": false},
  };

  $: update(highlight);

  function update(hl) {
    // console.log(hl);
    for (let ki in keys) {
      // console.log([ki, hl]);
      if (hl.includes(ki)) {
        keys[ki].press = true;
      } else {
        keys[ki].press = false;
      }
    }
  }

</script>

<style>

  .keyboard {
    margin: auto;
    text-align: center;
  }

  .row {
    display: flex;
  }

</style>


<div class="keyboard">
  <div class="row">
    <Key press={keys["q"].press} legend={keys["q"].legend} />
    <Key press={keys["w"].press} legend={keys["w"].legend} />
    <Key press={keys["e"].press} legend={keys["e"].legend} />
    <Key press={keys["r"].press} legend={keys["r"].legend} />
    <Key press={keys["t"].press} legend={keys["t"].legend} />
    <Key press={keys["y"].press} legend={keys["y"].legend} />
    <Key press={keys["u"].press} legend={keys["u"].legend} />
    <Key press={keys["i"].press} legend={keys["i"].legend} />
    <Key press={keys["o"].press} legend={keys["o"].legend} />
    <Key press={keys["p"].press} legend={keys["p"].legend} />
  </div >

  <div class="row">
    <Key press={keys["a"].press} legend={keys["a"].legend} />
    <Key press={keys["s"].press} legend={keys["s"].legend} />
    <Key press={keys["d"].press} legend={keys["d"].legend} />
    <Key press={keys["f"].press} legend={keys["f"].legend} />
    <Key press={keys["g"].press} legend={keys["g"].legend} />
    <Key press={keys["h"].press} legend={keys["h"].legend} />
    <Key press={keys["j"].press} legend={keys["j"].legend} />
    <Key press={keys["k"].press} legend={keys["k"].legend} />
    <Key press={keys["l"].press} legend={keys["l"].legend} />
    <Key press={keys[";"].press} legend={keys[";"].legend} />
  </div >

  <div class="row">
    <Key press={keys["z"].press} legend={keys["z"].legend} />
    <Key press={keys["x"].press} legend={keys["x"].legend} />
    <Key press={keys["c"].press} legend={keys["c"].legend} />
    <Key press={keys["v"].press} legend={keys["v"].legend} />
    <Key press={keys["b"].press} legend={keys["b"].legend} />
    <Key press={keys["n"].press} legend={keys["n"].legend} />
    <Key press={keys["m"].press} legend={keys["m"].legend} />
    <Key press={keys[","].press} legend={keys[","].legend} />
    <Key press={keys["."].press} legend={keys["."].legend} />
    <Key press={keys["/"].press} legend={keys["/"].legend} />
  </div >

  <div class="row">
    <Key />
    <Key />
    <Key />
    <Key size="key4u" press={keys["[s]"].press} legend={keys["[s]"].legend} />
    <Key />
    <Key />
    <Key />
  </div>
</div>

