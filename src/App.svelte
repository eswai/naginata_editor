<script>
	export let text;
	export let kanatext = "";

	export let keys = {
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

	const naginata = {

// 清音
		"a"     : {"key": ["j"              ],  "kana": "あ"},
		"i"     : {"key": ["k"              ],  "kana": "い"},
		"u"     : {"key": ["l"              ],  "kana": "う"},
		"e"     : {"key": ["shift", "o"     ],  "kana": "え"},
		"o"     : {"key": ["shift", "n"     ],  "kana": "お"},
		"ka"    : {"key": ["f"              ],  "kana": "か"},
		"ki"    : {"key": ["w"              ],  "kana": "き"},
		"ku"    : {"key": ["h"              ],  "kana": "く"},
		"ke"    : {"key": ["x"              ],  "kana": "け"},
		"ko"    : {"key": ["v"              ],  "kana": "こ"},
		"sa"    : {"key": ["shift", "u"     ],  "kana": "さ"},
		"si"    : {"key": ["r"              ],  "kana": "し"},
		"su"    : {"key": ["o"              ],  "kana": "す"},
		"se"    : {"key": ["shift", "a"     ],  "kana": "せ"},
		"so"    : {"key": ["b"              ],  "kana": "そ"},
		"ta"    : {"key": ["n"              ],  "kana": "た"},
		"ti"    : {"key": ["shift", "g"     ],  "kana": "ち"},
		"tu"    : {"key": ["shift", ";"     ],  "kana": "つ"},
		"te"    : {"key": ["e"              ],  "kana": "て"},
		"to"    : {"key": ["d"              ],  "kana": "と"},
		"na"    : {"key": ["m"              ],  "kana": "な"},
		"ni"    : {"key": ["shift", "d"     ],  "kana": "に"},
		"nu"    : {"key": ["shift", "s"     ],  "kana": "ぬ"},
		"ne"    : {"key": ["shift", "w"     ],  "kana": "ね"},
		"no"    : {"key": ["shift", "j"     ],  "kana": "の"},
		"ha"    : {"key": ["c"              ],  "kana": "は"},
		"hi"    : {"key": ["s"              ],  "kana": "ひ"},
		"hu"    : {"key": ["shift", "."     ],  "kana": "ふ"},
		"he"    : {"key": ["p"              ],  "kana": "へ"},
		"ho"    : {"key": ["z"              ],  "kana": "ほ"},
		"ma"    : {"key": ["shift", "f"     ],  "kana": "ま"},
		"mi"    : {"key": ["shift", "b"     ],  "kana": "み"},
		"mu"    : {"key": ["shift", ","     ],  "kana": "む"},
		"me"    : {"key": ["shift", "r"     ],  "kana": "め"},
		"mo"    : {"key": ["shift", "k"     ],  "kana": "も"},
		"ya"    : {"key": ["shift", "h"     ],  "kana": "や"},
		"yu"    : {"key": ["shift", "p"     ],  "kana": "ゆ"},
		"yo"    : {"key": ["shift", "i"     ],  "kana": "よ"},
		"ra"    : {"key": ["."              ],  "kana": "ら"},
		"ri"    : {"key": ["shift", "e"     ],  "kana": "り"},
		"ru"    : {"key": ["i"              ],  "kana": "る"},
		"re"    : {"key": ["/"              ],  "kana": "れ"},
		"ro"    : {"key": ["a"              ],  "kana": "ろ"},
		"wa"    : {"key": ["shift", "l"     ],  "kana": "わ"},
		"wo"    : {"key": ["shift", "c"     ],  "kana": "を"},
		"nn"    : {"key": [","              ],  "kana": "ん"},
		"-"     : {"key": [";"              ],  "kana": "ー"},

			// 濁音
		"ga"    : {"key": ["j", "f"         ], "kana": "が"},
		"gi"    : {"key": ["j", "w"         ], "kana": "ぎ"},
		"gu"    : {"key": ["f", "h"         ], "kana": "ぐ"},
		"ge"    : {"key": ["j", "x"         ], "kana": "げ"},
		"go"    : {"key": ["j", "v"         ], "kana": "ご"},
		"za"    : {"key": ["f", "u"         ], "kana": "ざ"},
		"zi"    : {"key": ["j", "r"         ], "kana": "じ"},
		"zu"    : {"key": ["f", "o"         ], "kana": "ず"},
		"ze"    : {"key": ["j", "a"         ], "kana": "ぜ"},
		"zo"    : {"key": ["j", "b"         ], "kana": "ぞ"},
		"da"    : {"key": ["f", "n"         ], "kana": "だ"},
		"di"    : {"key": ["j", "g"         ], "kana": "ぢ"},
		"du"    : {"key": ["f", ";"         ], "kana": "づ"},
		"de"    : {"key": ["j", "e"         ], "kana": "で"},
		"do"    : {"key": ["j", "d"         ], "kana": "ど"},
		"ba"    : {"key": ["j", "c"         ], "kana": "ば"},
		"bi"    : {"key": ["j", "s"         ], "kana": "び"},
		"bu"    : {"key": ["f", "."         ], "kana": "ぶ"},
		"be"    : {"key": ["f", "p"         ], "kana": "べ"},
		"bo"    : {"key": ["j", "z"         ], "kana": "ぼ"},
		"vu"    : {"key": ["f", "l"         ], "kana": "ゔ"},

			// 半濁音
		"pa"    : {"key": ["m", "c"         ], "kana": "ぱ"},
		"pi"    : {"key": ["m", "s"         ], "kana": "ぴ"},
		"pu"    : {"key": ["v", "."         ], "kana": "ぷ"},
		"pe"    : {"key": ["v", "p"         ], "kana": "ぺ"},
		"po"    : {"key": ["m", "z"         ], "kana": "ぽ"},

			// 清音拗音 濁音拗音 半濁拗音
		"sye"   : {"key": ["r", "o"         ], "kana": "しぇ"},
		"sya"   : {"key": ["r", "h"         ], "kana": "しゃ"},
		"syu"   : {"key": ["r", "p"         ], "kana": "しゅ"},
		"syo"   : {"key": ["r", "i"         ], "kana": "しょ"},
		"je"    : {"key": ["j", "r", "o"    ], "kana": "じぇ"},
		"ja"    : {"key": ["j", "r", "h"    ], "kana": "じゃ"},
		"ju"    : {"key": ["j", "r", "p"    ], "kana": "じゅ"},
		"jo"    : {"key": ["j", "r", "i"    ], "kana": "じょ"},
		"kya"   : {"key": ["w", "h"         ], "kana": "きゃ"},
		"kyu"   : {"key": ["w", "p"         ], "kana": "きゅ"},
		"kyo"   : {"key": ["w", "i"         ], "kana": "きょ"},
		"gya"   : {"key": ["j", "w", "h"    ], "kana": "ぎゃ"},
		"gyu"   : {"key": ["j", "w", "p"    ], "kana": "ぎゅ"},
		"gyo"   : {"key": ["j", "w", "i"    ], "kana": "ぎょ"},
		"che"   : {"key": ["g", "o"         ], "kana": "ちぇ"},
		"cha"   : {"key": ["g", "h"         ], "kana": "ちゃ"},
		"chu"   : {"key": ["g", "p"         ], "kana": "ちゅ"},
		"cho"   : {"key": ["g", "i"         ], "kana": "ちょ"},
		"dye"   : {"key": ["j", "g", "o"    ], "kana": "ぢぇ"},
		"dya"   : {"key": ["j", "g", "h"    ], "kana": "ぢゃ"},
		"dyu"   : {"key": ["j", "g", "p"    ], "kana": "ぢゅ"},
		"dyo"   : {"key": ["j", "g", "i"    ], "kana": "ぢょ"},
		"nya"   : {"key": ["d", "h"         ], "kana": "にゃ"},
		"nyu"   : {"key": ["d", "p"         ], "kana": "にゅ"},
		"nyo"   : {"key": ["d", "i"         ], "kana": "にょ"},
		"hya"   : {"key": ["s", "h"         ], "kana": "ひゃ"},
		"hyu"   : {"key": ["s", "p"         ], "kana": "ひゅ"},
		"hyo"   : {"key": ["s", "i"         ], "kana": "ひょ"},
		"bya"   : {"key": ["j", "s", "h"    ], "kana": "びゃ"},
		"byu"   : {"key": ["j", "s", "p"    ], "kana": "びゅ"},
		"byo"   : {"key": ["j", "s", "i"    ], "kana": "びょ"},
		"pya"   : {"key": ["m", "s", "h"    ], "kana": "ぴゃ"},
		"pyu"   : {"key": ["m", "s", "p"    ], "kana": "ぴゅ"},
		"pyo"   : {"key": ["m", "s", "i"    ], "kana": "ぴょ"},
		"mya"   : {"key": ["b", "h"         ], "kana": "みゃ"},
		"myu"   : {"key": ["b", "p"         ], "kana": "みゅ"},
		"myo"   : {"key": ["b", "i"         ], "kana": "みょ"},
		"rya"   : {"key": ["e", "h"         ], "kana": "りゃ"},
		"ryu"   : {"key": ["e", "p"         ], "kana": "りゅ"},
		"ryo"   : {"key": ["e", "i"         ], "kana": "りょ"},

			// 清音外来音 濁音外来音
		"texi"  : {"key": ["m", "e", "k"    ], "kana": "てぃ"},
		"texyu" : {"key": ["m", "e", "p"    ], "kana": "てゅ"},
		"dexi"  : {"key": ["j", "e", "k"    ], "kana": "でぃ"},
		"dexyu" : {"key": ["j", "e", "p"    ], "kana": "でゅ"},
		"toxu"  : {"key": ["m", "d", "l"    ], "kana": "とぅ"},
		"doxu"  : {"key": ["j", "d", "l"    ], "kana": "どぅ"},
		"sixe"  : {"key": ["m", "r", "o"    ], "kana": "しぇ"},
		"tixe"  : {"key": ["m", "g", "o"    ], "kana": "ちぇ"},
		"jixe"  : {"key": ["j", "r", "o"    ], "kana": "じぇ"},
		"dixe"  : {"key": ["j", "g", "o"    ], "kana": "ぢぇ"},
		"fa"    : {"key": ["v", ".", "j"    ], "kana": "ふぁ"},
		"fi"    : {"key": ["v", ".", "k"    ], "kana": "ふぃ"},
		"fe"    : {"key": ["v", ".", "o"    ], "kana": "ふぇ"},
		"fo"    : {"key": ["v", ".", "n"    ], "kana": "ふぉ"},
		"fyu"   : {"key": ["v", ".", "p"    ], "kana": "ふゅ"},
		"uxi"   : {"key": ["v", "l", "k"    ], "kana": "うぃ"},
		"uxe"   : {"key": ["v", "l", "o"    ], "kana": "うぇ"},
		"uxo"   : {"key": ["v", "l", "n"    ], "kana": "うぉ"},
		"va"    : {"key": ["f", "l", "j"    ], "kana": "ゔぁ"},
		"vi"    : {"key": ["f", "l", "k"    ], "kana": "ゔぃ"},
		"ve"    : {"key": ["f", "l", "o"    ], "kana": "ゔぇ"},
		"vo"    : {"key": ["f", "l", "n"    ], "kana": "ゔぉ"},
		"vuxyu" : {"key": ["f", "l", "p"    ], "kana": "ゔゅ"},
		"kuxa"  : {"key": ["v", "h", "j"    ], "kana": "くぁ"},
		"kuxi"  : {"key": ["v", "h", "k"    ], "kana": "くぃ"},
		"kuxe"  : {"key": ["v", "h", "o"    ], "kana": "くぇ"},
		"kuxo"  : {"key": ["v", "h", "n"    ], "kana": "くぉ"},
		"kuxwa" : {"key": ["v", "h", "l"    ], "kana": "くゎ"},
		"guxa"  : {"key": ["f", "h", "j"    ], "kana": "ぐぁ"},
		"guxi"  : {"key": ["f", "h", "k"    ], "kana": "ぐぃ"},
		"guxe"  : {"key": ["f", "h", "o"    ], "kana": "ぐぇ"},
		"guxo"  : {"key": ["f", "h", "n"    ], "kana": "ぐぉ"},
		"guxwa" : {"key": ["f", "h", "l"    ], "kana": "ぐゎ"},
		"tuxa"  : {"key": ["v", ";", "j"    ], "kana": "つぁ"},
		"tuxi"  : {"key": ["v", ";", "k"    ], "kana": "つぃ"},
		"tuxe"  : {"key": ["v", ";", "o"    ], "kana": "つぇ"},
		"tuxo"  : {"key": ["v", ";", "n"    ], "kana": "つぉ"},

			// 小書き
		"xya"   : {"key": ["q", "h"         ], "kana": "ゃ"},
		"xyu"   : {"key": ["q", "p"         ], "kana": "ゅ"},
		"xyo"   : {"key": ["q", "i"         ], "kana": "ょ"},
		"xa"    : {"key": ["q", "j"         ], "kana": "ぁ"},
		"xi"    : {"key": ["q", "k"         ], "kana": "ぃ"},
		"xu"    : {"key": ["q", "l"         ], "kana": "ぅ"},
		"xe"    : {"key": ["q", "o"         ], "kana": "ぇ"},
		"xo"    : {"key": ["q", "n"         ], "kana": "ぉ"},
		"xwa"   : {"key": ["q", "l"         ], "kana": "ゎ"},
		"xtu"   : {"key": ["g"              ], "kana": "っ"},

		"."     : {"key": ["m", "shift"     ], "kana": "。"},
		","     : {"key": ["v", "shift"     ], "kana": "、"},
	};

	var buffer = [];
	var lbuffer = [];

	function keyoff() {
		for (var k in keys) {
			keys[k].css = "keyoff";
		}
	}

	function seachKey(buf, n) {
		if (buf.length >= n) {
		　var bufn = buf.slice(buf.length - n);
			console.log(bufn.join(""));
			for (var n in naginata) {
				if (n == bufn.join("")) {
					keyoff();
					for (var k of naginata[n].key) {
						keys[k].css = "keyon";
					}
					return true;
				}
			}
		}
		return false;
	}

	function handleType(evt) {
		var kc = evt.key;
		console.log(kc);

		if (kc.length == 1) {
			buffer.push(kc);
			lbuffer.push(kc);			
		}
		console.log([buffer, lbuffer]);

		keyoff();

		if (kc == "Backspace") {
			buffer = [];
			lbuffer = [];
			keys["u"].css = "keyon";
			kanatext += "BS";
		}
		if (kc == "Enter") {
			buffer = [];
			lbuffer = [];
			keys["v"].css = "keyon";
			keys["m"].css = "keyon";
			kanatext += "Ent";
		}
		if (kc == " ") {
			buffer = [];
			lbuffer = [];
			keys["shift"].css = "keyon";
			kanatext += "Sp";
		}

		for (var n in naginata) {
			if (n == buffer.join("")) {
				kanatext += naginata[n].kana;
				for (var k of naginata[n].key) {
					keys[k].css = "keyon";
				}
				buffer = [];
				break;
			}
		}

		seachKey(lbuffer, 3);
		seachKey(lbuffer, 4);
		seachKey(lbuffer, 5);
		
		if (buffer.length > 4) buffer = [];
		if (lbuffer.length > 10) lbuffer = lbuffer.slice(1);
	}

</script>

<main>
	<h1>薙刀式を可視化するエディター</h1>
	<textarea bind:value={text} on:keyup={handleType}></textarea>
	<p>{kanatext}</p>
	
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