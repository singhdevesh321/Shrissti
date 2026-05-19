<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>For Shrissti’s Tomorrow</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      font-family: system-ui, -apple-system, "Segoe UI", sans-serif;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 20px;
      background: radial-gradient(circle at top, #fce4ec, #e3f2fd, #e8eaf6);
    }
    .wrapper {
      position: relative;
      width: 100%;
      max-width: 620px;
    }
    .glow {
      position: absolute;
      inset: -20px;
      background: radial-gradient(circle, rgba(255,255,255,0.7), transparent 60%);
      opacity: 0.6;
      filter: blur(8px);
      pointer-events: none;
    }
    .card {
      position: relative;
      background: #ffffffee;
      border-radius: 22px;
      padding: 26px 26px 30px;
      box-shadow: 0 18px 40px rgba(0, 0, 0, 0.2);
      backdrop-filter: blur(8px);
      overflow: hidden;
    }
    .ribbon {
      position: absolute;
      top: 0;
      left: 0;
      width: 130px;
      height: 130px;
      background: linear-gradient(135deg, #f06292, #ba68c8);
      transform: translate(-35%, -35%) rotate(-12deg);
      opacity: 0.7;
    }
    .ribbon::after {
      content: "🌙";
      position: absolute;
      right: 18px;
      bottom: 24px;
      font-size: 28px;
      color: #fff;
    }
    .header {
      text-align: center;
      margin-bottom: 18px;
    }
    .tagline {
      font-size: 12px;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: #9e9e9e;
      margin-bottom: 6px;
    }
    h1 {
      font-size: 26px;
      color: #303f9f;
      margin-bottom: 4px;
    }
    h2 {
      font-size: 16px;
      color: #616161;
      font-weight: 500;
    }
    .input-row {
      margin-top: 22px;
      display: flex;
      gap: 10px;
      justify-content: center;
      flex-wrap: wrap;
    }
    .input-row input {
      flex: 1 1 220px;
      min-width: 0;
      padding: 11px 14px;
      border-radius: 999px;
      border: 2px solid #c5cae9;
      font-size: 14px;
      outline: none;
      transition: border-color 0.2s, box-shadow 0.2s;
    }
    .input-row input:focus {
      border-color: #5c6bc0;
      box-shadow: 0 0 0 2px rgba(92, 107, 192, 0.2);
    }
    .input-row button {
      padding: 11px 22px;
      border-radius: 999px;
      border: none;
      background: linear-gradient(135deg, #5c6bc0, #ab47bc);
      color: #fff;
      font-size: 14px;
      font-weight: 500;
      cursor: pointer;
      white-space: nowrap;
      transition: transform 0.1s, box-shadow 0.2s, opacity 0.2s;
      box-shadow: 0 6px 16px rgba(171, 71, 188, 0.4);
    }
    .input-row button:hover {
      transform: translateY(-1px);
      box-shadow: 0 10px 22px rgba(171, 71, 188, 0.5);
      opacity: 0.95;
    }
    .message-area {
      margin-top: 22px;
      border-radius: 16px;
      background: linear-gradient(135deg, #f3e5f5, #e3f2fd);
      padding: 16px 18px 18px;
      text-align: left;
      max-height: 320px;
      overflow-y: auto;
      border: 1px solid rgba(92, 107, 192, 0.25);
    }
    .message-title {
      font-size: 13px;
      text-transform: uppercase;
      letter-spacing: 0.12em;
      color: #7e57c2;
      margin-bottom: 6px;
    }
    .message-body {
      font-size: 14px;
      line-height: 1.7;
      color: #37474f;
      white-space: pre-line;
    }
    .name {
      color: #5c6bc0;
      font-weight: 600;
    }
    .footer-note {
      margin-top: 16px;
      font-size: 11px;
      color: #9e9e9e;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="wrapper">
    <div class="glow"></div>
    <div class="card">
      <div class="ribbon"></div>

      <div class="header">
        <div class="tagline">for the days ahead</div>
        <h1>For Your Future, Shrissti</h1>
        <h2>Please write your name once so this wish becomes yours.</h2>
      </div>

      <div class="input-row">
        <input
          type="text"
          id="herName"
          placeholder="Type your name here..."
          autocomplete="off"
        />
        <button onclick="showMessage()">Open my wish</button>
      </div>

      <div class="message-area">
        <div class="message-title">Future wish</div>
        <div id="output" class="message-body">
          When you are ready, type your name above and open what I truly wish for you.
        </div>
      </div>

      <div id="hint" class="footer-note">
        This is not a question, not a request. Just a wish for your tomorrow.
      </div>
    </div>
  </div>

  <script>
    function showMessage() {
      const input = document.getElementById("herName");
      const name = input.value.trim();
      const output = document.getElementById("output");
      const hint = document.getElementById("hint");

      if (!name) {
        output.textContent = "Please write your name first. This wish is meant only for you.";
        return;
      }

      const msg =
`Dear ${name},

I don’t know exactly where life will take you,
which city you will live in,
or what kind of sky you will look at years from now.

But deep in my heart,
I wish that your future feels gentle, kind
and safe enough for you to breathe without overthinking.

I wish your hard work is recognised,
your silence is understood,
and your soft heart is protected instead of being taken for granted.

I hope you meet people who value you,
who don’t make you doubt your worth,
and who make you feel chosen without having to fight for it.

May your days be full of small, quiet joys:
peaceful mornings, messages that make you smile,
and evenings where you feel calm instead of exhausted.

If one day you ever feel lost or alone,
I hope you remember that there is someone
who always, silently, wishes
that life is extra kind to you.

You deserve a future where your heart is not heavy,
your mind is not tired,
and your name is always spoken with respect and love.

From my side,
I will always pray that your story ahead
is softer, brighter and more beautiful
than anything you have imagined for yourself.

– from me`;

      output.textContent = msg;
      hint.textContent = "I genuinely wish all of this reaches you in the best way.";
      input.disabled = true;
    }
  </script>
</body>
</html>
