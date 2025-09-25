<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Sign in · GitHub</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#0b1220; /* deep navy */
      --card:#0f1724;
      --muted:#9aa4b2;
      --accent:#2ea44f; /* github green */
      --glass: rgba(255,255,255,0.03);
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background: linear-gradient(180deg, #08101a 0%, #071022 50%, #02111b 100%);
      color:#e6eef6;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      display:flex;
      align-items:center;
      justify-content:center;
      padding:48px 16px;
    }

    .container{
      width:100%;
      max-width:980px;
      display:grid;
      grid-template-columns: 420px 1fr;
      gap:32px;
      align-items:center;
    }

    /* Left card (form) */
    .card{
      background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:12px;
      padding:28px;
      box-shadow: 0 6px 30px rgba(2,6,23,0.6);
      border:1px solid rgba(255,255,255,0.03);
    }

    .brand{
      display:flex;
      gap:12px;
      align-items:center;
      margin-bottom:8px;
    }
    .logo{
      width:40px;height:40px;border-radius:8px;background:linear-gradient(135deg,#24292e,#0f1724);display:grid;place-items:center;font-weight:700;font-size:18px;color:#fff;
      box-shadow: inset 0 -6px 18px rgba(0,0,0,0.6);
      border:1px solid rgba(255,255,255,0.03);
    }
    h1{margin:0;font-size:20px}
    p.lead{color:var(--muted);margin-top:8px;margin-bottom:18px}

    form{display:flex;flex-direction:column;gap:12px}

    label{font-size:13px;color:var(--muted);margin-bottom:6px;display:block}
    input[type=text], input[type=password] {
      width:100%;
      padding:12px 14px;
      border-radius:8px;
      border:1px solid rgba(255,255,255,0.04);
      background:var(--glass);
      color:inherit;
      outline:none;
      font-size:14px;
    }
    input:focus{box-shadow:0 0 0 4px rgba(46,164,79,0.08);border-color:rgba(46,164,79,0.9)}

    .row{display:flex;gap:12px;align-items:center}
    .remember{display:flex;gap:8px;align-items:center;color:var(--muted);font-size:14px}
    .btn{
      padding:10px 14px;border-radius:8px;border:0;background:var(--accent);color:#fff;font-weight:600;font-size:15px;cursor:pointer;
      box-shadow:0 6px 18px rgba(46,164,79,0.12);
    }
    .btn.secondary{background:transparent;border:1px solid rgba(255,255,255,0.06);color:var(--muted);font-weight:600}

    .links{display:flex;justify-content:space-between;align-items:center;margin-top:6px}
    a{color:inherit;text-decoration:none}
    a.ghost{color:var(--muted)}

    .alt-login{display:flex;flex-direction:column;gap:8px;margin-top:8px}
    .social{
      display:flex;gap:8px
    }
    .social button{flex:1;padding:9px;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:var(--muted);font-weight:600}

    /* right column: promo */
    .promo{
      padding:28px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.005));border:1px solid rgba(255,255,255,0.02);
      display:flex;flex-direction:column;gap:12px;align-items:flex-start;justify-content:center;min-height:260px
    }
    .promo h2{margin:0;font-size:18px}
    .promo p{margin:0;color:var(--muted)}

    .footer{margin-top:18px;color:var(--muted);font-size:13px}

    /* responsiveness */
    @media (max-width:880px){
      .container{grid-template-columns:1fr;max-width:520px}
      .promo{order:2}
    }
  </style>
</head>
<body>
  <main class="container" aria-labelledby="signin-title">
    <section class="card" aria-label="Sign in">
      <div class="brand">
        <div class="logo">GH</div>
        <div>
          <h1 id="signin-title">Sign in to GitHub</h1>
          <p class="lead">Enter your credentials to access your account.</p>
        </div>
      </div>

      <form id="signinForm" autocomplete="on" novalidate>
        <div>
          <label for="input-username">Username or email address</label>
          <input id="input-username" name="username" type="text" placeholder="your-username or email@example.com" required>
        </div>

        <div>
          <label for="input-password">Password</label>
          <input id="input-password" name="password" type="password" placeholder="Enter your password" minlength="6" required>
        </div>

        <div class="row" style="justify-content:space-between;align-items:center;margin-top:6px">
          <label class="remember"><input id="remember" type="checkbox"> Remember me</label>
          <a href="#" class="ghost">Forgot password?</a>
        </div>

        <div style="display:flex;gap:10px;margin-top:6px">
          <button class="btn" type="submit">Sign in</button>
          <button type="button" class="btn secondary" onclick="fillDemo()">Use demo</button>
        </div>

        <div class="alt-login">
          <div style="text-align:center;color:var(--muted);font-size:13px;margin-top:6px">Or continue with</div>
          <div class="social">
            <button type="button" onclick="alert('Pretend logging in with GitHub OAuth')">Continue with GitHub</button>
            <button type="button" onclick="alert('Pretend logging in with Google')">Continue with Google</button>
          </div>
        </div>

        <div class="footer">New to GitHub? <a href="#">Create an account</a></div>
      </form>
    </section>

    <aside class="promo" aria-hidden="false">
      <h2>Work faster, together</h2>
      <p>Collaborate on repositories, track issues, and ship code with confidence. Secure, fast, and trusted by millions.</p>
      <ul style="margin-top:12px;color:var(--muted);">
        <li>Two-factor authentication support</li>
        <li>SSH key management</li>
        <li>Organizations & teams</li>
      </ul>
    </aside>
  </main>

  <script>
    const form = document.getElementById('signinForm');
    form.addEventListener('submit', function(e){
      e.preventDefault();
      const username = document.getElementById('input-username').value.trim();
      const password = document.getElementById('input-password').value;

      // basic validation
      if(!username){
        alert('Please enter username or email');
        return;
      }
      if(!password || password.length < 6){
        alert('Password must be at least 6 characters');
        return;
      }

      // demo behavior: simulate success
      // NOTE: never collect or send real credentials — this is a static demo.
      document.querySelector('.btn').textContent = 'Signing in...';
      setTimeout(()=>{
        document.querySelector('.btn').textContent = 'Sign in';
        alert('Signed in (demo). To make this functional, wire up an auth backend or GitHub OAuth flow.');
      }, 900);
    });

    function fillDemo(){
      document.getElementById('input-username').value = 'octocat';
      document.getElementById('input-password').value = 'password123';
    }
  </script>
</body>
</html>
