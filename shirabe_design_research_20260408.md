━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
【しらべ リサーチレポート】AIっぽくないLPデザイン事例調査 / 2026-04-08
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

調査目的：FUKUOKA CONNECTのLP制作における「テンプレ感」脱却のための
デザインリソース・テクニック・書体の網羅的調査

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## 1. LPギャラリー・まとめサイト一覧
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

### Tier 1：毎日チェックすべきサイト

| サイト名 | URL | 特徴 | 業種フィルタ |
|---------|-----|------|------------|
| SANKOU! | https://sankoudesign.com/ | 4,000件超。更新頻度が高い。カテゴリ別で探しやすい | カフェ・飲食、美容室・サロン、タイポグラフィ等 |
| MUUUUU.ORG | https://muuuuu.org/ | 厳選されたハイクオリティ事例。「特殊Webフォント使用」等のユニークな検索軸 | 飲食店・グルメ等 |
| LP ARCHIVE | https://rdlp.jp/lp-archive/ | 43,000件超。「かわいい」「和風」「高級」等のイメージ検索が可能 | 業種・カラー・イメージ |

### Tier 2：テーマ別に参照

| サイト名 | URL | 特徴 |
|---------|-----|------|
| Web Design Clip | https://webdesignclip.com/ | 5,000件超。国内外のLP。スマホ特化も |
| LP advance | https://site-advance.info/ | LP特化型ギャラリー |
| LP幹事 | https://lp-kanji.com/ | 2,500件超。AND検索で絞り込み |

### 業種別カテゴリ直リンク（ブックマーク推奨）

- カフェ・飲食店：https://sankoudesign.com/category/cafe-restaurant-tavern/
- 美容室・サロン：https://sankoudesign.com/category/salon/
- タイポグラフィ重視：https://sankoudesign.com/category/typography/
- 飲食（MUUUUU）：https://muuuuu.org/category/industry/restaurant
- 治療院HP参考：https://mihoncho.com/sinkyu-seikotsu/ （124サイト厳選）


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## 2. 「AIっぽくない」デザインの共通点分析
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

### 2-1. レイアウトの崩し方・ずらし方

AIが生成するLPは「グリッドに忠実」で「左右対称」が基本。
人間のデザイナーは以下を意図的に行う：

【ブロークングリッドレイアウト】
- 基本のグリッドを「意識しつつ」部分的に崩す（完全無視ではない）
- 写真を意図的にグリッドからはみ出させる
- テキストブロックを画像に重ねて配置する
- 隣接する要素を「少しだけ」ずらして配置する（20〜50px程度）

参考：https://mtame.jp/design/Broken_Grid_Layout/

【実装のコツ】
- CSS Gridで基本を組み、特定要素だけ `grid-column: 1 / -1` ではみ出させる
- `position: relative` + `top/left` の微調整で「手作り感」を出す
- `margin-left: -5vw` のようなネガティブマージンで写真をはみ出させる


### 2-2. フォント選びのセンス

FUKUOKA CONNECTの現状：Noto Sans JP + Shippori Mincho の2種類固定
→ 問題：どの案件も同じ「顔」になる

優れたサイトの共通点：
- 見出し用と本文用で書体のコントラストを明確にする
- 英字と日本語で別フォントを組み合わせる
- 装飾書体は「見出し・キャッチ限定」で使い、本文は可読性重視

具体例（実際のサイトから確認）：
- 珈琲 占野：英字 Assistant + PP Neue Montreal、日本語は別フォント
- 高級飲食店：明朝ベースに英字セリフを合わせて格調を出す
- カジュアル店：丸ゴシック + 手書き風のアクセント


### 2-3. 文字組の工夫

【ジャンプ率（サイズ対比）】
AIが作ると見出し:本文 = 1.5〜2倍程度で「おとなしい」
人間のデザイナーは：
- キャッチコピー：80〜120px
- サブコピー：16〜20px
- → ジャンプ率4〜6倍で視覚的なドラマを作る

【配置の遊び】
- 横書きの中に縦書きを混ぜる（CSSの `writing-mode: vertical-rl`）
- テキストを斜めに配置する（`transform: rotate(-3deg)`）
- 文字の一部だけ色やサイズを変える（`<span>`で個別制御）
- 行間を極端に詰める/広げるセクションを作る

【字間の印象操作】
- 字間広め（0.1〜0.2em）：穏やか・上品・余裕
- 字間狭め（0〜-0.02em）：力強い・堅実・緊張感


### 2-4. セクション構成の独自性

AIのテンプレ構成：
NAV → HERO → 特徴 → メニュー → 口コミ → アクセス → CTA

人間が作る構成のバリエーション：
- 「ストーリーテリング型」：オーナーの想い → 素材のこだわり → 提供の瞬間 → 体験の声
- 「ビジュアルファースト型」：全画面写真 → 最小テキスト → 写真 → テキスト の交互
- 「雑誌型」：見出し + 大型写真 + コラム風テキストを不規則に配置
- 「一問一答型」：Q&A形式でスクロールごとに1つの問いに答える


### 2-5. 余白・間の使い方

AIが作るLP：
- 全セクション均等な padding（80px〜120px）
- 要素間も均等

人間のデザイナーの余白：
- セクション間に「呼吸」を入れる（200〜300pxの大きな余白）
- 関連性の高い要素は近接させ、異なるグループは大きく離す
- 「何もない空間」を恐れない（余白 = 高級感・信頼感）
- 基本単位を8pxにして、8/16/24/32/48/64/96/128... と規則的に使い分け

参考：https://giginc.co.jp/blog/giglab/yohaku-design


### 2-6. 写真とテキストの関係性

AI的アプローチ：写真の上にオーバーレイ → テキスト配置（全部同じ）

人間的アプローチ：
- 写真の「余白部分」にテキストを配置（写真の構図を活かす）
- テキストが写真にかかる部分は `text-shadow` や背景ぼかしで可読性確保
- 写真をマスク（丸、斜め、blob形状）で切り抜いてレイアウトに変化
- 写真の上に大きな文字を「あえて重ねる」（雑誌的手法）


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## 3. Google Fonts 日本語書体カタログ
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

現在Google Fontsには64の日本語書体（132ウェイト）が登録されている。
以下、FUKUOKA CONNECTの案件ジャンル別に推奨書体を整理する。

### 3-1. カフェ・ベーカリー・スイーツ向け（柔らかく親しみやすい）

| フォント名 | カテゴリ | 特徴 | おすすめ用途 |
|-----------|---------|------|------------|
| Zen Maru Gothic | 丸ゴシック | 角の丸みが深く、自然で柔らかい印象 | 見出し・本文両方OK |
| Kiwi Maru | 丸ゴシック | 手書きのようなかわいらしさ | 見出し・サブコピー |
| M PLUS Rounded 1c | 丸ゴシック | 親しみやすい丸み | エンタメ・カジュアル店 |
| Kosugi Maru | 丸ゴシック | すっきりした曲線。小サイズでも読みやすい | 本文・補足テキスト |
| Yomogi | 手書き風 | 細ペンでかわいらしい。縦書き対応 | アクセント・メニュー名 |

### 3-2. 美容室・サロン・エステ向け（上品でエレガント）

| フォント名 | カテゴリ | 特徴 | おすすめ用途 |
|-----------|---------|------|------------|
| Shippori Mincho | 明朝体 | エッジが丸く上品。現在も使用中 | 見出し・キャッチ |
| Zen Old Mincho | 明朝体 | レトロ風で毛筆のような柔らかさ | 和テイストの見出し |
| Hina Mincho | 明朝体 | 細めの漢字に丸み。伝統的で上品 | 高級サロン向け見出し |
| Kaisei Decol | デザイン書体 | 明朝風+丸い装飾。エレガント | ロゴ的キャッチ |
| Zen Kurenaido | 手書き風 | ボールペン風で可読性が高い | サブコピー・キャプション |
| Klee One | 手書き風 | 鉛筆・ペン風。教科書体に近い | 本文・説明文 |

### 3-3. 整骨院・整体・治療院向け（力強く信頼感）

| フォント名 | カテゴリ | 特徴 | おすすめ用途 |
|-----------|---------|------|------------|
| Dela Gothic One | 極太ゴシック | 超極太で横長。圧倒的インパクト | キャッチコピー限定 |
| Zen Kaku Gothic New | ゴシック体 | ひらがなが小ぶりで落ち着いた印象 | 本文・見出し |
| BIZ UDPGothic | UDゴシック | ユニバーサルデザイン。医療系に最適 | 本文（信頼感） |
| Noto Serif JP | 明朝体 | 高級感・信頼感の王道 | 見出し |
| Sawarabi Gothic | ゴシック体 | 小サイズでもつぶれにくい | 本文・補足 |

### 3-4. 個性的・アクセント用（見出し・キャッチ限定）

| フォント名 | カテゴリ | 特徴 | 注意点 |
|-----------|---------|------|--------|
| Yusei Magic | 手書き（マジック） | 油性マジック風。インパクト大 | 本文使用は避ける |
| Hachi Maru Pop | ポップ | 丸文字。親しみやすさ | カジュアル限定 |
| Mochiy Pop One | ポップ | 女の子の手書きトレース | ターゲットを選ぶ |
| Rampart One | 装飾（立体） | 3D風の輪郭影付き | タイトル限定 |
| Aoboshi One | セリフ装飾 | かわいくレトロ | アクセント的使用 |
| Kaisei Opti | デザイン書体 | モダン+ポップなドット装飾 | 見出し |

### 3-5. 推奨フォントペアリング（案件タイプ別）

【カフェ・ベーカリー】
- 見出し：Zen Maru Gothic (700) + 英字：Google Fonts の Josefin Sans
- 本文：Zen Maru Gothic (400)
- アクセント：Yomogi

【美容室・サロン】
- 見出し：Zen Old Mincho (700) + 英字：Cormorant Garamond
- 本文：Klee One (400)
- アクセント：Kaisei Decol

【整骨院・整体】
- 見出し：Dela Gothic One + 英字：Bebas Neue
- 本文：Zen Kaku Gothic New (400)
- キャッチ：Noto Serif JP (700)

【地域密着・多業種】
- 見出し：M PLUS 1p (700) + 英字：Poppins
- 本文：BIZ UDPGothic (400)
- アクセント：Kiwi Maru

参考リンク：
- Google Fonts日本語一覧：https://fonts.google.com/?subset=japanese
- Google Fonts日本語特設：https://googlefonts.github.io/japanese/
- SANKOU! font：https://sankoufont.com/service/googlefonts/
- 福岡サンゼンデザイン 24選解説：https://www.sanzen-design.jp/labo/p6914


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## 4. CSS/デザインテクニック集
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

### 4-1. 文字の重ね・はみ出し

```css
/* 大きな英字を背景テキストとして重ねる */
.section-bg-text {
  font-size: clamp(80px, 15vw, 200px);
  font-weight: 900;
  color: rgba(0, 0, 0, 0.03);
  position: absolute;
  top: -20px;
  left: -10px;
  z-index: 0;
  letter-spacing: 0.05em;
  white-space: nowrap;
  pointer-events: none;
}

/* 日本語キャッチを写真にかぶせる */
.hero-catch {
  position: relative;
  z-index: 2;
  margin-top: -80px; /* 写真に食い込ませる */
  font-size: clamp(32px, 5vw, 64px);
  font-weight: 700;
  mix-blend-mode: multiply; /* 写真と馴染ませる */
}
```

### 4-2. 非対称レイアウト

```css
/* 左右交互の非対称グリッド */
.content-block {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0;
}

.content-block:nth-child(odd) .image {
  grid-column: 1;
  margin-right: -5vw; /* 右にはみ出し */
}

.content-block:nth-child(odd) .text {
  grid-column: 2;
  padding: 60px 40px 60px 80px;
  align-self: center;
}

.content-block:nth-child(even) .image {
  grid-column: 2;
  margin-left: -5vw; /* 左にはみ出し */
}

.content-block:nth-child(even) .text {
  grid-column: 1;
  padding: 60px 80px 60px 40px;
  align-self: center;
}
```

### 4-3. スクロール連動パララックス（CSS Only）

```css
/* Scroll-Driven Animation（Chrome/Edge対応） */
@keyframes parallax-bg {
  from { background-position: center 0px; }
  to   { background-position: center -400px; }
}

.parallax-section {
  background-image: url('hero.jpg');
  background-size: cover;
  animation: parallax-bg linear;
  animation-timeline: scroll();
}

/* 要素のフェードイン + スライドアップ */
@keyframes fade-slide-up {
  from {
    opacity: 0;
    transform: translateY(40px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.scroll-reveal {
  animation: fade-slide-up linear;
  animation-timeline: view();
  animation-range: entry 0% entry 100%;
}

/* アクセシビリティ対応 */
@media (prefers-reduced-motion: reduce) {
  .parallax-section,
  .scroll-reveal {
    animation: none !important;
  }
}
```

参考：https://css-tricks.com/bringing-back-parallax-with-scroll-driven-css-animations/

### 4-4. 写真のトリミング・マスクの工夫

```css
/* Blob形状マスク（案件ごとに変数を変えてバリエーション） */
.blob-mask {
  clip-path: polygon(
    30% 0%, 70% 0%, 100% 30%, 100% 70%,
    70% 100%, 30% 100%, 0% 70%, 0% 30%
  );
}

/* 斜めカットマスク */
.diagonal-mask {
  clip-path: polygon(0 0, 100% 0, 100% 85%, 0 100%);
}

/* 円形マスク + ホバーで拡大 */
.circle-mask {
  clip-path: circle(45% at 50% 50%);
  transition: clip-path 0.6s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}
.circle-mask:hover {
  clip-path: circle(50% at 50% 50%);
}

/* SVGマスクで有機的な形状 */
.organic-mask {
  mask-image: url('mask-shape.svg');
  mask-size: cover;
  mask-repeat: no-repeat;
}
```

### 4-5. グリッドを意図的に崩す手法

```css
/* ベースグリッドを組みつつ、特定要素をはみ出させる */
.magazine-grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: 16px;
}

/* 標準要素は6列 */
.magazine-grid .item { grid-column: span 6; }

/* 特集写真は全幅+はみ出し */
.magazine-grid .feature-image {
  grid-column: 1 / -1;
  margin-left: -5vw;
  margin-right: -5vw;
  width: calc(100% + 10vw);
}

/* テキストを微妙にずらす */
.magazine-grid .offset-text {
  grid-column: 2 / 8;
  margin-top: -40px;
  position: relative;
  z-index: 2;
  background: white;
  padding: 32px;
}
```

### 4-6. 日本語縦書きの活用

```css
/* セクションタイトルを縦書きに */
.vertical-title {
  writing-mode: vertical-rl;
  text-orientation: mixed;
  font-size: 14px;
  letter-spacing: 0.3em;
  position: absolute;
  right: 20px;
  top: 50%;
  transform: translateY(-50%);
}

/* 和テイストの縦書きキャッチ */
.tategaki-catch {
  writing-mode: vertical-rl;
  font-family: 'Zen Old Mincho', serif;
  font-size: clamp(24px, 4vw, 48px);
  line-height: 2;
  letter-spacing: 0.2em;
}
```

### 4-7. 文字サイズのドラマチックな対比

```css
/* キャッチコピーの大小対比 */
.dramatic-catch {
  line-height: 1.1;
}
.dramatic-catch .large {
  font-size: clamp(48px, 10vw, 120px);
  font-weight: 900;
  display: block;
}
.dramatic-catch .small {
  font-size: clamp(14px, 2vw, 18px);
  font-weight: 400;
  letter-spacing: 0.2em;
  margin-top: 16px;
  display: block;
}

/* 数字を極端に大きくする */
.big-number {
  font-size: clamp(64px, 12vw, 160px);
  font-weight: 900;
  line-height: 0.9;
  color: var(--accent);
}
.big-number + .label {
  font-size: 14px;
  margin-top: 8px;
}
```


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## 5. 参考にすべき具体的サイト事例
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

### 飲食・カフェ系

| サイト名 | URL | 学ぶべきポイント |
|---------|-----|----------------|
| 珈琲 占野 | https://coffee-shimeno.com/ | GSAP+ScrollTriggerのパララックス、黒背景×大型写真の没入感、セクション間300pxの大胆余白 |
| シーベジスタンド | https://seavege-stand.com/ | イラスト×写真のMix、縦書きキャッチコピー、装飾SVGフレーム |
| Fujiya1935 | https://fujiya1935.com/ | 「季節と記憶の食卓」のストーリーテリング構成 |
| hosa | https://www.hosa.nagoya/ | 洗練されたミニマルデザイン |
| パレード伏見洋菓子店 | https://parade.kyoto/ | 洋菓子店らしい上品さと遊び心の両立 |
| 焼肉きんぐ | https://www.yakiniku-king.jp/ | 大衆×スタイリッシュの両立、QUOITWORKS制作 |

### 美容室・サロン系
- SANKOU! サロンカテゴリ：https://sankoudesign.com/category/salon/
  （ここから最新事例を定期チェック推奨）

### 整骨院・治療院系
- 治療院HP参考124サイト：https://mihoncho.com/sinkyu-seikotsu/


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## 6. 総合提言：FUKUOKA CONNECTのLP制作を「脱AI感」するための5つのアクション
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

### アクション1：フォントパレットの拡充
現在のNoto Sans JP + Shippori Minchoに加え、案件タイプ別のフォントペアリングを
上記3-5のとおり4パターン用意する。
→ 最低でも Zen Maru Gothic / Zen Old Mincho / Dela Gothic One / Klee One を導入

### アクション2：ジャンプ率を上げる
キャッチコピーのフォントサイズを現在の1.5〜2倍にし、
本文との対比（ジャンプ率）を4〜6倍に引き上げる。
→ `clamp(48px, 8vw, 96px)` レベルの見出しサイズを恐れない

### アクション3：セクション構成のバリエーション
テンプレ的な「NAV→HERO→STRIP→...」から脱却するため、
以下の3パターンをストックとして持つ：
- ストーリーテリング型（想い→素材→体験→声）
- ビジュアルファースト型（全画面写真交互）
- 雑誌型（不規則グリッド+コラム風テキスト）

### アクション4：「崩し」のCSSスニペット集を作る
上記4章のCSSコードを共通スニペットとしてプロジェクトに組み込み、
案件ごとに「どの崩しを使うか」を選べるようにする。
特に効果が高いもの：
- 背景テキスト重ね（4-1）
- 非対称グリッド（4-2）
- 写真のネガティブマージンはみ出し（4-5）
- 縦書きアクセント（4-6）

### アクション5：週1回のデザインインプット
SANKOU!とMUUUUU.ORGを週1回チェックし、
「これは使える」と思ったデザインのスクリーンショットと
「何が効いているか」のメモを蓄積する。


━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
## 7. ソース一覧
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

### ギャラリーサイト
- SANKOU!：https://sankoudesign.com/
- MUUUUU.ORG：https://muuuuu.org/
- LP ARCHIVE：https://rdlp.jp/lp-archive/
- LP advance：https://site-advance.info/
- Web Design Clip：https://webdesignclip.com/

### Google Fonts関連
- Google Fonts 日本語：https://fonts.google.com/?subset=japanese
- Google Fonts 日本語特設：https://googlefonts.github.io/japanese/
- SANKOU! font：https://sankoufont.com/service/googlefonts/
- サンゼンデザイン 24選：https://www.sanzen-design.jp/labo/p6914
- PhotoshopVIP 32選：https://photoshopvip.net/131206
- コリス フリーフォント817種：https://coliss.com/articles/freebies/japanese-free-fonts.html

### デザインテクニック
- ブロークングリッド解説：https://mtame.jp/design/Broken_Grid_Layout/
- CSS Scroll-Driven Animations：https://css-tricks.com/bringing-back-parallax-with-scroll-driven-css-animations/
- CSS Parallax Effects集：https://freefrontend.com/css-parallax/
- CSS Scroll Effects 50選：https://prismic.io/blog/css-scroll-effects
- GIG 余白デザイン術：https://giginc.co.jp/blog/giglab/yohaku-design

### タイポグラフィ
- BRISK タイポグラフィ基礎：https://b-risk.jp/blog/2023/05/typography/
- SANKOU! タイポグラフィ事例：https://sankoudesign.com/category/typography/
- Adobe タイポグラフィ基礎：https://www.adobe.com/jp/creativecloud/roc/blog/design/typography.html

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
しらべ（SHIRABE） 調査完了
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
