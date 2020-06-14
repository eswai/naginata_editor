<script>
	export let text;

	export let keys = {
		"q": {"legend": "Q", "css": "keyoff", "keycode": 81},
		"w": {"legend": "W", "css": "keyoff", "keycode": 87},
		"e": {"legend": "E", "css": "keyoff", "keycode": 69},
		"r": {"legend": "R", "css": "keyoff", "keycode": 82},
		"t": {"legend": "T", "css": "keyoff", "keycode": 84},
		"y": {"legend": "Y", "css": "keyoff", "keycode": 89},
		"u": {"legend": "U", "css": "keyoff", "keycode": 85},
		"i": {"legend": "I", "css": "keyoff", "keycode": 73},
		"o": {"legend": "O", "css": "keyoff", "keycode": 79},
		"p": {"legend": "P", "css": "keyoff", "keycode": 80},
		"a": {"legend": "A", "css": "keyoff", "keycode": 65},
		"s": {"legend": "S", "css": "keyoff", "keycode": 83},
		"d": {"legend": "D", "css": "keyoff", "keycode": 68},
		"f": {"legend": "F", "css": "keyoff", "keycode": 70},
		"g": {"legend": "G", "css": "keyoff", "keycode": 71},
		"h": {"legend": "H", "css": "keyoff", "keycode": 72},
		"j": {"legend": "J", "css": "keyoff", "keycode": 74},
		"k": {"legend": "K", "css": "keyoff", "keycode": 75},
		"l": {"legend": "L", "css": "keyoff", "keycode": 76},
		";": {"legend": ";", "css": "keyoff", "keycode": 187},
		"z": {"legend": "Z", "css": "keyoff", "keycode": 90},
		"x": {"legend": "X", "css": "keyoff", "keycode": 88},
		"c": {"legend": "C", "css": "keyoff", "keycode": 67},
		"v": {"legend": "V", "css": "keyoff", "keycode": 86},
		"b": {"legend": "B", "css": "keyoff", "keycode": 66},
		"m": {"legend": "M", "css": "keyoff", "keycode": 77},
		"n": {"legend": "N", "css": "keyoff", "keycode": 78},
		",": {"legend": ",", "css": "keyoff", "keycode": 188},
		".": {"legend": ".", "css": "keyoff", "keycode": 190},
		"/": {"legend": "/", "css": "keyoff", "keycode": 191},
		"shift": {"legend": "Shift", "css": "keyoff", "keycode": 16},
	};

	function handleType(evt) {
		var kc = evt.which;

		if (kc == 16) {
			keys["shift"].css = "keyon";
		} else {
			for (var k in keys) {
				keys[k].css = "keyoff";
			}
			for (var k in keys) {
				if (keys[k].keycode == kc) {
					keys[k].css = "keyon";
					break;
				}
			}
		}
	}

</script>

<main>
	<input bind:value={text} on:keyup={handleType}>
	<p>Type {text}</p>
	
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
		<div class="key1u {keys["m"].css}">{keys["m"].legend}</div>
		<div class="key1u {keys["n"].css}">{keys["n"].legend}</div>
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

</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	.key1u {
		float: left;
		margin: 2px;
		height:40px;
		width:40px;
		background-color:#ffffff;
		border:1px solid #838383;
		border-radius:4px;
	}

	.key4u {
		float: left;
		margin: 2px;
		height:40px;
		width:178px;
		background-color:#ffffff;
		border:1px solid #838383;
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

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>