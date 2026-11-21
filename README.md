<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>DSA Roadmap: Base Camp to Summit</title>
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,400;12..96,600;12..96,800&display=swap" rel="stylesheet">
<style>
:root{
  --night:#10143a; --dusk:#3a2a6e; --glow:#ff8a5c; --sun:#ffc15e; --snow:#f4f1ff; --mint:#38d9b4; --mute:#b9b4dd;
  --card:rgba(20,22,64,.72); --line:rgba(255,255,255,.16);
  box-sizing:border-box; padding-top:env(safe-area-inset-top,0px); padding-bottom:env(safe-area-inset-bottom,0px);
  color-scheme:dark;
}
@media (prefers-color-scheme: dark){:root:not([data-theme="light"]){--night:#10143a}}
:root[data-theme="dark"]{--night:#10143a}
*{box-sizing:border-box;margin:0}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
body{font-family:"Bricolage Grotesque",system-ui,-apple-system,"Segoe UI",sans-serif;color:var(--snow);background:var(--night);line-height:1.55;overflow-x:hidden}
.sky{position:fixed;inset:0;z-index:-1;background:
  radial-gradient(ellipse at 50% 108%,var(--glow) 0,rgba(255,138,92,0) 45%),
  linear-gradient(180deg,#0b0e2e 0%,var(--night) 35%,var(--dusk) 78%,#8a4a7a 100%)}
.stars{position:fixed;inset:0;z-index:-1;background-image:
  radial-gradient(1.5px 1.5px at 12% 18%,#fff,transparent),radial-gradient(1px 1px at 28% 8%,#fff,transparent),
  radial-gradient(1.5px 1.5px at 44% 24%,#fff,transparent),radial-gradient(1px 1px at 63% 12%,#fff,transparent),
  radial-gradient(1.5px 1.5px at 78% 30%,#fff,transparent),radial-gradient(1px 1px at 90% 10%,#fff,transparent),
  radial-gradient(1px 1px at 8% 44%,#fff,transparent),radial-gradient(1px 1px at 55% 40%,#fff,transparent),
  radial-gradient(1.5px 1.5px at 94% 52%,#fff,transparent);opacity:.8}
.mtn{position:fixed;left:0;right:0;bottom:0;height:46vh;z-index:-1;width:100%;pointer-events:none}
.wrap{max-width:980px;margin:0 auto;padding:0 20px}
header{padding:72px 0 40px;text-align:center}
.sun{width:92px;height:92px;border-radius:50%;margin:0 auto 26px;background:radial-gradient(circle at 40% 35%,#fff3c9,var(--sun) 55%,var(--glow));box-shadow:0 0 70px 18px rgba(255,170,90,.45)}
h1{font-size:clamp(2.3rem,7vw,4.6rem);font-weight:800;line-height:1.02;letter-spacing:-.03em}
h1 span{display:block;font-weight:400;color:var(--sun);font-size:.55em;letter-spacing:-.01em;margin-top:10px}
.sub{max-width:560px;margin:22px auto 0;color:var(--mute);font-size:1.08rem}
.stats{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin:34px 0 8px}
.stat{background:var(--card);border:1px solid var(--line);border-radius:14px;padding:16px 8px;text-align:center;backdrop-filter:blur(6px)}
.stat b{display:block;font-size:1.9rem;font-weight:800;color:var(--sun);line-height:1.1}
.stat small{color:var(--mute);font-size:.82rem}
h2{font-size:1.5rem;font-weight:600;margin:46px 0 16px;text-align:center}
.day{display:flex;height:54px;border-radius:12px;overflow:hidden;border:1px solid var(--line)}
.day div{display:flex;flex-direction:column;justify-content:center;align-items:center;font-size:.8rem;color:#10143a;font-weight:600;line-height:1.2;text-align:center;padding:0 4px}
.day div b{font-size:1rem}
.trail{position:relative;margin-top:10px;padding:10px 0}
.trail::before{content:"";position:absolute;left:50%;top:0;bottom:0;width:3px;transform:translateX(-50%);background:repeating-linear-gradient(180deg,var(--sun) 0 10px,transparent 10px 20px);opacity:.7}
.camp{position:relative;width:calc(50% - 34px);margin:0 0 30px;background:var(--card);border:1px solid var(--line);border-radius:18px;padding:20px 22px;backdrop-filter:blur(8px)}
.camp:nth-child(odd){margin-right:auto}
.camp:nth-child(even){margin-left:auto}
.camp::after{content:"";position:absolute;top:26px;width:20px;height:20px;border-radius:50%;background:var(--c);border:4px solid var(--night);box-shadow:0 0 0 2px var(--c),0 0 18px var(--c)}
.camp:nth-child(odd)::after{right:-45px}
.camp:nth-child(even)::after{left:-45px}
.wk{display:inline-block;font-size:.85rem;font-weight:700;color:#10143a;background:var(--c);border-radius:999px;padding:2px 12px}
.camp h3{font-size:1.3rem;font-weight:800;margin:10px 0 6px;letter-spacing:-.01em}
.camp p{color:var(--mute);font-size:.95rem}
.chips{display:flex;flex-wrap:wrap;gap:6px;margin:12px 0}
.chips i{font-style:normal;font-size:.78rem;padding:3px 10px;border-radius:999px;border:1px solid var(--line);background:rgba(255,255,255,.06)}
.goal{border-top:1px solid var(--line);padding-top:10px;font-size:.9rem}
.goal b{color:var(--c)}
.peak{text-align:center;padding:30px 0 10px}
.peak .flag{font-size:3rem}
.quote{max-width:640px;margin:0 auto;font-size:clamp(1.3rem,3.6vw,1.9rem);font-weight:600;line-height:1.25;letter-spacing:-.01em}
.rules{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-top:22px}
.rules div{background:var(--card);border:1px solid var(--line);border-radius:14px;padding:14px 16px;font-size:.92rem;backdrop-filter:blur(6px)}
.rules b{display:block;color:var(--mint);margin-bottom:2px}
footer{text-align:center;padding:30px 0 60px;color:var(--mute);font-size:.9rem}
@media(max-width:720px){
  .stats{grid-template-columns:repeat(2,1fr)}
  .rules{grid-template-columns:1fr}
  .trail::before{left:14px}
  .camp{width:calc(100% - 44px);margin-left:44px!important;margin-right:0!important}
  .camp::after{left:-40px!important;right:auto!important}
}
@media (prefers-reduced-motion: no-preference){
  .sun{animation:rise 1.6s ease-out both}
  @keyframes rise{from{transform:translateY(60px);opacity:0}to{transform:none;opacity:1}}
}
</style>
</head>
<body>
<div class="sky"></div><div class="stars"></div>
<svg class="mtn" viewBox="0 0 1200 400" preserveAspectRatio="none" aria-hidden="true">
  <path d="M0 400V250L140 150L260 240L420 90L560 230L700 130L860 250L1000 140L1200 260V400Z" fill="#2a1f5c" opacity=".75"/>
  <path d="M0 400V300L180 210L320 290L500 170L650 300L820 200L980 300L1100 230L1200 300V400Z" fill="#1a1546" opacity=".9"/>
  <path d="M0 400V340L200 290L380 345L560 280L760 350L960 290L1200 350V400Z" fill="#0d0f2c"/>
</svg>

<div class="wrap">
<header>
  <div class="sun" aria-hidden="true"></div>
  <h1>Base Camp to Summit<span>36 weeks. 2 hours a day. One pattern at a time.</span></h1>
  <p class="sub">You have already solved a few problems. This is the path that turns those few into a skill you can use in any coding test or interview.</p>
  <div class="stats">
    <div class="stat"><b>36</b><small>weeks</small></div>
    <div class="stat"><b>12h</b><small>per week</small></div>
    <div class="stat"><b>200+</b><small>new problems</small></div>
    <div class="stat"><b>432h</b><small>total practice</small></div>
  </div>
</header>

<h2>Your 2 hours, every day</h2>
<div class="day">
  <div style="flex:20;background:#ffc15e"><b>20m</b>Learn</div>
  <div style="flex:50;background:#ff8a5c"><b>50m</b>Solve</div>
  <div style="flex:30;background:#38d9b4"><b>30m</b>Review</div>
  <div style="flex:20;background:#b7a8ff"><b>20m</b>Notes</div>
</div>

<h2>The climb</h2>
<div class="trail">
  <section class="camp" style="--c:#ffc15e">
    <span class="wk">Weeks 1–4</span>
    <h3>Base Camp</h3>
    <p>Get comfortable in C++ and spot the simple patterns.</p>
    <div class="chips"><i>C++ and STL</i><i>Big-O</i><i>Arrays</i><i>Strings</i><i>Hash maps</i></div>
    <div class="goal"><b>You can:</b> use vectors, maps and sets, and recognise a frequency map. About 25 problems.</div>
  </section>
  <section class="camp" style="--c:#ff8a5c">
    <span class="wk">Weeks 5–8</span>
    <h3>Foundations</h3>
    <p>Replace nested loops with smarter moves.</p>
    <div class="chips"><i>Two pointers</i><i>Sliding window</i><i>Prefix sums</i><i>Binary search</i><i>Sorting</i><i>Stack</i><i>Queue</i></div>
    <div class="goal"><b>You can:</b> write binary search from memory and know when a window fits. About 30 problems.</div>
  </section>
  <section class="camp" style="--c:#38d9b4">
    <span class="wk">Weeks 9–14</span>
    <h3>Core Structures</h3>
    <p>Think recursively and work with linked data.</p>
    <div class="chips"><i>Linked lists</i><i>Recursion</i><i>Backtracking</i><i>Trees</i><i>BST</i><i>Heap</i><i>Greedy</i><i>Intervals</i><i>Matrices</i></div>
    <div class="goal"><b>You can:</b> trace recursive calls, run DFS and BFS on trees, and justify a greedy choice. About 45 problems.</div>
  </section>
  <section class="camp" style="--c:#b7a8ff">
    <span class="wk">Weeks 15–22</span>
    <h3>Graphs and DP</h3>
    <p>The hardest stretch, and the one that pays off most.</p>
    <div class="chips"><i>Graphs</i><i>BFS / DFS</i><i>Union-Find</i><i>Topological sort</i><i>Shortest paths</i><i>DP</i><i>Bits</i><i>Trie</i></div>
    <div class="goal"><b>You can:</b> define a DP state, transition and base case, and traverse any graph. About 57 problems.</div>
  </section>
  <section class="camp" style="--c:#ff6f91">
    <span class="wk">Weeks 23–28</span>
    <h3>Sharpening</h3>
    <p>Advanced tools. Learn the basics, treat rare ones as optional.</p>
    <div class="chips"><i>Monotonic stack</i><i>Segment tree</i><i>Fenwick tree</i><i>Number theory</i><i>String matching</i></div>
    <div class="goal"><b>You can:</b> spot next-greater and range-query problems quickly. About 32 problems.</div>
  </section>
  <section class="camp" style="--c:#ffe08a">
    <span class="wk">Weeks 29–36</span>
    <h3>Summit Push</h3>
    <p>Mixed revision, timed tests and mock interviews.</p>
    <div class="chips"><i>Mixed sets</i><i>Timed contests</i><i>Company-style sets</i><i>Mock interviews</i><i>Error log</i></div>
    <div class="goal"><b>You can:</b> pick the right pattern unprompted and explain the trade-offs aloud. About 49 problems.</div>
  </section>
</div>

<div class="peak">
  <div class="flag" aria-hidden="true">🚩</div>
  <p class="quote">Placement-ready does not mean every Hard solved. It means you think clearly, code calmly and explain well.</p>
</div>

<h2>Three habits that carry you up</h2>
<div class="rules">
  <div><b>Try first</b>Struggle honestly, take a small hint, then re-code from a blank editor.</div>
  <div><b>Revisit</b>Re-solve missed problems after 1 day, 3 days and 7 days.</div>
  <div><b>Keep moving</b>Not clicking yet? Add a catch-up week. Exam week? Do 3–4 hours.</div>
</div>

<footer>One problem today is one step higher than yesterday.</footer>
</div>
</body>
</html>
