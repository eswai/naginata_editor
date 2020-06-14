<script>
	export let name;

	export let keys = {
		"q": {"legend": "Q", "css": "key1u"},
		"w": {"legend": "W", "css": "key1u"},
		"e": {"legend": "E", "css": "key1u"},
		"r": {"legend": "R", "css": "key1u"},
		"t": {"legend": "T", "css": "key1u"},
		"y": {"legend": "Y", "css": "key1u"},
		"u": {"legend": "U", "css": "key1u"},
		"i": {"legend": "I", "css": "key1u"},
		"o": {"legend": "O", "css": "key1u"},
		"p": {"legend": "P", "css": "key1u"},
		"a": {"legend": "A", "css": "key1u"},
		"s": {"legend": "S", "css": "key1u"},
		"d": {"legend": "D", "css": "key1u"},
		"f": {"legend": "F", "css": "key1u"},
		"g": {"legend": "G", "css": "key1u"},
		"h": {"legend": "H", "css": "key1u"},
		"j": {"legend": "J", "css": "key1u"},
		"k": {"legend": "K", "css": "key1u"},
		"l": {"legend": "L", "css": "key1u"},
		";": {"legend": ";", "css": "key1u"},
		"z": {"legend": "Z", "css": "key1u"},
		"x": {"legend": "X", "css": "key1u"},
		"c": {"legend": "C", "css": "key1u"},
		"v": {"legend": "V", "css": "key1u"},
		"b": {"legend": "B", "css": "key1u"},
		"m": {"legend": "M", "css": "key1u"},
		"n": {"legend": "N", "css": "key1u"},
		",": {"legend": ",", "css": "key1u"},
		".": {"legend": ".", "css": "key1u"},
		"/": {"legend": "/", "css": "key1u"},
	};

	function handleType() {
		for (var k in keys) {
			keys[k].css = "key1u";
		}
		keys[name[name.length-1]].css = "key1ut"
	}
</script>

<main>
	<input bind:value={name} on:input={handleType}>
	<p>Type {name}</p>
	
	<div class="row">
		<div class="{keys["q"]["css"]}">{keys["q"]["legend"]}</div>
		<div class="{keys["w"]["css"]}">{keys["w"]["legend"]}</div>
		<div class="{keys["e"]["css"]}">{keys["e"]["legend"]}</div>
		<div class="{keys["r"]["css"]}">{keys["r"]["legend"]}</div>
		<div class="{keys["t"]["css"]}">{keys["t"]["legend"]}</div>
		<div class="{keys["y"]["css"]}">{keys["y"]["legend"]}</div>
		<div class="{keys["u"]["css"]}">{keys["u"]["legend"]}</div>
		<div class="{keys["i"]["css"]}">{keys["i"]["legend"]}</div>
		<div class="{keys["o"]["css"]}">{keys["o"]["legend"]}</div>
		<div class="{keys["p"]["css"]}">{keys["p"]["legend"]}</div>
	</div>

	<div class="row">
		<div class="{keys["a"]["css"]}">{keys["a"]["legend"]}</div>
		<div class="{keys["s"]["css"]}">{keys["s"]["legend"]}</div>
		<div class="{keys["d"]["css"]}">{keys["d"]["legend"]}</div>
		<div class="{keys["f"]["css"]}">{keys["f"]["legend"]}</div>
		<div class="{keys["g"]["css"]}">{keys["g"]["legend"]}</div>
		<div class="{keys["h"]["css"]}">{keys["h"]["legend"]}</div>
		<div class="{keys["j"]["css"]}">{keys["j"]["legend"]}</div>
		<div class="{keys["k"]["css"]}">{keys["k"]["legend"]}</div>
		<div class="{keys["l"]["css"]}">{keys["l"]["legend"]}</div>
		<div class="{keys[";"]["css"]}">{keys[";"]["legend"]}</div>
	</div>

	<div class="row">
		<div class="{keys["z"]["css"]}">{keys["z"]["legend"]}</div>
		<div class="{keys["x"]["css"]}">{keys["x"]["legend"]}</div>
		<div class="{keys["c"]["css"]}">{keys["c"]["legend"]}</div>
		<div class="{keys["v"]["css"]}">{keys["v"]["legend"]}</div>
		<div class="{keys["b"]["css"]}">{keys["b"]["legend"]}</div>
		<div class="{keys["m"]["css"]}">{keys["m"]["legend"]}</div>
		<div class="{keys["n"]["css"]}">{keys["n"]["legend"]}</div>
		<div class="{keys[","]["css"]}">{keys[","]["legend"]}</div>
		<div class="{keys["."]["css"]}">{keys["."]["legend"]}</div>
		<div class="{keys["/"]["css"]}">{keys["/"]["legend"]}</div>
	</div>

	<div class="row">
		<div class="key1u"></div>
		<div class="key1u"></div>
		<div class="key1u"></div>
		<div class="key2u"></div>
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

	.key1ut {
		float: left;
		margin: 2px;
		height:40px;
		width:40px;
		background-color:#caffbd;
		border:1px solid #838383;
		border-radius:4px;
	}

	.key2u {
		float: left;
		margin: 2px;
		height:40px;
		width:178px;
		background-color:#ffffff;
		border:1px solid #838383;
		border-radius:4px;
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