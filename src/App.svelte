<script>
	import Keyboard from './Keyboard.svelte';

	let text = "";
	let kanatext = [];
	let highlight = [];
	let kanahtml = "";

	const naginata = {

// 清音
		"a"     : {"key": ["j"              ],  "kana": "あ"},
		"i"     : {"key": ["k"              ],  "kana": "い"},
		"u"     : {"key": ["l"              ],  "kana": "う"},
		"e"     : {"key": ["[s]", "o"       ],  "kana": "え"},
		"o"     : {"key": ["[s]", "n"       ],  "kana": "お"},
		"ka"    : {"key": ["f"              ],  "kana": "か"},
		"ki"    : {"key": ["w"              ],  "kana": "き"},
		"ku"    : {"key": ["h"              ],  "kana": "く"},
		"ke"    : {"key": ["x"              ],  "kana": "け"},
		"ko"    : {"key": ["v"              ],  "kana": "こ"},
		"sa"    : {"key": ["[s]", "u"       ],  "kana": "さ"},
		"si"    : {"key": ["r"              ],  "kana": "し"},
		"su"    : {"key": ["o"              ],  "kana": "す"},
		"se"    : {"key": ["[s]", "a"       ],  "kana": "せ"},
		"so"    : {"key": ["b"              ],  "kana": "そ"},
		"ta"    : {"key": ["n"              ],  "kana": "た"},
		"ti"    : {"key": ["[s]", "g"       ],  "kana": "ち"},
		"tu"    : {"key": ["[s]", ";"       ],  "kana": "つ"},
		"te"    : {"key": ["e"              ],  "kana": "て"},
		"to"    : {"key": ["d"              ],  "kana": "と"},
		"na"    : {"key": ["m"              ],  "kana": "な"},
		"ni"    : {"key": ["[s]", "d"       ],  "kana": "に"},
		"nu"    : {"key": ["[s]", "s"       ],  "kana": "ぬ"},
		"ne"    : {"key": ["[s]", "w"       ],  "kana": "ね"},
		"no"    : {"key": ["[s]", "j"       ],  "kana": "の"},
		"ha"    : {"key": ["c"              ],  "kana": "は"},
		"hi"    : {"key": ["s"              ],  "kana": "ひ"},
		"hu"    : {"key": ["[s]", "."       ],  "kana": "ふ"},
		"he"    : {"key": ["p"              ],  "kana": "へ"},
		"ho"    : {"key": ["z"              ],  "kana": "ほ"},
		"ma"    : {"key": ["[s]", "f"       ],  "kana": "ま"},
		"mi"    : {"key": ["[s]", "b"       ],  "kana": "み"},
		"mu"    : {"key": ["[s]", ","       ],  "kana": "む"},
		"me"    : {"key": ["[s]", "r"       ],  "kana": "め"},
		"mo"    : {"key": ["[s]", "k"       ],  "kana": "も"},
		"ya"    : {"key": ["[s]", "h"       ],  "kana": "や"},
		"yu"    : {"key": ["[s]", "p"       ],  "kana": "ゆ"},
		"yo"    : {"key": ["[s]", "i"       ],  "kana": "よ"},
		"ra"    : {"key": ["."              ],  "kana": "ら"},
		"ri"    : {"key": ["[s]", "e"       ],  "kana": "り"},
		"ru"    : {"key": ["i"              ],  "kana": "る"},
		"re"    : {"key": ["/"              ],  "kana": "れ"},
		"ro"    : {"key": ["a"              ],  "kana": "ろ"},
		"wa"    : {"key": ["[s]", "l"       ],  "kana": "わ"},
		"wo"    : {"key": ["[s]", "c"       ],  "kana": "を"},
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
		"zye"   : {"key": ["j", "r", "o"    ], "kana": "じぇ"},
		"zya"   : {"key": ["j", "r", "h"    ], "kana": "じゃ"},
		"zyu"   : {"key": ["j", "r", "p"    ], "kana": "じゅ"},
		"zyo"   : {"key": ["j", "r", "i"    ], "kana": "じょ"},
		"kya"   : {"key": ["w", "h"         ], "kana": "きゃ"},
		"kyu"   : {"key": ["w", "p"         ], "kana": "きゅ"},
		"kyo"   : {"key": ["w", "i"         ], "kana": "きょ"},
		"gya"   : {"key": ["j", "w", "h"    ], "kana": "ぎゃ"},
		"gyu"   : {"key": ["j", "w", "p"    ], "kana": "ぎゅ"},
		"gyo"   : {"key": ["j", "w", "i"    ], "kana": "ぎょ"},
		"tye"   : {"key": ["g", "o"         ], "kana": "ちぇ"},
		"tya"   : {"key": ["g", "h"         ], "kana": "ちゃ"},
		"tyu"   : {"key": ["g", "p"         ], "kana": "ちゅ"},
		"tyo"   : {"key": ["g", "i"         ], "kana": "ちょ"},
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
		"thi"   : {"key": ["m", "e", "k"    ], "kana": "てぃ"},
		"texyu" : {"key": ["m", "e", "p"    ], "kana": "てゅ"},
		"dhi"   : {"key": ["j", "e", "k"    ], "kana": "でぃ"},
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
		"wi"    : {"key": ["v", "l", "k"    ], "kana": "うぃ"},
		"we"    : {"key": ["v", "l", "o"    ], "kana": "うぇ"},
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

		"."     : {"key": ["m", "[s]"       ], "kana": "。"},
		","     : {"key": ["v", "[s]"       ], "kana": "、"},
	};

	var buffer = [];
	var lbuffer = [];

	function seachKey(buf, n) {
		if (buf.length >= n) {
		　var bufn = buf.slice(buf.length - n);
			// console.log(bufn.join(""));
			for (var n in naginata) {
				if (n == bufn.join("")) {
					highlight = [];
					for (var k of naginata[n].key) {
						highlight.push(k);
					}
					return true;
				}
			}
		}
		return false;
	}

	function handleType(evt) {
		var kc = evt.key;
		// console.log(kc);

		if (kc.length == 1) {
			buffer.push(kc);
			lbuffer.push(kc);
		}
		// console.log([buffer, lbuffer]);

		highlight = [];

		if (kc == "Backspace") {
			buffer = [];
			lbuffer = [];
			highlight.push("u");
			kanatext.push(["BS", ["U"]]);
		}
		if (kc == "Enter") {
			buffer = [];
			lbuffer = [];
			highlight.push("v");
			highlight.push("m");
			kanatext.push(["Ent", ["V", "M"]]);
		}
		if (kc == " ") {
			buffer = [];
			lbuffer = [];
			highlight.push("[s]");
			kanatext.push(["Sp", ["[S]"]]);
		}

		for (var n in naginata) {
			if (n == buffer.join("")) {
				kanatext.push([naginata[n].kana, naginata[n].key]);
				for (var k of naginata[n].key) {
					highlight.push(k);
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

		kanatext = kanatext.slice(-20);
		kanahtml = kanatext.map(function(value, index, array) {
			let a = "<div>" + value[0] + "</div>";
			let b = value[1].map(function(v2, i2, a2) {
				return "<div class='key'>" + v2.toUpperCase() + "</div>";
			}).join("");
		  return "<div class='tate'>" + a + b + "</div>";
		}).join("");
	}
</script>

<main>
	<h1>薙刀式を可視化するエディター</h1>
	<textarea bind:value={text} on:keyup={handleType}></textarea>
	<p class="kana" >{@html kanahtml}</p>
	
	<Keyboard highlight={highlight} />

</main>

<style>
	main {
		margin: 0 auto;
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

	.kana {
		font-size: 20px;
		display: flex;
		align-items: baseline;
	}

	.tate {
		flex-direction: column;
		align-items: center;
	}

	.key {
		font-size: 20px;
		border:1px solid #bebebe;
    border-radius:4px;
	}

	@media (min-width: 640px) {
		main {
			max-width: 800px;
		}
	}
</style>