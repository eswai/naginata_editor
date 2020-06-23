<script>
	import Keyboard from './Keyboard.svelte';

	let text = "";
	let kanatext = [];
	let highlight = [];
	let kanahtml = "";

	const naginata = {

// 清音
		"a"     : {"key": ["j"              ],  "kana": "あ", "del": 0},
		"i"     : {"key": ["k"              ],  "kana": "い", "del": 0},
		"u"     : {"key": ["l"              ],  "kana": "う", "del": 0},
		"e"     : {"key": ["[s]", "o"       ],  "kana": "え", "del": 0},
		"o"     : {"key": ["[s]", "n"       ],  "kana": "お", "del": 0},
		"ka"    : {"key": ["f"              ],  "kana": "か", "del": 0},
		"ki"    : {"key": ["w"              ],  "kana": "き", "del": 0},
		"ku"    : {"key": ["h"              ],  "kana": "く", "del": 0},
		"ke"    : {"key": ["x"              ],  "kana": "け", "del": 0},
		"ko"    : {"key": ["v"              ],  "kana": "こ", "del": 0},
		"sa"    : {"key": ["[s]", "u"       ],  "kana": "さ", "del": 0},
		"si"    : {"key": ["r"              ],  "kana": "し", "del": 0},
		"su"    : {"key": ["o"              ],  "kana": "す", "del": 0},
		"se"    : {"key": ["[s]", "a"       ],  "kana": "せ", "del": 0},
		"so"    : {"key": ["b"              ],  "kana": "そ", "del": 0},
		"ta"    : {"key": ["n"              ],  "kana": "た", "del": 0},
		"ti"    : {"key": ["[s]", "g"       ],  "kana": "ち", "del": 0},
		"tu"    : {"key": ["[s]", ";"       ],  "kana": "つ", "del": 0},
		"te"    : {"key": ["e"              ],  "kana": "て", "del": 0},
		"to"    : {"key": ["d"              ],  "kana": "と", "del": 0},
		"na"    : {"key": ["m"              ],  "kana": "な", "del": 0},
		"ni"    : {"key": ["[s]", "d"       ],  "kana": "に", "del": 0},
		"nu"    : {"key": ["[s]", "s"       ],  "kana": "ぬ", "del": 0},
		"ne"    : {"key": ["[s]", "w"       ],  "kana": "ね", "del": 0},
		"no"    : {"key": ["[s]", "j"       ],  "kana": "の", "del": 0},
		"ha"    : {"key": ["c"              ],  "kana": "は", "del": 0},
		"hi"    : {"key": ["s"              ],  "kana": "ひ", "del": 0},
		"hu"    : {"key": ["[s]", "."       ],  "kana": "ふ", "del": 0},
		"he"    : {"key": ["p"              ],  "kana": "へ", "del": 0},
		"ho"    : {"key": ["z"              ],  "kana": "ほ", "del": 0},
		"ma"    : {"key": ["[s]", "f"       ],  "kana": "ま", "del": 0},
		"mi"    : {"key": ["[s]", "b"       ],  "kana": "み", "del": 0},
		"mu"    : {"key": ["[s]", ","       ],  "kana": "む", "del": 0},
		"me"    : {"key": ["[s]", "r"       ],  "kana": "め", "del": 0},
		"mo"    : {"key": ["[s]", "k"       ],  "kana": "も", "del": 0},
		"ya"    : {"key": ["[s]", "h"       ],  "kana": "や", "del": 0},
		"yu"    : {"key": ["[s]", "p"       ],  "kana": "ゆ", "del": 0},
		"yo"    : {"key": ["[s]", "i"       ],  "kana": "よ", "del": 0},
		"ra"    : {"key": ["."              ],  "kana": "ら", "del": 0},
		"ri"    : {"key": ["[s]", "e"       ],  "kana": "り", "del": 0},
		"ru"    : {"key": ["i"              ],  "kana": "る", "del": 0},
		"re"    : {"key": ["/"              ],  "kana": "れ", "del": 0},
		"ro"    : {"key": ["a"              ],  "kana": "ろ", "del": 0},
		"wa"    : {"key": ["[s]", "l"       ],  "kana": "わ", "del": 0},
		"wo"    : {"key": ["[s]", "c"       ],  "kana": "を", "del": 0},
		"nn"    : {"key": [","              ],  "kana": "ん", "del": 0},
		"-"     : {"key": [";"              ],  "kana": "ー", "del": 0},

			// 濁音
		"ga"    : {"key": ["f", "j"         ], "kana": "が", "del": 0},
		"gi"    : {"key": ["w", "j"         ], "kana": "ぎ", "del": 0},
		"gu"    : {"key": ["f", "h"         ], "kana": "ぐ", "del": 0},
		"ge"    : {"key": ["x", "j"         ], "kana": "げ", "del": 0},
		"go"    : {"key": ["v", "j"         ], "kana": "ご", "del": 0},
		"za"    : {"key": ["f", "u"         ], "kana": "ざ", "del": 0},
		"zi"    : {"key": ["r", "j"         ], "kana": "じ", "del": 0},
		"zu"    : {"key": ["f", "o"         ], "kana": "ず", "del": 0},
		"ze"    : {"key": ["a", "j"         ], "kana": "ぜ", "del": 0},
		"zo"    : {"key": ["b", "j"         ], "kana": "ぞ", "del": 0},
		"da"    : {"key": ["f", "n"         ], "kana": "だ", "del": 0},
		"di"    : {"key": ["g", "j"         ], "kana": "ぢ", "del": 0},
		"du"    : {"key": ["f", ";"         ], "kana": "づ", "del": 0},
		"de"    : {"key": ["e", "j"         ], "kana": "で", "del": 0},
		"do"    : {"key": ["d", "j"         ], "kana": "ど", "del": 0},
		"ba"    : {"key": ["c", "j"         ], "kana": "ば", "del": 0},
		"bi"    : {"key": ["s", "j"         ], "kana": "び", "del": 0},
		"bu"    : {"key": ["f", "."         ], "kana": "ぶ", "del": 0},
		"be"    : {"key": ["f", "p"         ], "kana": "べ", "del": 0},
		"bo"    : {"key": ["z", "j"         ], "kana": "ぼ", "del": 0},
		"vu"    : {"key": ["f", "l"         ], "kana": "ゔ", "del": 0},

			// 半濁音
		"pa"    : {"key": ["c", "m"         ], "kana": "ぱ", "del": 0},
		"pi"    : {"key": ["s", "m"         ], "kana": "ぴ", "del": 0},
		"pu"    : {"key": ["v", "."         ], "kana": "ぷ", "del": 0},
		"pe"    : {"key": ["v", "p"         ], "kana": "ぺ", "del": 0},
		"po"    : {"key": ["z", "m"         ], "kana": "ぽ", "del": 0},

			// 清音拗音 濁音拗音 半濁拗音
		"sye"   : {"key": ["r", "o"         ], "kana": "しぇ", "del": 0},
		"sya"   : {"key": ["r", "h"         ], "kana": "しゃ", "del": 0},
		"syu"   : {"key": ["r", "p"         ], "kana": "しゅ", "del": 0},
		"syo"   : {"key": ["r", "i"         ], "kana": "しょ", "del": 0},
		"zye"   : {"key": ["r", "j", "o"    ], "kana": "じぇ", "del": 0},
		"zya"   : {"key": ["r", "h", "j"    ], "kana": "じゃ", "del": 0},
		"zyu"   : {"key": ["r", "j", "p"    ], "kana": "じゅ", "del": 0},
		"zyo"   : {"key": ["r", "j", "i"    ], "kana": "じょ", "del": 0},
		"kya"   : {"key": ["w", "h"         ], "kana": "きゃ", "del": 0},
		"kyu"   : {"key": ["w", "p"         ], "kana": "きゅ", "del": 0},
		"kyo"   : {"key": ["w", "i"         ], "kana": "きょ", "del": 0},
		"gya"   : {"key": ["w", "h", "j"    ], "kana": "ぎゃ", "del": 0},
		"gyu"   : {"key": ["w", "j", "p"    ], "kana": "ぎゅ", "del": 0},
		"gyo"   : {"key": ["w", "j", "i"    ], "kana": "ぎょ", "del": 0},
		"tye"   : {"key": ["g", "o"         ], "kana": "ちぇ", "del": 0},
		"tya"   : {"key": ["g", "h"         ], "kana": "ちゃ", "del": 0},
		"tyu"   : {"key": ["g", "p"         ], "kana": "ちゅ", "del": 0},
		"tyo"   : {"key": ["g", "i"         ], "kana": "ちょ", "del": 0},
		"dye"   : {"key": ["g", "j", "o"    ], "kana": "ぢぇ", "del": 0},
		"dya"   : {"key": ["g", "h", "j"    ], "kana": "ぢゃ", "del": 0},
		"dyu"   : {"key": ["g", "j", "p"    ], "kana": "ぢゅ", "del": 0},
		"dyo"   : {"key": ["g", "j", "i"    ], "kana": "ぢょ", "del": 0},
		"nya"   : {"key": ["d", "h"         ], "kana": "にゃ", "del": 0},
		"nyu"   : {"key": ["d", "p"         ], "kana": "にゅ", "del": 0},
		"nyo"   : {"key": ["d", "i"         ], "kana": "にょ", "del": 0},
		"hya"   : {"key": ["s", "h"         ], "kana": "ひゃ", "del": 0},
		"hyu"   : {"key": ["s", "p"         ], "kana": "ひゅ", "del": 0},
		"hyo"   : {"key": ["s", "i"         ], "kana": "ひょ", "del": 0},
		"bya"   : {"key": ["s", "h", "j"    ], "kana": "びゃ", "del": 0},
		"byu"   : {"key": ["s", "j", "p"    ], "kana": "びゅ", "del": 0},
		"byo"   : {"key": ["s", "j", "i"    ], "kana": "びょ", "del": 0},
		"pya"   : {"key": ["s", "h", "m"    ], "kana": "ぴゃ", "del": 0},
		"pyu"   : {"key": ["s", "m", "p"    ], "kana": "ぴゅ", "del": 0},
		"pyo"   : {"key": ["s", "m", "i"    ], "kana": "ぴょ", "del": 0},
		"mya"   : {"key": ["b", "h"         ], "kana": "みゃ", "del": 0},
		"myu"   : {"key": ["b", "p"         ], "kana": "みゅ", "del": 0},
		"myo"   : {"key": ["b", "i"         ], "kana": "みょ", "del": 0},
		"rya"   : {"key": ["e", "h"         ], "kana": "りゃ", "del": 0},
		"ryu"   : {"key": ["e", "p"         ], "kana": "りゅ", "del": 0},
		"ryo"   : {"key": ["e", "i"         ], "kana": "りょ", "del": 0},

			// 清音外来音 濁音外来音
		"thi"   : {"key": ["e", "m", "k"    ], "kana": "てぃ", "del": 0},
		"thu"   : {"key": ["e", "m", "p"    ], "kana": "てゅ", "del": 0},
		"dhi"   : {"key": ["e", "j", "k"    ], "kana": "でぃ", "del": 0},
		"dhu"   : {"key": ["e", "j", "p"    ], "kana": "でゅ", "del": 1},
		"toxu"  : {"key": ["d", "m", "l"    ], "kana": "とぅ", "del": 1},
		"doxu"  : {"key": ["d", "j", "l"    ], "kana": "どぅ", "del": 1},
		"sye"   : {"key": ["r", "m", "o"    ], "kana": "しぇ", "del": 1},
		"tye"   : {"key": ["g", "m", "o"    ], "kana": "ちぇ", "del": 1},
		"zye"   : {"key": ["r", "j", "o"    ], "kana": "じぇ", "del": 1},
		"dye"   : {"key": ["g", "j", "o"    ], "kana": "ぢぇ", "del": 1},
		"fa"    : {"key": ["v", "j", "."    ], "kana": "ふぁ", "del": 0},
		"fi"    : {"key": ["v", "k", "."    ], "kana": "ふぃ", "del": 0},
		"fe"    : {"key": ["v", "o", "."    ], "kana": "ふぇ", "del": 0},
		"fo"    : {"key": ["v", "n", "."    ], "kana": "ふぉ", "del": 0},
		"fyu"   : {"key": ["v", ".", "p"    ], "kana": "ふゅ", "del": 0},
		"wi"    : {"key": ["v", "k", "l"    ], "kana": "うぃ", "del": 0},
		"we"    : {"key": ["v", "o", "l"    ], "kana": "うぇ", "del": 0},
		"uxo"   : {"key": ["v", "n", "l"    ], "kana": "うぉ", "del": 1},
		"va"    : {"key": ["f", "j", "l"    ], "kana": "ゔぁ", "del": 0},
		"vi"    : {"key": ["f", "k", "l"    ], "kana": "ゔぃ", "del": 0},
		"ve"    : {"key": ["f", "o", "l"    ], "kana": "ゔぇ", "del": 0},
		"vo"    : {"key": ["f", "n", "l"    ], "kana": "ゔぉ", "del": 0},
		"vuxyu" : {"key": ["f", "l", "p"    ], "kana": "ゔゅ", "del": 1},
		"kuxa"  : {"key": ["v", "h", "j"    ], "kana": "くぁ", "del": 1},
		"kuxi"  : {"key": ["v", "h", "k"    ], "kana": "くぃ", "del": 1},
		"kuxe"  : {"key": ["v", "h", "o"    ], "kana": "くぇ", "del": 1},
		"kuxo"  : {"key": ["v", "h", "n"    ], "kana": "くぉ", "del": 1},
		"kuxwa" : {"key": ["v", "h", "l"    ], "kana": "くゎ", "del": 1},
		"guxa"  : {"key": ["f", "h", "j"    ], "kana": "ぐぁ", "del": 1},
		"guxi"  : {"key": ["f", "h", "k"    ], "kana": "ぐぃ", "del": 1},
		"guxe"  : {"key": ["f", "h", "o"    ], "kana": "ぐぇ", "del": 1},
		"guxo"  : {"key": ["f", "h", "n"    ], "kana": "ぐぉ", "del": 1},
		"guxwa" : {"key": ["f", "h", "l"    ], "kana": "ぐゎ", "del": 1},
		"tsa"  : {"key": ["v", "j", ";"    ], "kana": "つぁ", "del": 1},
		"tsi"  : {"key": ["v", "k", ";"    ], "kana": "つぃ", "del": 1},
		"tse"  : {"key": ["v", "o", ";"    ], "kana": "つぇ", "del": 1},
		"tso"  : {"key": ["v", "n", ";"    ], "kana": "つぉ", "del": 1},

			// 小書き
		"xya"   : {"key": ["q", "h"         ], "kana": "ゃ", "del": 0},
		"xyu"   : {"key": ["q", "p"         ], "kana": "ゅ", "del": 0},
		"xyo"   : {"key": ["q", "i"         ], "kana": "ょ", "del": 0},
		"xa"    : {"key": ["q", "j"         ], "kana": "ぁ", "del": 0},
		"xi"    : {"key": ["q", "k"         ], "kana": "ぃ", "del": 0},
		"xu"    : {"key": ["q", "l"         ], "kana": "ぅ", "del": 0},
		"xe"    : {"key": ["q", "o"         ], "kana": "ぇ", "del": 0},
		"xo"    : {"key": ["q", "n"         ], "kana": "ぉ", "del": 0},
		"xwa"   : {"key": ["q", "l"         ], "kana": "ゎ", "del": 0},
		"xtu"   : {"key": ["g"              ], "kana": "っ", "del": 0},

		"."     : {"key": ["[s]", "m"       ], "kana": "。", "del": 0},
		","     : {"key": ["[s]", "v"       ], "kana": "、", "del": 0},
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
					kanatext = kanatext.slice(0, kanatext.length - naginata[n].del);
					kanatext.push([naginata[n].kana, naginata[n].key]);
					for (var k of naginata[n].key) {
						highlight.push(k);
					}
					buffer = [];
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

		if (kc == "Backspace") {
			buffer = [];
			lbuffer = [];
			highlight = [];
			highlight.push("u");
			kanatext.push(["←", ["U"]]);
		}
		if (kc == "Enter") {
			if (lbuffer[lbuffer.length-1] != ".") {
				highlight = [];
				highlight.push("v");
				highlight.push("m");
				kanatext.push(["⤶", ["V", "M"]]);
			}
			buffer = [];
			lbuffer = [];
		}
		if (kc == " ") {
			buffer = [];
			lbuffer = [];
			highlight = [];
			highlight.push("[s]");
			kanatext.push(["□", ["[S]"]]);
		}

		if (!seachKey(lbuffer, 5)) {
			if (!seachKey(lbuffer, 4)) {
				if (!seachKey(lbuffer, 3)) {
					for (var n in naginata) {
						if (n == buffer.join("")) {
							highlight = [];
							kanatext.push([naginata[n].kana, naginata[n].key]);
							for (var k of naginata[n].key) {
								highlight.push(k);
							}
							buffer = [];
							break;
						}
					}
				}
			}
		}
		

		buffer = buffer.slice(-4);
		lbuffer = lbuffer.slice(-10);

		kanatext = kanatext.slice(-16);

	}
</script>

<main>
	<h1>薙刀式を可視化する</h1>
	<textarea bind:value={text} on:keyup={handleType}></textarea>
	<p class="stream" >
		{#each kanatext as [kana, keys]}
			<div class='tate'>
				<div class="kana">{kana}</div>
				{#each keys as k}
					<div class='key'>{k.toUpperCase()}</div>
				{/each}
			</div>
		{/each}
	</p>
	
	<Keyboard highlight={highlight} />

	<div class="note">
		<ul>
			<li>Windowsの新しいIMEでは日本語入力中にキー入力をブラウザが取得できないため、以前のバージョンのMicrosoft IMEを使う、にオプションを設定しないと動作しません。</li>
			<li>ブラウザの種類、OSによっては正常に動作しません。Linux+Mozc+Firefox、MacOS+Firefox、Windows+以前のIME+Firefoxなどで動作を確認済みです。</li>
		</ul>
	</div>

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

	.stream {
		font-size: 25px;
		display: flex;
		align-items: baseline;
	}

	.kana {
		height: 40px;
	}

	.tate {
		flex-direction: column;
		align-items: center;
	}

	.key {
		font-size: 15px;
		border:1px solid #bebebe;
    	border-radius:4px;
    	text-align: center;
    	width: 25px;
    	height: 25px;
    	margin: 2px;
	}

	.note {
		width: 70%;
		padding: 5px;
		margin: 30px;
		font-size: 8pt;
		background-color: rgb(241, 241, 241);
	}

	@media (min-width: 640px) {
		main {
			max-width: 800px;
		}
	}
</style>