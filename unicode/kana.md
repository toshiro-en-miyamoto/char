# Japanese Kana in Unicode

The Unicode defines three major areas for Japanese Hiragana and Katakana:

| Kana                  | Unicode code point
|-----------------------|------------
| [Hiragana](http://www.unicode.org/charts/PDF/U3040.pdf)           | 3040 - 309F
| [Katakana](http://www.unicode.org/charts/PDF/U30A0.pdf)           | 30A0 - 30FF
| [Halfwidth Katakana](http://www.unicode.org/charts/PDF/UFF00.pdf) | FF5F - FF9F

The code point tables are available at [`unicode.org`](http://www.unicode.org/charts/).

## Voiced Katakana

When you render Katakana characters,
- prefer code points in the range from U-30A0 to U-30FF by default;
- when you have no choice but to render Halfwidth Katakana characters, use code points in the range from U-FF61 to U-FF9F;
- alternatively, you might have Katakana characters followed by *Combining voiced sound mark* (U-3099) or *Combining semi-voiced sound mark* (U-309A).


| Letter | Prefer | *p | Halfwidth Katakana | *h | avoid sound marks | *a
|----|-------:|----|--------------:|----|----------------:|----
| GA | 30AC   | ガ | FF76 (ｶ), FF9E | ｶﾞ | 30AB (カ), 3099 | ガ
| GI | 30AE   | ギ | FF77 (ｷ), FF9E | ｷﾞ | 30AD (キ), 3099 | ギ
| GU | 30B0   | グ | FF78 (ｸ), FF9E | ｸﾞ | 30AF (ク), 3099 | グ
| GE | 30B2   | ゲ | FF79 (ｹ), FF9E | ｹﾞ | 30B1 (ケ), 3099 | ゲ
| GO | 30B4   | ゴ | FF7A (ｺ), FF9E | ｺﾞ | 30B3 (コ), 3099 | ゴ
| ZA | 30B6   | ザ | FF7B (ｻ), FF9E | ｻﾞ | 30B5 (サ), 3099 | ザ
| ZI | 30B8   | ジ | FF7C (ｼ), FF9E | ｼﾞ | 30B7 (シ), 3099 | ジ
| ZU | 30BA   | ズ | FF7D (ｽ), FF9E | ｽﾞ | 30B9 (ス), 3099 | ズ
| ZE | 30BC   | ゼ | FF7E (ｾ), FF9E | ｾﾞ | 30BB (セ), 3099 | ゼ
| ZO | 30BE   | ゾ | FF7F (ｿ), FF9E | ｿﾞ | 30BD (ソ), 3099 | ゾ
| DA | 30C0   | ダ | FF80 (ﾀ), FF9E | ﾀﾞ | 30BF (タ), 3099 | ダ
| DI | 30C2   | ヂ | FF81 (ﾁ), FF9E | ﾁﾞ | 30C1 (チ), 3099 | ヂ
| DU | 30C5   | ヅ | FF82 (ﾂ), FF9E | ﾂﾞ | 30C4 (ツ), 3099 | ヅ
| DE | 30C7   | デ | FF83 (ﾃ), FF9E | ﾃﾞ | 30C6 (テ), 3099 | デ
| DO | 30C9   | ド | FF84 (ﾄ), FF9E | ﾄﾞ | 30C8 (ト), 3099 | ド
| BA | 30D0   | バ | FF8A (ﾊ), FF9E | ﾊﾞ | 30CF (ハ), 3099 | バ
| BI | 30D3   | ビ | FF8B (ﾋ), FF9E | ﾋﾞ | 30D2 (ヒ), 3099 | ビ
| BU | 30D6   | ブ | FF8C (ﾌ), FF9E | ﾌﾞ | 30D5 (フ), 3099 | ブ
| BE | 30D9   | ベ | FF8D (ﾍ), FF9E | ﾍﾞ | 30D8 (ヘ), 3099 | ベ
| BO | 30DC   | ボ | FF8E (ﾎ), FF9E | ﾎﾞ | 30DB (ホ), 3099 | ボ
| PA | 30D1   | パ | FF8A (ﾊ), FF9F | ﾊﾟ | 30CF (ハ), 309A | パ
| PI | 30D4   | ピ | FF8B (ﾋ), FF9F | ﾋﾟ | 30D2 (ヒ), 309A | ピ
| PU | 30D7   | プ | FF8C (ﾌ), FF9F | ﾌﾟ | 30D5 (フ), 309A | プ
| PE | 30DA   | ペ | FF8D (ﾍ), FF9F | ﾍﾟ | 30D8 (ヘ), 309A | ペ
| PO | 30DD   | ポ | FF8E (ﾎ), FF9F | ﾎﾟ | 30DB (ホ), 309A | ポ

## Voicing marks

Japanese language has two kinds of *voicing mark*:

<table>
<tr>
<th>sound mark<th>ja
<tr>
<td>Voiced sound mark:<td>゛<ruby>濁点<rt>だくてん</rt></ruby>
<tr>
<td>Semi-voiced sound mark:<td>゜<ruby>半濁点<rt>はんだくてん</rt></ruby>
</table>

Unicode defines six vocing marks for Japanese:

| Voicing mark                              | Code point | Ch
|-------------------------------------------|-------|----
| Combining voiced sound mark               | 3099  |
| Combining semi-voiced sound mark          | 309A  |
| Voiced sound mark                         | 309B  | ゛
| Semi-voiced sound mark                    | 309C  | ゜
| Halfwidth Katakana voiced sound mark      | FF9E  | ﾞ
| Halfwidth Katakana semi-voiced sound mark | FF9F  | ﾟ

Combining marks (U-3099 and U-309A) are so called because they are not allowed to stand alone, rather a character may be followd by a combining sound mark so as to transform its voice.

Other four voicing marks (U-309B, U-309C, U-FF9E, and U-FF9F) are allowed to stand alone: they are defined to visualize the marks as distinct characters.

The table below shows how Katakana BA and PA can be represented:

| Building block                                | Code point        | Ch | Letter
|-----------------------------------------------|-------------------|----|-------
| Katakana BA                                   | 30D0              | バ | BA
| Katakana PA                                   | 30D1              | パ | PA
| Katakana HA, Combining voiced sound mark      | 30CF (ハ), 3099   | バ | BA
| Katakana HA, Combining semi-voiced sound mark | 30CF (ハ), 309A   | パ | PA

As the above table shows, you can represent a Katakana BA in two ways:

-   with one code point, U-30D0 バ
-   with two code points, U-30CF ハ followed by U-3099 ゛Combining voiced sound mark

In fact, you can erase U-30D0 バ by one click of the Back Space key; on the other hand, only one click of the BS key for バ that is made up of U-30CF ハ and U-3099 ゛just ends up changing the バ to U-30CF ハ.

The table below show that the Voiced sound mark U-309B looks as similar as the Combining voiced sound mark U-3099.

| Building block                            | Code point        | Ch | Letter
|-------------------------------------------|-------------------|----|-------
| Katakana HA, Combining voiced sound mark  | 30CF (ハ), 3099   | バ | BA
| Katakana HA, Voiced sound mark            | 30CF (ハ), 309B   | ハ゛| BA

バ (U-30CF, U-3099) and ハ゛ (U-30CF, U-309B) look almost the same but they are totally distinct entities in that:

-   バ (U-30CF, U-3099) is regarded as a combined single entity, thus e.g., you cannot place the cursor between the two code points;
-   ハ゛ (U-30CF, U-309B) are regarded as two consecutive code points, thus e.g., you can place cursor between them and any characters can be put in between, such as ハ=゛ (U-30CF ハ, followed by an equal sign, followed by U-309B Voiced sound mark).

The table below shows how Halfwidth Katakana BA and PA can be represented:

| Building block                                | Code point        | Ch | Letter
|-----------------------------------------------|-------------------|----|--------
| Halfwidth Katakana HA, voiced sound mark      | FF8A (ﾊ), FF9E    | ﾊﾞ | BA
| Halfwidth Katakana HA, semi-voiced sound mark | FF8A (ﾊ), FF9F    | ﾊﾟ | PA

Notice that neither voiced Halfwidth Katakana nor semi-voiced can be represented by single code points. Combining a Halfwidth Katakana character with the Halfwidth Katakana voiced sound mark U-FF9E (or semi-voiced U-FF9F) is the only way to render a voiced (or semi-voiced) Halfwidth Katakana character.

Halfwidth Katakana sound marks U-FF9E (voiced) and U-FF9F (semi-voiced) have the same function as Combining sound marks U-3099 (voiced) and U-309A (semi-voiced) in that:

-   the Halfwidth Katakana sound mark U-FF9E (or U-FF9F) and the preceding Halfwidth Katakana character is regarded as a combined single entity, thus e.g., you cannot place the cursor between the two code points;

On the other hand, Halfwidth Katakana sound marks U-FF9E (voiced) and U-FF9F (semi-voiced) can stand alone just like U-309B (voiced) and U-309C (semi-voiced).
