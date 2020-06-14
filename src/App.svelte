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
		"-": {"legend": "-", "css": "keyoff", "keycode": 173},
	};

	const naginata = {

// 清音
		"a"     : ["j"              ], // あ
		"i"     : ["k"              ], // い
		"u"     : ["l"              ], // う
		"e"     : ["shift", "o"     ], // え
		"o"     : ["shift", "n"     ], // お
		"ka"    : ["f"              ], // か
		"ki"    : ["w"              ], // き
		"ku"    : ["h"              ], // く
		"ke"    : ["x"              ], // け
		"ko"    : ["v"              ], // こ
		"sa"    : ["shift", "u"     ], // さ
		"si"    : ["r"              ], // し
		"su"    : ["o"              ], // す
		"se"    : ["shift", "a"     ], // せ
		"so"    : ["b"              ], // そ
		"ta"    : ["n"              ], // た
		"ti"    : ["shift", "g"     ], // ち
		"tu"    : ["shift", ";"     ], // つ
		"te"    : ["e"              ], // て
		"to"    : ["d"              ], // と
		"na"    : ["m"              ], // な
		"ni"    : ["shift", "d"     ], // に
		"nu"    : ["shift", "s"     ], // ぬ
		"ne"    : ["shift", "w"     ], // ね
		"no"    : ["shift", "j"     ], // の
		"ha"    : ["c"              ], // は
		"hi"    : ["s"              ], // ひ
		"hu"    : ["shift", "."     ], // ふ
		"he"    : ["p"              ], // へ
		"ho"    : ["z"              ], // ほ
		"ma"    : ["shift", "f"     ], // ま
		"mi"    : ["shift", "b"     ], // み
		"mu"    : ["shift", ","     ], // む
		"me"    : ["shift", "r"     ], // め
		"mo"    : ["shift", "k"     ], // も
		"ya"    : ["shift", "h"     ], // や
		"yu"    : ["shift", "p"     ], // ゆ
		"yo"    : ["shift", "i"     ], // よ
		"ra"    : ["."              ], // ら
		"ri"    : ["shift", "e"     ], // り
		"ru"    : ["i"              ], // る
		"re"    : ["/"              ], // れ
		"ro"    : ["a"              ], // ろ
		"wa"    : ["shift", "l"     ], // わ
		"wo"    : ["shift", "c"     ], // を
		"nn"    : [","              ], // ん
		"-"     : [";"              ], // ー

			// 濁音
		"ga"    : ["j", "f"         ], // が
		"gi"    : ["j", "w"         ], // ぎ
		"gu"    : ["f", "h"         ], // ぐ
		"ge"    : ["j", "x"         ], // げ
		"go"    : ["j", "v"         ], // ご
		"za"    : ["f", "u"         ], // ざ
		"zi"    : ["j", "r"         ], // じ
		"zu"    : ["f", "o"         ], // ず
		"ze"    : ["j", "a"         ], // ぜ
		"zo"    : ["j", "b"         ], // ぞ
		"da"    : ["f", "n"         ], // だ
		"di"    : ["j", "g"         ], // ぢ
		"du"    : ["f", ";"         ], // づ
		"de"    : ["j", "e"         ], // で
		"do"    : ["j", "d"         ], // ど
		"ba"    : ["j", "c"         ], // ば
		"bi"    : ["j", "s"         ], // び
		"bu"    : ["f", "."         ], // ぶ
		"be"    : ["f", "p"         ], // べ
		"bo"    : ["j", "z"         ], // ぼ
		"vu"    : ["f", "l"         ], // ゔ

			// 半濁音
		"pa"    : ["m", "c"         ], // ぱ
		"pi"    : ["m", "s"         ], // ぴ
		"pu"    : ["v", "."         ], // ぷ
		"pe"    : ["v", "p"         ], // ぺ
		"po"    : ["m", "z"         ], // ぽ

			// 清音拗音 濁音拗音 半濁拗音
		"sye"   : ["r", "o"         ], // しぇ
		"sya"   : ["r", "h"         ], // しゃ
		"syu"   : ["r", "p"         ], // しゅ
		"syo"   : ["r", "i"         ], // しょ
		"je"    : ["j", "r", "o"    ], // じぇ
		"ja"    : ["j", "r", "h"    ], // じゃ
		"ju"    : ["j", "r", "p"    ], // じゅ
		"jo"    : ["j", "r", "i"    ], // じょ
		"kya"   : ["w", "h"         ], // きゃ
		"kyu"   : ["w", "p"         ], // きゅ
		"kyo"   : ["w", "i"         ], // きょ
		"gya"   : ["j", "w", "h"    ], // ぎゃ
		"gyu"   : ["j", "w", "p"    ], // ぎゅ
		"gyo"   : ["j", "w", "i"    ], // ぎょ
		"che"   : ["g", "o"         ], // ちぇ
		"cha"   : ["g", "h"         ], // ちゃ
		"chu"   : ["g", "p"         ], // ちゅ
		"cho"   : ["g", "i"         ], // ちょ
		"dye"   : ["j", "g", "o"    ], // ぢぇ
		"dya"   : ["j", "g", "h"    ], // ぢゃ
		"dyu"   : ["j", "g", "p"    ], // ぢゅ
		"dyo"   : ["j", "g", "i"    ], // ぢょ
		"nya"   : ["d", "h"         ], // にゃ
		"nyu"   : ["d", "p"         ], // にゅ
		"nyo"   : ["d", "i"         ], // にょ
		"hya"   : ["s", "h"         ], // ひゃ
		"hyu"   : ["s", "p"         ], // ひゅ
		"hyo"   : ["s", "i"         ], // ひょ
		"bya"   : ["j", "s", "h"    ], // びゃ
		"byu"   : ["j", "s", "p"    ], // びゅ
		"byo"   : ["j", "s", "i"    ], // びょ
		"pya"   : ["m", "s", "h"    ], // ぴゃ
		"pyu"   : ["m", "s", "p"    ], // ぴゅ
		"pyo"   : ["m", "s", "i"    ], // ぴょ
		"mya"   : ["b", "h"         ], // みゃ
		"myu"   : ["b", "p"         ], // みゅ
		"myo"   : ["b", "i"         ], // みょ
		"rya"   : ["e", "h"         ], // りゃ
		"ryu"   : ["e", "p"         ], // りゅ
		"ryo"   : ["e", "i"         ], // りょ

			// 清音外来音 濁音外来音
		"texi"  : ["m", "e", "k"    ], // てぃ
		"texyu" : ["m", "e", "p"    ], // てゅ
		"dexi"  : ["j", "e", "k"    ], // でぃ
		"dexyu" : ["j", "e", "p"    ], // でゅ
		"toxu"  : ["m", "d", "l"    ], // とぅ
		"doxu"  : ["j", "d", "l"    ], // どぅ
		"sixe"  : ["m", "r", "o"    ], // しぇ
		"tixe"  : ["m", "g", "o"    ], // ちぇ
		"jixe"  : ["j", "r", "o"    ], // じぇ
		"dixe"  : ["j", "g", "o"    ], // ぢぇ
		"fa"    : ["v", ".", "j"    ], // ふぁ
		"fi"    : ["v", ".", "k"    ], // ふぃ
		"fe"    : ["v", ".", "o"    ], // ふぇ
		"fo"    : ["v", ".", "n"    ], // ふぉ
		"fyu"   : ["v", ".", "p"    ], // ふゅ
		"uxi"   : ["v", "l", "k"    ], // うぃ
		"uxe"   : ["v", "l", "o"    ], // うぇ
		"uxo"   : ["v", "l", "n"    ], // うぉ
		"va"    : ["f", "l", "j"    ], // ゔぁ
		"vi"    : ["f", "l", "k"    ], // ゔぃ
		"ve"    : ["f", "l", "o"    ], // ゔぇ
		"vo"    : ["f", "l", "n"    ], // ゔぉ
		"vuxyu" : ["f", "l", "p"    ], // ゔゅ
		"kuxa"  : ["v", "h", "j"    ], // くぁ
		"kuxi"  : ["v", "h", "k"    ], // くぃ
		"kuxe"  : ["v", "h", "o"    ], // くぇ
		"kuxo"  : ["v", "h", "n"    ], // くぉ
		"kuxwa" : ["v", "h", "l"    ], // くゎ
		"guxa"  : ["f", "h", "j"    ], // ぐぁ
		"guxi"  : ["f", "h", "k"    ], // ぐぃ
		"guxe"  : ["f", "h", "o"    ], // ぐぇ
		"guxo"  : ["f", "h", "n"    ], // ぐぉ
		"guxwa" : ["f", "h", "l"    ], // ぐゎ
		"tuxa"  : ["v", ";", "j"    ], // つぁ
		"tuxi"  : ["v", ";", "k"    ], // つぃ
		"tuxe"  : ["v", ";", "o"    ], // つぇ
		"tuxo"  : ["v", ";", "n"    ], // つぉ

			// 小書き
		"xya"   : ["q", "h"         ], // ゃ
		"xyu"   : ["q", "p"         ], // ゅ
		"xyo"   : ["q", "i"         ], // ょ
		"xa"    : ["q", "j"         ], // ぁ
		"xi"    : ["q", "k"         ], // ぃ
		"xu"    : ["q", "l"         ], // ぅ
		"xe"    : ["q", "o"         ], // ぇ
		"xo"    : ["q", "n"         ], // ぉ
		"xwa"   : ["q", "l"         ], // ゎ
		"xtu"   : ["g"              ], // っ

		"."     : ["m", "shift"     ],
		","     : ["v", "shift"     ],
	};

	var buffer = "";
	var lbuffer = "";

	function keyoff() {
		for (var k in keys) {
			keys[k].css = "keyoff";
		}
	}

	function seachKey(buf, n) {
		if (buf.length >= n) {
		　var bufn = buf.substr(-n+1)
			// console.log(bufn);
			for (var n in naginata) {
				if (n == bufn) {
					keyoff();
					for (var k of naginata[n]) {
						keys[k].css = "keyon";
					}
					return true;
				}
			}
		}
		return false;
	}

	function handleType(evt) {
		var kc = evt.which;

		for (var k in keys) {
			if (keys[k].keycode == kc) {
				buffer += k;
				lbuffer += k;
				console.log([buffer, lbuffer]);
				break;
			}
		}

		keyoff();

		if (kc == 8) { // backspace
			buffer = "";
			keys["u"].css = "keyon";
		}
		if (kc == 13) { // enter
			buffer = "";
			keys["v"].css = "keyon";
			keys["m"].css = "keyon";
		}
		if (kc == 32) { // space
			buffer = "";
			keys["shift"].css = "keyon";
		}

		for (var n in naginata) {
			if (n == buffer) {
				for (var k of naginata[n]) {
					keys[k].css = "keyon";
				}
				buffer = "";
				break;
			}
		}

		seachKey(lbuffer, 4);
		seachKey(lbuffer, 5);
		seachKey(lbuffer, 6);
		
		if (buffer.length > 4) buffer = "";
		lbuffer = lbuffer.substr(-10);
	}

</script>

<main>
	<h1>薙刀式を可視化するエディター</h1>
	<textarea bind:value={text} on:keyup={handleType}></textarea>
	
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

</main>

<style>
	main {
		margin: 0 auto;
	}

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

	h1 {
		color: #008f18;
		text-transform: uppercase;
		font-size: 30px;
		font-weight: 100;
	}

	textarea {
		width: 80%; 
		height: 100px; 
		font-size: 20px;
		margin-bottom: 10px;
	}

	@media (min-width: 640px) {
		main {
			max-width: 800px;
		}
	}
</style>