
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ultra Phone Number Replacer</title>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #ffffff;
      --bg2: #f5f5f4;
      --bg3: #eeede9;
      --text: #1a1a1a;
      --text2: #666;
      --border: #d1d0cc;
      --accent: #1a1a1a;
      --accent-text: #fff;
      --info-bg: #e6f1fb;
      --info-text: #185fa5;
      --mark-bg: #B5D4F4;
      --mark-text: #042C53;
      --mark-usa-bg: #FFE5B4;
      --mark-usa-text: #7A4000;
      --usa-border: #f59e0b;
      --usa-bg: #fffbeb;
      --radius: 8px;
      --radius-lg: 12px;
    }

    @media (prefers-color-scheme: dark) {
      :root {
        --bg: #1c1c1c;
        --bg2: #252525;
        --bg3: #2e2e2e;
        --text: #e8e8e6;
        --text2: #999;
        --border: #3a3a3a;
        --accent: #e8e8e6;
        --accent-text: #1c1c1c;
        --info-bg: #0c3456;
        --info-text: #85b7eb;
        --mark-bg: #0c447c;
        --mark-text: #B5D4F4;
        --mark-usa-bg: #5a3200;
        --mark-usa-text: #ffd580;
        --usa-border: #b45309;
        --usa-bg: #2a1f00;
      }
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
      background: var(--bg);
      color: var(--text);
      min-height: 100vh;
      padding: 2rem 1rem;
    }

    .container {
      max-width: 820px;
      margin: 0 auto;
    }

    header {
      margin-bottom: 2rem;
    }

    header h1 {
      font-size: 22px;
      font-weight: 600;
      margin-bottom: 4px;
    }

    header p {
      font-size: 13px;
      color: var(--text2);
    }

    .card {
      background: var(--bg);
      border: 0.5px solid var(--border);
      border-radius: var(--radius-lg);
      padding: 1.25rem;
      margin-bottom: 1rem;
    }

    .usa-card {
      border: 1.5px solid var(--usa-border);
      background: var(--usa-bg);
    }

    .section { margin-bottom: 1.2rem; }
    .section:last-child { margin-bottom: 0; }

    label {
      display: block;
      font-size: 12px;
      font-weight: 600;
      color: var(--text2);
      margin-bottom: 6px;
      text-transform: uppercase;
      letter-spacing: 0.05em;
    }

    input[type="text"], textarea {
      width: 100%;
      padding: 10px 13px;
      border-radius: var(--radius);
      border: 0.5px solid var(--border);
      background: var(--bg2);
      color: var(--text);
      font-family: 'SF Mono', 'Fira Code', 'Cascadia Code', monospace;
      font-size: 13px;
      outline: none;
      transition: box-shadow 0.15s;
    }

    input[type="text"] { font-size: 15px; }

    input[type="text"]:focus,
    textarea:focus {
      box-shadow: 0 0 0 2px var(--info-bg);
      border-color: var(--info-text);
    }

    textarea { resize: vertical; line-height: 1.7; min-height: 130px; }

    .inline-row {
      display: flex;
      gap: 12px;
      align-items: flex-end;
      flex-wrap: wrap;
    }

    .inline-row .field { flex: 1; min-width: 180px; }
    .inline-row .field-small { width: 90px; flex: none; }

    .btn-row { display: flex; gap: 8px; flex-wrap: wrap; margin-top: 10px; }

    button {
      padding: 9px 18px;
      border-radius: var(--radius);
      border: 0.5px solid var(--border);
      background: var(--bg);
      color: var(--text);
      font-size: 13px;
      font-family: inherit;
      cursor: pointer;
      transition: background 0.15s;
    }

    button:hover { background: var(--bg2); }

    .btn-primary {
      background: var(--accent);
      color: var(--accent-text);
      border-color: var(--accent);
    }

    .btn-primary:hover { opacity: 0.85; background: var(--accent); }

    .stats-row { display: flex; gap: 10px; margin: 12px 0 0; flex-wrap: wrap; }

    .stat {
      flex: 1;
      min-width: 100px;
      background: var(--bg2);
      border-radius: var(--radius);
      padding: 10px 14px;
    }

    .stat.usa-stat {
      background: var(--usa-bg);
      border: 1px solid var(--usa-border);
    }

    .stat-label { font-size: 10px; color: var(--text2); text-transform: uppercase; letter-spacing: .05em; }
    .stat-val { font-size: 24px; font-weight: 600; margin-top: 2px; }
    .stat.usa-stat .stat-val { color: var(--mark-usa-text); }

    .mono-block {
      font-family: 'SF Mono', 'Fira Code', monospace;
      font-size: 12px;
      background: var(--bg3);
      border-radius: var(--radius);
      padding: 12px;
      max-height: 280px;
      overflow-y: auto;
      white-space: pre-wrap;
      word-break: break-all;
      line-height: 1.8;
      color: var(--text);
    }

    mark {
      background: var(--mark-bg);
      color: var(--mark-text);
      border-radius: 3px;
      padding: 0 2px;
    }

    mark.usa {
      background: var(--mark-usa-bg);
      color: var(--mark-usa-text);
      border-radius: 3px;
      padding: 0 2px;
    }

    .pill {
      display: inline-block;
      font-size: 10px;
      padding: 2px 8px;
      border-radius: 20px;
      background: var(--info-bg);
      color: var(--info-text);
      margin-left: 6px;
      font-weight: 600;
      vertical-align: middle;
    }

    .pill.usa-pill {
      background: var(--mark-usa-bg);
      color: var(--mark-usa-text);
    }

    .info-text {
      font-size: 12px;
      color: var(--text2);
      margin-top: 5px;
      line-height: 1.5;
    }

    .hidden { display: none; }

    .divider {
      border: none;
      border-top: 0.5px solid var(--border);
      margin: 1rem 0;
    }

    footer {
      margin-top: 2rem;
      font-size: 12px;
      color: var(--text2);
      text-align: center;
    }

    .toggle-row {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 12px;
    }

    .toggle-label {
      font-size: 13px;
      font-weight: 500;
      color: var(--text);
      cursor: pointer;
      user-select: none;
    }

    /* Toggle Switch */
    .switch {
      position: relative;
      display: inline-block;
      width: 42px;
      height: 24px;
      flex-shrink: 0;
    }

    .switch input { opacity: 0; width: 0; height: 0; }

    .slider {
      position: absolute;
      cursor: pointer;
      top: 0; left: 0; right: 0; bottom: 0;
      background: var(--border);
      border-radius: 34px;
      transition: 0.2s;
    }

    .slider:before {
      position: absolute;
      content: "";
      height: 18px;
      width: 18px;
      left: 3px;
      bottom: 3px;
      background: white;
      border-radius: 50%;
      transition: 0.2s;
    }

    input:checked + .slider { background: #f59e0b; }
    input:checked + .slider:before { transform: translateX(18px); }

    .usa-section {
      border: 1.5px solid var(--usa-border);
      border-radius: var(--radius-lg);
      padding: 14px;
      background: var(--usa-bg);
      transition: opacity 0.2s;
    }

    .usa-section.disabled {
      opacity: 0.4;
      pointer-events: none;
    }

    .usa-flag {
      font-size: 16px;
      margin-right: 4px;
    }

    .section-title {
      font-size: 13px;
      font-weight: 600;
      color: var(--text);
      margin-bottom: 12px;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .badge {
      font-size: 10px;
      background: var(--usa-border);
      color: #fff;
      padding: 2px 7px;
      border-radius: 20px;
      font-weight: 600;
    }
  </style>
</head>
<body>
<div class="container">

  <header>
    <h1>Ultra Phone Number Replacer</h1>
    <p>Replaces phone numbers in any unicode format — bold digits, combining underlines, overlays, fullwidth, circled, and more.</p>
  </header>

  <!-- Input card -->
  <div class="card">
    <div class="inline-row">
      <div class="field section">
        <label>Your replacement number (default / non-USA)</label>
        <input type="text" id="myNum" placeholder="e.g. 52 800 999 1234">
        <p class="info-text">Only digits matter — spaces/dashes for readability are fine.</p>
      </div>
      <div class="field-small section">
        <label>Min digits</label>
        <input type="text" id="minD" value="6" style="width:80px">
        <p class="info-text">Min digits to treat as phone number.</p>
      </div>
    </div>

    <!-- USA Toggle + Section -->
    <div class="section">
      <div class="toggle-row">
        <label class="switch">
          <input type="checkbox" id="usaToggle" onchange="toggleUSA()">
          <span class="slider"></span>
        </label>
        <span class="toggle-label"><span class="usa-flag">🇺🇸</span> USA Number Replacement (<code style="font-size:11px">+1 / 1-xxx</code> numbers ko alag number se replace karein)</span>
      </div>

      <div class="usa-section disabled" id="usaSection">
        <div class="section-title">
          <span>🇺🇸 USA Number Replacement</span>
          <span class="badge">+1 / 1-xxx</span>
        </div>
        <input type="text" id="usaNum" placeholder="e.g. 1 800 555 0123">
        <p class="info-text" style="margin-top:6px">Numbers starting with <strong>+1</strong> or <strong>1</strong> followed by 10 digits will be replaced with this number. All other numbers will use the default replacement above.</p>
      </div>
    </div>

    <div class="section">
      <label>Paste your PDF / text content here</label>
      <textarea id="inp" rows="10" placeholder="Paste content here...&#10;&#10;Supports: ★[52]✤800-||𝟺𝟼𝟷||-𝟷3*8#2&#10;52-𝟴0-̲4̾6̾1̾-̲𝟭𝟯𝟴𝟮  5̲2̲-̲8̲0̲0̲-̲4̾6̾1̾-̲1̲3̲8̲2̲  +𝟓𝟸 𝟾𝟶𝟶 𝟺𝟼𝟷 𝟷𝟹𝟾𝟸&#10;USA: +1 800 555 1234  or  1-888-999-0000"></textarea>
    </div>

    <div class="btn-row">
      <button class="btn-primary" onclick="go()">Replace All Numbers</button>
      <button onclick="loadSample()">Load sample</button>
      <button onclick="clearAll()">Clear</button>
    </div>
  </div>

  <!-- Stats + Output -->
  <div id="resultCard" class="card hidden">
    <div class="stats-row">
      <div class="stat">
        <div class="stat-label">Total spans replaced</div>
        <div class="stat-val" id="sc">0</div>
      </div>
      <div class="stat">
        <div class="stat-label">Digits replaced</div>
        <div class="stat-val" id="dc">0</div>
      </div>
      <div class="stat usa-stat" id="usaStatBox" style="display:none">
        <div class="stat-label">🇺🇸 USA spans replaced</div>
        <div class="stat-val" id="usasc">0</div>
      </div>
    </div>

    <hr class="divider">

    <div class="section">
      <label>Output</label>
      <textarea id="out" rows="10" readonly></textarea>
    </div>

    <div class="btn-row">
      <button onclick="copyOut()">Copy output</button>
      <button onclick="toggleHL()">Highlight view</button>
      <button onclick="toggleDbg()">Debug log</button>
    </div>

    <div id="hlSec" class="hidden" style="margin-top:12px">
      <label>
        Highlight view
        <span class="pill">replaced = blue</span>
        <span class="pill usa-pill" id="usaPillLegend" style="display:none">🇺🇸 USA = orange</span>
      </label>
      <div id="hlView" class="mono-block"></div>
    </div>

    <div id="dbgSec" class="hidden" style="margin-top:12px">
      <label>Debug log</label>
      <div id="dbg" class="mono-block"></div>
    </div>
  </div>

  <footer>Ultra Phone Number Replacer &mdash; works fully offline, no server needed.</footer>
</div>

<script>
// ═══════════════════════════════════════════════════════════════════════════
// 1. UNICODE DIGIT MAP
// ═══════════════════════════════════════════════════════════════════════════
function buildDigitMap() {
  const m = {};
  function addRange(base, startDigit) {
    for (let d = startDigit; d <= 9; d++) {
      try { m[String.fromCodePoint(base + d)] = String(d); } catch(e) {}
    }
  }
  addRange(0x1D7CE, 0); addRange(0x1D7D8, 0); addRange(0x1D7E2, 0);
  addRange(0x1D7EC, 0); addRange(0x1D7F6, 0); addRange(0xFF10, 0);
  addRange(0x2460, 1); addRange(0x2776, 1); addRange(0x24F5, 1);
  addRange(0x2780, 1); addRange(0x24EA, 0); addRange(0x1F101, 0);
  addRange(0x1F10B, 0);
  '⁰¹²³⁴⁵⁶⁷⁸⁹'.split('').forEach((c, i) => m[c] = String(i));
  '₀₁₂₃₄₅₆₇₈₉'.split('').forEach((c, i) => m[c] = String(i));
  '⓿❶❷❸❹❺❻❼❽❾'.split('').forEach((c, i) => m[c] = String(i));
  '٠١٢٣٤٥٦٧٨٩'.split('').forEach((c, i) => m[c] = String(i));
  '۰۱۲۳۴۵۶۷۸۹'.split('').forEach((c, i) => m[c] = String(i));
  '०१२३४५६७८९'.split('').forEach((c, i) => m[c] = String(i));
  '০১২৩৪৫৬৭৮৯'.split('').forEach((c, i) => m[c] = String(i));
  '๐๑๒๓๔๕๖๗๘๙'.split('').forEach((c, i) => m[c] = String(i));
  '០១២៣៤៥៦៧៨៩'.split('').forEach((c, i) => m[c] = String(i));
  '၀၁၂၃၄၅၆၇၈၉'.split('').forEach((c, i) => m[c] = String(i));
  return m;
}

const DMAP = buildDigitMap();

function toAsciiDigit(c) {
  if (c >= '0' && c <= '9') return c;
  return DMAP[c] || null;
}

// ═══════════════════════════════════════════════════════════════════════════
// 2. COMBINING CHARACTER DETECTOR
// ═══════════════════════════════════════════════════════════════════════════
function isCombining(cp) {
  if (cp >= 0x0300 && cp <= 0x036F) return true;
  if (cp >= 0x1AB0 && cp <= 0x1AFF) return true;
  if (cp >= 0x1DC0 && cp <= 0x1DFF) return true;
  if (cp >= 0x20D0 && cp <= 0x20FF) return true;
  if (cp >= 0xFE20 && cp <= 0xFE2F) return true;
  if (cp === 0x200B || cp === 0x200C || cp === 0x200D || cp === 0xFEFF || cp === 0x00AD) return true;
  return false;
}

// ═══════════════════════════════════════════════════════════════════════════
// 3. SEPARATOR DETECTOR
// ═══════════════════════════════════════════════════════════════════════════
const SEP_SET = new Set([
  ...' \t\n\r',
  ...'-.,()|~_+[]{}/\\:!*#^@=<>·•',
  ...'✤➠➟⪼★✧❀🫠🛬✈🌐💯⭐😊💼🎀🍒⚡→←↑↓↔',
  ...'【】〔〕〖〗（）＋－＊／：；，。？！《》「」『』',
  // Extra pipe/bar variants used in obfuscated numbers
  ...'│┃╎╏║¦‖',
]);

function isSep(c) {
  if (SEP_SET.has(c)) return true;
  const cp = c.codePointAt(0);
  if (cp >= 0x2000 && cp <= 0x206F) return true; // General Punctuation
  if (cp >= 0x2190 && cp <= 0x21FF) return true; // Arrows block (→←↑↓ etc.)
  if (cp >= 0x2700 && cp <= 0x27BF) return true; // Dingbats (✤➠➟➤ etc.)
  if (cp >= 0x2900 && cp <= 0x297F) return true; // Supplemental Arrows-B (⪼ etc.)
  if (cp >= 0x2B00 && cp <= 0x2BFF) return true; // Misc Symbols and Arrows
  if (cp >= 0x2E00 && cp <= 0x2E7F) return true; // Supplemental Punctuation
  if (cp >= 0x3000 && cp <= 0x303F) return true; // CJK Symbols and Punctuation
  if (cp >= 0xFE50 && cp <= 0xFE6F) return true; // Small Form Variants
  if (cp >= 0x1F300 && cp <= 0x1FAFF) return true; // Emoji / symbols range
  return false;
}

// ═══════════════════════════════════════════════════════════════════════════
// 4. TOKENISER
// ═══════════════════════════════════════════════════════════════════════════
function tokenise(text) {
  const tokens = [];
  const chars = [...text];
  let i = 0;
  while (i < chars.length) {
    const c = chars[i];
    const cp = c.codePointAt(0);
    if (isCombining(cp)) {
      if (tokens.length > 0) tokens[tokens.length - 1].orig += c;
      else tokens.push({ type: 'combining', orig: c, ascii: '' });
      i++; continue;
    }
    const ascii = toAsciiDigit(c);
    if (ascii !== null) {
      const tok = { type: 'digit', orig: c, ascii };
      i++;
      while (i < chars.length && isCombining(chars[i].codePointAt(0))) { tok.orig += chars[i]; i++; }
      tokens.push(tok); continue;
    }
    if (isSep(c)) {
      let s = c; i++;
      while (i < chars.length) {
        const nc = chars[i];
        if (isCombining(nc.codePointAt(0))) { s += nc; i++; continue; }
        if (isSep(nc)) { s += nc; i++; continue; }
        break;
      }
      tokens.push({ type: 'sep', orig: s, ascii: '' }); continue;
    }
    tokens.push({ type: 'other', orig: c, ascii: '' });
    i++;
  }
  return tokens;
}

// ═══════════════════════════════════════════════════════════════════════════
// 5. SPAN FINDER
//    A span starts when we see a digit, or a sep-containing-'+' immediately
//    followed (possibly after more seps) by a digit.
//    The leading '+'/sep IS included in the span so it's preserved in output.
// ═══════════════════════════════════════════════════════════════════════════
function findSpans(tokens, minDigits) {
  const n = tokens.length;
  const spans = [];
  let i = 0;

  while (i < n) {
    const t = tokens[i];
    let spanStart = i;
    let firstDigitAt = -1;

    if (t.type === 'digit') {
      // Span starts right here with a digit
      firstDigitAt = i;
    } else if (t.type === 'sep' && t.orig.includes('+')) {
      // Sep token has a '+' — look ahead past any further seps for the first digit
      let k = i + 1;
      while (k < n && tokens[k].type === 'sep') k++;
      if (k < n && tokens[k].type === 'digit') {
        // Include the leading sep(s) in the span so '+' is preserved in output
        spanStart = i;
        firstDigitAt = k;
      }
    }

    if (firstDigitAt === -1) { i++; continue; }

    // Now walk from firstDigitAt collecting digit+sep tokens
    let j = firstDigitAt;
    let digitCount = 0;
    let lastDigitJ = -1;

    while (j < n) {
      const tk = tokens[j];
      if (tk.type === 'digit') {
        digitCount++;
        lastDigitJ = j;
        j++;
      } else if (tk.type === 'sep') {
        // Only continue if there's a digit coming after this sep group
        let k = j + 1;
        while (k < n && tokens[k].type === 'sep') k++;
        if (k < n && tokens[k].type === 'digit') { j = k; }
        else { break; }
      } else {
        break; // hit a letter/other char — stop
      }
    }

    const end = lastDigitJ >= 0 ? lastDigitJ + 1 : spanStart + 1;
    if (digitCount >= minDigits && lastDigitJ >= firstDigitAt) {
      spans.push({ start: spanStart, end, digitCount });
      i = end;
    } else {
      i++;
    }
  }
  return spans;
}

// ═══════════════════════════════════════════════════════════════════════════
// 6. USA NUMBER DETECTOR
//    The span now INCLUDES any leading sep (e.g. "+", "++", " +").
//    A USA number is one whose digit sequence starts with 1 and has 11 digits,
//    OR has a + prefix with a leading 1 (country code) and 10 more digits.
// ═══════════════════════════════════════════════════════════════════════════
function isUSASpan(tokens, span) {
  // Collect all ascii digits in span in order
  const digits = [];
  for (let i = span.start; i < span.end; i++) {
    if (tokens[i].type === 'digit') digits.push(tokens[i].ascii);
  }
  const digitStr = digits.join('');

  // Check if span has a leading '+' (in the first sep token of the span, or token before)
  let hasPlusPrefix = false;
  // Check the first token of span if it's a sep
  if (tokens[span.start].type === 'sep' && tokens[span.start].orig.includes('+')) hasPlusPrefix = true;
  // Also check token before span in case span starts directly with digit
  if (!hasPlusPrefix && span.start > 0 && tokens[span.start - 1].type === 'sep'
      && tokens[span.start - 1].orig.includes('+')) hasPlusPrefix = true;

  // +1 XXXXXXXXXX  → hasPlusPrefix + digits start with 1, total 11 digits
  if (hasPlusPrefix && digitStr.length === 11 && digitStr.startsWith('1')) return true;
  // +1 with country code as sep, span has 10 digits (no leading 1 in digit stream)
  if (hasPlusPrefix && digitStr.length === 10) return true;
  // No +, but 11 digits starting with 1  → treat as USA (1-800-xxx-xxxx format)
  if (!hasPlusPrefix && digitStr.length === 11 && digitStr.startsWith('1')) return true;

  return false;
}

// ═══════════════════════════════════════════════════════════════════════════
// 7. DIGIT REPLACER
//    Strategy: Walk through the span token-by-token.
//    - Non-digit tokens (separators, symbols) are kept AS-IS in their position.
//    - Digit tokens are replaced one-for-one with digits from myDigits.
//    - If source has MORE digits than myDigits: extra source digits are dropped
//      (we stop emitting digits once myDigits is exhausted, but keep separators).
//    - If source has FEWER digits than myDigits: remaining myDigits are appended
//      right after the last digit in the span.
//    This ensures output ALWAYS contains exactly the digits of myDigits.
// ═══════════════════════════════════════════════════════════════════════════
function replaceSpan(tokens, span, myDigits) {
  let di = 0;                // index into myDigits
  let out = '';
  let lastDigitPos = -1;     // track where to append leftover digits

  for (let i = span.start; i < span.end; i++) {
    const tk = tokens[i];
    if (tk.type === 'digit') {
      if (di < myDigits.length) {
        // Replace this source digit with next myDigit
        const baseChar = [...tk.orig][0];
        const combining = tk.orig.slice(baseChar.length);
        out += myDigits[di] + combining;
        lastDigitPos = out.length; // remember end position after this digit+combining
        di++;
      }
      // If myDigits exhausted: silently drop extra source digits
    } else {
      out += tk.orig; // keep separator/symbol unchanged
    }
  }

  // If myDigits has MORE digits than source, append remaining digits at end
  if (di < myDigits.length) {
    out += myDigits.slice(di);
  }

  return out;
}

// ═══════════════════════════════════════════════════════════════════════════
// 8. MAIN ENGINE
// ═══════════════════════════════════════════════════════════════════════════
let lastOutput = '';
let replacedTexts = [];    // [{text, isUSA}]

function go() {
  const myNum = document.getElementById('myNum').value.trim();
  const text = document.getElementById('inp').value;
  const minD = Math.max(1, parseInt(document.getElementById('minD').value) || 6);
  const usaEnabled = document.getElementById('usaToggle').checked;
  const usaNum = document.getElementById('usaNum').value.trim();

  if (!myNum) { alert('Pehle apna replacement number enter karein!'); return; }
  if (!text)  { alert('Content paste karein!'); return; }

  const myDigits = myNum.replace(/\D/g, '');
  if (myDigits.length < 2) { alert('Valid number enter karein (at least 2 digits)'); return; }

  let usaDigits = null;
  if (usaEnabled) {
    if (!usaNum) { alert('USA replacement number enter karein ya USA feature band karein!'); return; }
    usaDigits = usaNum.replace(/\D/g, '');
    if (usaDigits.length < 2) { alert('Valid USA number enter karein!'); return; }
  }

  const tokens = tokenise(text);
  const spans  = findSpans(tokens, minD);

  // Tag each span as USA or not
  const taggedSpans = spans.map(sp => ({
    ...sp,
    isUSA: usaEnabled ? isUSASpan(tokens, sp) : false
  }));

  // Debug log
  const dbgLines = [
    `Tokens: ${tokens.length} | Spans found: ${spans.length} | Your digits: ${myDigits}`,
    usaEnabled ? `USA mode ON | USA digits: ${usaDigits}` : `USA mode OFF`,
    ''
  ];
  taggedSpans.forEach((s, idx) => {
    const preview = tokens.slice(s.start, s.end).map(t => t.orig).join('');
    dbgLines.push(`[${idx+1}] ${s.isUSA ? '🇺🇸 USA' : 'DEFAULT'} digits=${s.digitCount}  tok[${s.start}–${s.end}]  → "${preview.substring(0,60)}"`);
  });
  document.getElementById('dbg').textContent = dbgLines.join('\n');

  if (spans.length === 0) {
    document.getElementById('resultCard').classList.remove('hidden');
    document.getElementById('dbgSec').classList.remove('hidden');
    document.getElementById('sc').textContent = '0';
    document.getElementById('dc').textContent = '0';
    document.getElementById('out').value = text;
    alert('Koi phone number nahi mila. Debug log check karein.');
    return;
  }

  // Build output
  let result = '';
  let prev = 0;
  let totalDigits = 0;
  let usaCount = 0;
  replacedTexts = [];

  for (const sp of taggedSpans) {
    for (let i = prev; i < sp.start; i++) result += tokens[i].orig;
    const digitsToUse = (sp.isUSA && usaDigits) ? usaDigits : myDigits;
    const rep = replaceSpan(tokens, sp, digitsToUse);
    replacedTexts.push({ text: rep, isUSA: sp.isUSA });
    result += rep;
    totalDigits += sp.digitCount;
    if (sp.isUSA) usaCount++;
    prev = sp.end;
  }
  for (let i = prev; i < tokens.length; i++) result += tokens[i].orig;

  lastOutput = result;
  document.getElementById('sc').textContent = spans.length;
  document.getElementById('dc').textContent = totalDigits;
  document.getElementById('out').value = result;
  document.getElementById('resultCard').classList.remove('hidden');
  document.getElementById('hlSec').classList.add('hidden');
  document.getElementById('dbgSec').classList.add('hidden');

  // USA stat box
  const usaStatBox = document.getElementById('usaStatBox');
  if (usaEnabled) {
    usaStatBox.style.display = '';
    document.getElementById('usasc').textContent = usaCount;
  } else {
    usaStatBox.style.display = 'none';
  }

  const usaPill = document.getElementById('usaPillLegend');
  usaPill.style.display = usaEnabled ? '' : 'none';
}

// ═══════════════════════════════════════════════════════════════════════════
// 9. UI HELPERS
// ═══════════════════════════════════════════════════════════════════════════
function toggleUSA() {
  const on = document.getElementById('usaToggle').checked;
  const sec = document.getElementById('usaSection');
  sec.classList.toggle('disabled', !on);
}

function toggleHL() {
  const sec = document.getElementById('hlSec');
  if (!sec.classList.contains('hidden')) { sec.classList.add('hidden'); return; }

  let html = esc(lastOutput);

  // Highlight USA spans first (orange), then normal (blue)
  // We do it by building HTML with marks inline from replacedTexts
  // Rebuild highlight from scratch for accuracy
  let hlHtml = '';
  let remaining = lastOutput;

  // Simple sequential highlight: go through replacedTexts in order
  for (const { text: t, isUSA } of replacedTexts) {
    const idx = remaining.indexOf(t);
    if (idx === -1) continue;
    hlHtml += esc(remaining.slice(0, idx));
    hlHtml += `<mark class="${isUSA ? 'usa' : ''}">${esc(t)}</mark>`;
    remaining = remaining.slice(idx + t.length);
  }
  hlHtml += esc(remaining);

  document.getElementById('hlView').innerHTML = hlHtml;
  sec.classList.remove('hidden');
}

function toggleDbg() {
  document.getElementById('dbgSec').classList.toggle('hidden');
}

function esc(s) {
  return s
    .replace(/&/g, '&amp;')
    .replace(/</g, '&lt;')
    .replace(/>/g, '&gt;')
    .replace(/\n/g, '<br>');
}

function copyOut() {
  navigator.clipboard.writeText(lastOutput).then(() => {
    const b = event.target;
    b.textContent = 'Copied!';
    setTimeout(() => b.textContent = 'Copy output', 1500);
  });
}

function loadSample() {
  document.getElementById('inp').value =
`+52-800-➤953-➤𝟘𝟝𝟠𝟜
＋5 2 －（ 800 ） — || -+46 113-8252800
++52➞800➞953➞0584
++1➞800➞255➞2208
+𝟓𝟸 𝟾𝟶𝟶 𝟺𝟼𝟷 𝟷𝟹𝟾𝟸
5̲2̲-̲8̲0̲0̲-̲4̾6̾1̾-̲1̲3̲8̲2̲
+1 800 555 1234
1-888-999-0000
+𝟏 𝟒𝟎𝟖 𝟓𝟓𝟓 𝟗𝟗𝟗𝟗`;
  document.getElementById('myNum').value = '52 999 888 7777';
  document.getElementById('usaNum').value = '1 800 123 4567';
  document.getElementById('usaToggle').checked = true;
  toggleUSA();
}

function clearAll() {
  ['myNum', 'inp', 'out', 'usaNum'].forEach(id => document.getElementById(id).value = '');
  document.getElementById('resultCard').classList.add('hidden');
  document.getElementById('hlSec').classList.add('hidden');
  document.getElementById('dbgSec').classList.add('hidden');
  lastOutput = ''; replacedTexts = [];
}
</script>
</body>
</html>
