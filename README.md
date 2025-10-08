<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Tic Tac Toe — Vibe Edition</title>
  <style>
    /* Minimal modern styling with responsive grid */
    :root{--bg:#0f1724;--card:#0b1220;--accent:#7c3aed;--muted:#94a3b8;--win:#16a34a}
    *{box-sizing:border-box;font-family:Inter,ui-sans-serif,system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial}
    html,body{height:100%;margin:0;background:linear-gradient(180deg,#021124 0%, #071735 60%);color:#e6eef8}
    .wrap{min-height:100vh;display:flex;align-items:center;justify-content:center;padding:32px}
    .card{width:min(680px,96vw);background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border-radius:14px;padding:24px;box-shadow:0 8px 30px rgba(2,6,23,0.6);border:1px solid rgba(255,255,255,0.03)}

    header{display:flex;gap:16px;align-items:center;margin-bottom:18px}
    .logo{width:56px;height:56px;border-radius:12px;background:linear-gradient(135deg,var(--accent),#06b6d4);display:grid;place-items:center;font-weight:700;color:white;font-size:20px;box-shadow:0 6px 18px rgba(124,58,237,0.18)}
    h1{font-size:20px;margin:0}
    p.lead{margin:0;color:var(--muted);font-size:13px}

    .board-wrap{display:flex;gap:20px;align-items:flex-start}
    .board{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;background:linear-gradient(180deg, rgba(255,255,255,0.01), transparent);padding:12px;border-radius:10px}
    .cell{width:92px;height:92px;display:grid;place-items:center;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.005));border-radius:8px;font-size:42px;font-weight:800;cursor:pointer;user-select:none;transition:transform .12s ease, box-shadow .12s ease}
    .cell:hover{transform:translateY(-4px);box-shadow:0 8px 20px rgba(2,6,23,0.5)}
    .cell.disabled{cursor:default;opacity:.9}

    .meta{flex:1;display:flex;flex-direction:column;gap:12px}
    .status{background:linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:12px;border-radius:10px}
    .big{font-size:18px;font-weight:700}
    .muted{color:var(--muted);font-size:13px}

    .controls{display:flex;gap:8px;flex-wrap:wrap}
    button.btn{background:transparent;border:1px solid rgba(255,255,255,0.06);padding:10px 14px;border-radius:10px;color:inherit;cursor:pointer;font-weight:600}
    button.primary{background:linear-gradient(90deg,var(--accent),#06b6d4);border:none;color:white}

    .win{outline:4px solid rgba(22,163,74,0.12);box-shadow:0 12px 30px rgba(16,185,129,0.06)}
    .winning-cell{background:linear-gradient(90deg, rgba(22,163,74,0.18), rgba(22,163,74,0.06));transform:scale(1.05);}

    footer{margin-top:18px;border-top:1px dashed rgba(255,255,255,0.02);padding-top:12px;color:var(--muted);font-size:13px;display:flex;justify-content:space-between;gap:12px}

    /* Responsive tweaks */
    @media (max-width:520px){.cell{width:68px;height:68px;font-size:30px}.board-wrap{flex-direction:column}.meta{order:2}}
    pre.readme{white-space:pre-wrap;background:rgba(0,0,0,0.25);padding:12px;border-radius:8px;color:#dbeafe;font-size:13px}
  </style>
</head>
<body>
  <div class="wrap">
    <div class="card" role="application" aria-label="Tic Tac Toe Vibe Game">
      <header>
        <div class="logo">V</div>
        <div>
          <h1>Tic Tac Toe — Vibe Edition</h1>
          <p class="lead">Play locally with a friend. Clean UI, keyboard-friendly, instant replay, and winning glow.</p>
        </div>
      </header>

      <main class="board-wrap">
        <section class="board" id="board" aria-label="Tic Tac Toe board">
          <!-- 9 cells inserted by JS for clarity in code -->
        </section>

        <aside class="meta">
          <div class="status" id="status">
            <div class="big" id="turn">Current: <span id="player">X</span></div>
            <div class="muted" id="message">Take turns. First to align three wins.</div>
          </div>

          <div class="controls">
            <button class="btn" id="newBtn">New Game</button>
            <button class="btn" id="swapBtn">Swap Starting Player</button>
            <button class="btn primary" id="undoBtn">Undo Last Move</button>
          </div>

          <div class="status">
            <div class="muted">Game Info</div>
            <div id="score">X: 0 | O: 0 | Draws: 0</div>
          </div>

          <div class="status">
            <div class="muted">Tips</div>
            <div class="muted">Click or press number keys 1–9 (numpad layout) to place a mark.</div>
          </div>
        </aside>
      </main>

      <footer>
        <div>Built with ❤️ for quick jams</div>
        <div>Vibe™ · Local Multiplayer</div>
      </footer>

      <section style="margin-top:14px">
        <details>
          <summary style="cursor:pointer;color:var(--muted)">README — click to expand (unique &amp; fascinating)</summary>
          <pre class="readme" id="readme">
Tic Tac Toe — Vibe Edition
==========================

A single-file, pocket-sized Tic Tac Toe crafted to feel like a tiny ceremony: small, decisive, and oddly satisfying.

What makes this one special?
- A focused, responsive 3x3 grid with playful micro-interactions.
- Instant visual reward: winning line is highlighted and gently scaled.
- Undo and Swap-start features for endless rematches and fairness.
- Keyboard-friendly: use keys 1–9 (like a numpad) for fast play.
- Single file. No setup. Open in any browser and play.

How to play
-----------
- Two players alternate turns, X starts by default.
- Click a cell or press its corresponding number (1 bottom-left to 9 top-right) to place your mark.
- First to align three marks horizontally, vertically or diagonally wins.
- If the board fills with no winner, it's a draw.
- Use "New Game" to reset the board, "Swap Starting Player" to change who begins, and "Undo Last Move" to reverse a single last move.

Design Philosophy — "Vibe"
--------------------------
I wanted a tiny, elegant experience: no clutter, immediate feedback, and room for personality.
- The UI respects small details — subtle lifts on hover, a soft glow on victory.
- The code keeps logic readable and approachable — perfect for beginners to explore and remix.

Developer Notes
---------------
- Everything is in this file: HTML, CSS and JavaScript.
- Win detection uses a fixed list of winning index triplets — simple and fast.
- The state keeps a move history for undo and animation replay.

License
-------
Use, learn, remix. Attribution appreciated but not required. Have fun.

Thank you for playing. If this little app had an aura, I hope it would be calm, decisive, and slightly mischievous.
          </pre>
        </details>
      </section>

    </div>
  </div>

  <script>
    // Tic Tac Toe — Vibe Edition
    // Single-file game logic. Accessible and concise.

    const boardEl = document.getElementById('board');
    const playerEl = document.getElementById('player');
    const messageEl = document.getElementById('message');
    const turnEl = document.getElementById('turn');
    const scoreEl = document.getElementById('score');

    const newBtn = document.getElementById('newBtn');
    const swapBtn = document.getElementById('swapBtn');
    const undoBtn = document.getElementById('undoBtn');

    // Game state
    let board = Array(9).fill('');
    let current = 'X';
    let starting = 'X';
    let running = true;
    let history = [];
    const score = { X: 0, O: 0, D: 0 };

    const wins = [
      [0,1,2],[3,4,5],[6,7,8], // rows
      [0,3,6],[1,4,7],[2,5,8], // cols
      [0,4,8],[2,4,6] // diags
    ];

    // Create cells
    for(let i=0;i<9;i++){
      const c = document.createElement('button');
      c.className='cell';
      c.setAttribute('data-i', i);
      c.setAttribute('aria-label', `Cell ${i+1}`);
      c.addEventListener('click', onCell);
      c.addEventListener('keydown', (e)=>{ if(e.key==='Enter' || e.key===' ') { e.preventDefault(); onCell(e); } });
      boardEl.appendChild(c);
    }

    function refreshUI(){
      const cells = boardEl.querySelectorAll('.cell');
      cells.forEach((el, idx) => {
        el.textContent = board[idx];
        el.classList.toggle('disabled', !!board[idx] || !running);
        el.classList.remove('winning-cell');
      });
      playerEl.textContent = current;
      scoreEl.textContent = `X: ${score.X} | O: ${score.O} | Draws: ${score.D}`;
    }

    function onCell(e){
      if(!running) return;
      const i = Number(e.currentTarget.dataset.i);
      if(board[i]) return; // occupied
      makeMove(i, current);
    }

    function makeMove(i, player){
      board[i]=player;
      history.push({i,player});
      const winInfo = checkWin();
      if(winInfo){
        // mark winning cells
        winInfo.indices.forEach(idx => {
          boardEl.querySelector(`[data-i='${idx}']`).classList.add('winning-cell');
        });
        messageEl.textContent = `Player ${player} wins! 🎉`;
        score[player]++;
        running = false;
        highlightBoardWin();
      } else if(board.every(Boolean)){
        messageEl.textContent = `It's a draw.`;
        score.D++;
        running = false;
      } else {
        current = current === 'X' ? 'O' : 'X';
        messageEl.textContent = `Good move — ${current}'s turn.`;
      }
      refreshUI();
    }

    function checkWin(){
      for(const trip of wins){
        const [a,b,c]=trip;
        if(board[a] && board[a]===board[b] && board[a]===board[c]){
          return {winner: board[a], indices: trip};
        }
      }
      return null;
    }

    function highlightBoardWin(){
      // add a gentle win outline to the board
      boardEl.classList.add('win');
      setTimeout(()=>boardEl.classList.remove('win'), 1600);
    }

    function newGame(){
      board = Array(9).fill('');
      running = true;
      history = [];
      current = starting;
      messageEl.textContent = `New game — ${current} starts.`;
      refreshUI();
    }

    function swapStart(){
      starting = starting === 'X' ? 'O' : 'X';
      current = starting;
      newGame();
    }

    function undo(){
      if(history.length===0 || !running && history.length===0) return;
      // If game ended, allow undo to resume
      if(!running){
        running = true; // resume if last move undone
      }
      const last = history.pop();
      board[last.i] = '';
      // set current to the player who would move next
      current = last.player === 'X' ? 'X' : 'O';
      messageEl.textContent = `Undid last move. ${current}'s turn.`;
      refreshUI();
    }

    // Keyboard support (numpad-like mapping)
    // We'll map: 7 8 9
    //           4 5 6  -> indices 0..8 are top-left to bottom-right: but common numpad is 7 top-left. We'll map 1 bottom-left to 9 top-right for simpler mental model mentioned in README.
    const keyMap = {
      '1':6, '2':7, '3':8,
      '4':3, '5':4, '6':5,
      '7':0, '8':1, '9':2
    };

    window.addEventListener('keydown', (e)=>{
      if(e.target.tagName==='INPUT' || e.target.tagName==='TEXTAREA') return;
      if(e.key in keyMap){
        const i = keyMap[e.key];
        const cell = boardEl.querySelector(`[data-i='${i}']`);
        if(cell) cell.click();
      } else if(e.key==='n' || e.key==='N') newGame();
      else if(e.key==='u' || e.key==='U') undo();
      else if(e.key==='s' || e.key==='S') swapStart();
    });

    // Buttons
    newBtn.addEventListener('click', newGame);
    swapBtn.addEventListener('click', swapStart);
    undoBtn.addEventListener('click', undo);

    // init
    messageEl.textContent = `Ready — ${current} begins.`;
    refreshUI();

  </script>
</body>
</html>
