# Component Gallery

Copy-paste markup for every Superheat block. Deck components work inside a
`<section class="slide dark|light|orange">`; whitepaper components work inside a
`<section class="page">`. Colors and fonts come from the design system — don't add
inline styles beyond the height % on bar fills.

> Legend: 🖥️ deck · 📄 whitepaper · 🔁 both

---

## 🔁 Inline accent

Wrap the one word/phrase that matters. This is *the* brand move.

```html
<h1>Same Machine. <span class="a">Better Asset.</span></h1>
<p class="lede">…still a working water heater with <span class="hl">standalone value</span>.</p>
```

---

## 🖥️ Cover / close slide

```html
<section class="slide orange cover">
  <div>
    <div class="top">Superheat<sup>™</sup></div>
    <div class="px-tag">&gt; THE HEATER THAT PAYS YOU BACK_</div>
  </div>
  <div class="bottom">
    <div class="big">From Thermal Hardware<br>to Financial Infrastructure</div>
    <div class="sub">Network strategy · live unit economics · the debt machine</div>
  </div>
</section>
```

---

## 🔁 Kicker + two-part headline

```html
<div class="kicker">The Thesis</div>
<h1>The Product Isn't the Heater.<br><span class="a">It Isn't Even the Compute.</span></h1>
```

---

## 🔁 Stat row

Numbers are DM Mono + orange. Use `<small>` for units. Column count: `c2` / `c3` / `c4`.

```html
<div class="stats c4">
  <div class="stat"><div class="n">1,000+</div><div class="t">Units deployed</div><div class="d">Real homes &amp; commercial installs across North America</div></div>
  <div class="stat"><div class="n">$550K+</div><div class="t">Passive income</div><div class="d">Validated real-world fleet revenue to date</div></div>
  <div class="stat"><div class="n">~1.0</div><div class="t">Effective PUE</div><div class="d">Cooling cost: zero. Heat is the product.</div></div>
  <div class="stat"><div class="n">−78<small>%</small></div><div class="t">4090 rentals since '24</div><div class="d">$1.84 → $0.40/hr on the marketplace floor</div></div>
</div>
```

---

## 🔁 Table

`td.num` = right-feeling DM Mono figure · `td.hl` = orange key cell · `<b>` in a `td` = the row label.

**Deck** (wrap in `.tbl-wrap` for the rounded card + scroll):

```html
<div class="tbl-wrap">
  <table>
    <tr><th>GPU</th><th>VRAM</th><th>Median $/hr</th><th>Range</th><th>Supply</th></tr>
    <tr><td><b>RTX 4090</b></td><td class="num">24 GB</td><td class="num hl">$0.40</td><td class="num">0.13 – 12.00</td><td>High</td></tr>
    <tr><td>RTX 3090</td><td class="num">24 GB</td><td class="num hl">$0.16</td><td class="num">0.08 – 1.33</td><td>High</td></tr>
  </table>
</div>
<p class="tbl-note">The v3.5 deck assumed $0.49/hr flat. The market says <b>$0.40 — and falling.</b></p>
```

**Whitepaper** (no wrapper; `.tbl-cap` for the caption):

```html
<table>
  <tr><th>Component</th><th>8 × RTX 4090</th><th>6 × RTX 5090</th></tr>
  <tr><td><b>Total installed CAPEX</b></td><td class="num hl">$18,000</td><td class="num hl">$18,000</td></tr>
</table>
<p class="tbl-cap">Both builds = 3.3 kW thermal, identical to H1 spec.</p>
```

---

## 🔁 Cards

Parallel concepts. Deck: `.cards.c2` / `.c3`. Optional `.tag` kicker per card.

```html
<div class="cards c2">
  <div class="card">
    <span class="tag">Layer 1 · Commodity</span>
    <div class="ttl">Physical <span class="a">hardware</span></div>
    <p>Near-zero margin at scale. It exists to create the other three layers.</p>
  </div>
  <div class="card">
    <span class="tag">Layer 4 · The Moat</span>
    <div class="ttl">Servicing &amp; <span class="a">orchestration</span></div>
    <p>Sticky, recurring, never sold. <b>Only Superheat can operate the fleet.</b></p>
  </div>
</div>
```

---

## 🖥️ Flow (pipeline of steps)

```html
<div class="flow">
  <span class="step">Originate</span><span class="arr">→</span>
  <span class="step">Package</span><span class="arr">→</span>
  <span class="step">Sell</span><span class="arr">→</span>
  <span class="step">Recycle capital</span><span class="arr">→</span>
  <span class="step">Repeat</span>
</div>
```

---

## 🖥️ Equation strip (reframe)

`.chip` = neutral term · `.chip.gain` = the orange win · `.to` / `.plus` = orange operators.

```html
<div class="eq">
  <div class="row">
    <span class="lbl">Regular heater</span>
    <span class="chip">Electricity</span><span class="to">→</span><span class="chip">Hot water</span>
    <span class="verdict">a cost center</span>
  </div>
  <div class="row">
    <span class="lbl">Superheat H1</span>
    <span class="chip">Electricity</span><span class="to">→</span><span class="chip">Hot water</span>
    <span class="plus">+</span><span class="chip gain">Compute revenue</span>
    <span class="verdict">an income-producing, financeable asset</span>
  </div>
</div>
```

---

## 🖥️ Bar chart

Set each `.fill` height as a % of the tallest bar (tallest = `100%`).

```html
<div class="bars" aria-label="Net cash per unit by year">
  <div class="bar"><div class="v">$12.0K</div><div class="fill" style="height:100%"></div><div class="y">Yr 1</div></div>
  <div class="bar"><div class="v">$9.6K</div><div class="fill" style="height:80%"></div><div class="y">Yr 2</div></div>
  <div class="bar"><div class="v">$3.9K</div><div class="fill" style="height:33%"></div><div class="y">Yr 6</div></div>
</div>
```

---

## 🖥️ Numbered list (actions / contacts)

```html
<div class="nlist">
  <div class="nitem"><span class="no">01</span><div><div class="who">Upper90</div><div class="ask">Lead $10–20M hybrid equity + first-loss. They did Crusoe.</div></div></div>
  <div class="nitem"><span class="no">02</span><div><div class="who">GoodLeap</div><div class="ask">H1 as an approved financed product; 500-loan pilot.</div></div></div>
</div>
```

---

## 🖥️ Footnote / source (deck)

Anchored to the bottom of the slide; carries the honest caveat.

```html
<p class="foot-note">Read the second stat honestly: ≈ <b>$300–600 per unit-year realized</b> — largely bitcoin-era units on residential duty cycles.</p>
<p class="src">Source: Vast.ai live snapshot, 06.11.2026 · <a href="#">methodology</a></p>
```

---

## 📄 Whitepaper: memo header

```html
<div class="memo-head">
  <div class="brand"><span class="wm">Superheat<sup>™</sup></span><span class="tag">&gt; WHITEPAPER MEMO_</span></div>
  <dl class="memo-grid">
    <dt>Re</dt><dd>From thermal hardware to financial infrastructure</dd>
    <dt>Date</dt><dd>June 2026 · internal working draft v1.0</dd>
    <dt>Sources</dt><dd>Consolidates: <i>One-Pager</i> · <i>Economics Plan</i> · <i>Capital Map</i></dd>
  </dl>
</div>
```

## 📄 Whitepaper: section head, lede, callout

```html
<h2><span class="no">0</span>Executive summary</h2>
<p class="lede">Superheat's product was never the water heater, and it is not even the compute.</p>
<p>Supporting paragraph, dense and footnoted…</p>
<div class="callout"><b>The heater is the commodity. The manufactured cash flow is the business.</b></div>
```

## 📄 Whitepaper: two-column, call list, page footer

```html
<div class="cols">
  <div><h3><span class="a">Product A</span> — Residential</h3><p>…</p><ul><li>…</li></ul></div>
  <div><h3><span class="a">Product B</span> — Commercial</h3><p>…</p><ul><li>…</li></ul></div>
</div>

<div class="calls">
  <div class="c"><span class="no">01</span><span><b>Upper90</b> — lead $10–20M hybrid equity + first-loss.</span></div>
</div>

<div class="pfoot"><span>SUPERHEAT™ · WHITEPAPER MEMO · 06.2026</span><span class="o">02 / 09</span></div>
```

---

For the rules behind these components (color discipline, type moves, rhythm, voice),
read the [design system](../design-system/README.md).
