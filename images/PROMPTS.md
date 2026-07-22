# 画像生成プロンプト（gpt-image 用）

## 全画像共通の指定（各プロンプトの末尾に必ず付ける）

```
Style: quiet luxury, muted and desaturated. Palette limited to warm greige (#EDE6DD),
soft ivory, pale taupe, and a restrained champagne gold (#C4A57B). Absolutely no black —
the darkest tone is a warm dark brown (#5A5148). No high-saturation colors.
Soft natural window light, gentle diffused shadows, low contrast, film-like grain.
No text, no lettering, no logos, no watermarks anywhere in the image.
Photorealistic editorial photography, not illustration.
```

**文字禁止は必須。** FVで一度つまずいた通り、焼き込まれた文字はレスポンシブで破綻して修正不能になる。

## サイズについて

LP側は `object-fit:cover` + `aspect-ratio` 指定なので、多少の比率ズレは自動でトリミングされる。
gpt-image の出力サイズ → 保存サイズの対応：

| ファイル | LP上の比率 | 生成サイズ | 保存時 |
|---|---|---|---|
| reason-01〜03 | 4:3 | 1536×1024 | 800×600 に縮小（左右わずかにトリム） |
| gallery-01〜08 | 1:1 | 1024×1024 | 600×600 に縮小 |
| cta-bg | 16:9 | 1536×1024 | 1920×1080 に拡大（背景なので劣化は目立たない） |

---

## reason-01.jpg — 少人数レッスン風景

```
A small nail art lesson in a bright home studio. Three Japanese women in their 30s to 50s
seated around a pale wooden table, one instructor leaning in to guide another's hand.
Shot slightly from behind and to the side so faces are soft-focus or turned away.
Linen aprons in oatmeal tones, dried flowers in a ceramic vase on the table.
Calm, unhurried, intimate — the feeling of being taught properly, not processed in bulk.
```

## reason-02.jpg — ネイル施術の手元アップ

```
Extreme close-up of a nail technician's hands applying a sheer beige gel polish to a
client's fingernail, brush mid-stroke. Shallow depth of field, the brush tip in sharp focus.
Both hands well-formed with exactly five fingers each, natural skin texture.
Pale wooden table surface, a folded ivory towel beneath the hand.
```

> **手の描写は要検品。** 生成AIは指の本数と関節を高確率で誤る。等倍で指を数えてから採用すること。

## reason-03.jpg — ノートとタブレットで学ぶ様子

```
A woman's hands writing in a linen-bound notebook beside a tablet displaying a soft,
out-of-focus interface. Warm desk lamp light from the left. A cup of tea, a few dried
eucalyptus stems. Overhead flat-lay angle, slightly tilted. Studious and quiet —
evening study after the children are asleep.
```

## cta-bg.jpg — CTA背景

```
Soft pale marble surface in warm ivory with faint greige veining, photographed from above.
Dried flowers — pampas grass, preserved roses in muted dusty tones — arranged loosely
along one edge, leaving the center largely empty and uncluttered.
Very low contrast, hazy soft light. This is a background image: the center must stay
calm and near-empty so overlaid text remains readable.
```

---

## gallery-01〜08.jpg — 作品ギャラリー

**⚠️ AI生成での作成は推奨しない。理由は下記「ギャラリーの扱い」を参照。**

実写を使う前提で、撮影時の仕様だけ記しておく：

- 正方形・被写体は手元のみ・背景は無地のアイボリーかペールウッド
- 自然光（直射日光は避ける）、影は柔らかく
- 彩度を上げない。SNS的な加工・白飛びさせる補正はしない
- 8点の想定デザイン（HTMLのalt属性と対応）：
  1. ベージュのワンカラー
  2. くすみピンクのグラデーション
  3. マットな質感のニュアンス
  4. ゴールドラインをあしらったデザイン
  5. グレージュのシンプル
  6. クリアベースのフレンチ
  7. パールを添えたブライダル
  8. 深いボルドーのワンカラー
