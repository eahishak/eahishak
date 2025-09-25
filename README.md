<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover" />
  <title>Emmanuel Ahishakiye</title>
  <meta name="theme-color" content="#000000" />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=JetBrains+Mono:wght@400;600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --brand:#03cb87;
      --bg:#000000;
      --bg2:#0a0a0a;
      --card:#0f1115;
      --text:#e6f2ec;
      --muted:#9fb4ac;
      --ring:rgba(3,203,135,.55);
      --glass:rgba(255,255,255,.08);
      --white:#ffffff;
      --shadow:0 20px 60px rgba(0,0,0,.45);
      --radius:18px;
      --wrap:1200px;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      color:var(--text);
      font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,Helvetica,Arial,sans-serif;
      background:radial-gradient(1200px 600px at 20% -10%, rgba(3,203,135,.15), transparent),
                 radial-gradient(900px 500px at 85% 10%, rgba(255,255,255,.06), transparent),
                 linear-gradient(180deg, var(--bg), var(--bg2));
      overflow-x:hidden;
    }
    a{color:inherit;text-decoration:none}
    .wrap{max-width:var(--wrap);margin:0 auto;padding:24px}

    /* Header */
    .nav{position:sticky;top:0;z-index:50;background:linear-gradient(180deg, rgba(0,0,0,.75), rgba(0,0,0,0));backdrop-filter:saturate(140%) blur(8px)}
    .navInner{display:flex;align-items:center;gap:16px;padding:16px 24px}
    .brand{
      display:flex;align-items:center;gap:12px;font-weight:800;letter-spacing:.3px
    }
    .logo{width:36px;height:36px;border-radius:12px;background:conic-gradient(from 90deg at 50% 50%, rgba(3,203,135,.35), rgba(3,203,135,1), rgba(3,203,135,.35));box-shadow:0 0 0 2px rgba(255,255,255,.08), 0 8px 30px rgba(3,203,135,.35)}
    .brandName{font-size:18px}
    .spacer{flex:1}
    .navBtn{padding:10px 14px;border-radius:12px;background:rgba(255,255,255,.06);border:1px solid rgba(255,255,255,.08)}
    .cta{padding:12px 16px;border-radius:12px;background:var(--brand);color:#00140c;font-weight:700;box-shadow:0 10px 30px rgba(3,203,135,.35)}

    /* Hero */
    .hero{padding:64px 24px 24px}
    .heroGrid{display:grid;grid-template-columns:1.3fr .7fr;gap:28px;align-items:center}
    .title{font-size:64px;line-height:1.02;margin:0 0 12px;font-weight:900;letter-spacing:-.6px}
    .title span{color:var(--brand);text-shadow:0 8px 40px rgba(3,203,135,.25)}
    .subtitle{font-size:20px;color:var(--muted);max-width:720px}
    .heroCard{border:1px solid rgba(255,255,255,.08);background:linear-gradient(180deg, rgba(255,255,255,.06), rgba(255,255,255,.02));border-radius:20px;padding:18px;box-shadow:var(--shadow)}
    .metricRow{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-top:16px}
    .metric{padding:16px;border:1px solid rgba(255,255,255,.08);border-radius:16px;background:rgba(255,255,255,.04)}
    .metric .num{font-size:28px;font-weight:800}
    .metric .cap{font-size:12px;color:var(--muted)}

    /* Cards */
    .section{padding:42px 24px}
    .sectionHeader{display:flex;align-items:end;gap:12px;margin-bottom:18px}
    .h2{font-size:28px;font-weight:800;margin:0}
    .fade{color:var(--muted)}
    .grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}
    .card{position:relative;border:1px solid rgba(255,255,255,.08);border-radius:18px;background:linear-gradient(160deg, rgba(255,255,255,.06), rgba(255,255,255,.02));box-shadow:var(--shadow);overflow:hidden}
    .cardInner{padding:18px}
    .chip{display:inline-block;padding:6px 10px;border-radius:999px;background:rgba(3,203,135,.12);border:1px solid rgba(3,203,135,.35);color:var(--brand);font-size:12px;font-weight:700;margin-bottom:10px}
    .cardTitle{font-size:18px;font-weight:800;margin:6px 0}
    .cardText{font-size:14px;color:var(--muted)}
    .cardFoot{display:flex;gap:10px;margin-top:14px}
    .ghostBtn{padding:10px 12px;border-radius:12px;background:rgba(255,255,255,.06);border:1px solid rgba(255,255,255,.12)}

    .statImg{width:100%;height:140px;border-radius:14px;border:1px solid rgba(255,255,255,.08);background:#0b0d12;display:flex;align-items:center;justify-content:center;overflow:hidden}
    .statImg img{width:100%;height:100%;object-fit:cover}

    /* Experience timeline */
    .timeline{position:relative;margin-top:4px}
    .line{position:absolute;left:13px;top:0;bottom:0;width:2px;background:linear-gradient(180deg, rgba(3,203,135,.35), transparent)}
    .item{display:grid;grid-template-columns:28px 1fr;gap:14px;padding:12px 0}
    .dot{width:12px;height:12px;border-radius:999px;background:var(--brand);box-shadow:0 0 0 4px rgba(3,203,135,.15)}
    .role{font-weight:800}
    .time{font-size:12px;color:var(--muted)}

    /* Skills */
    .skillWrap{display:flex;flex-wrap:wrap;gap:10px}
    .skill{padding:10px 12px;border-radius:12px;border:1px solid rgba(255,255,255,.10);background:rgba(255,255,255,.04);font-weight:600}

    /* Footer */
    .footer{padding:24px;border-top:1px solid rgba(255,255,255,.08);display:flex;gap:12px;align-items:center;justify-content:space-between;color:var(--muted)}

    /* Toys */
    .shine{position:absolute;inset:0;background:radial-gradient(400px 200px at var(--mx,50%) var(--my,50%), rgba(3,203,135,.14), rgba(3,203,135,0));pointer-events:none}
    .glow{filter:drop-shadow(0 20px 80px rgba(3,203,135,.35))}

    /* Responsive */
    @media (max-width:980px){
      .heroGrid{grid-template-columns:1fr}
      .grid{grid-template-columns:1fr 1fr}
      .title{font-size:46px}
    }
    @media (max-width:620px){
      .grid{grid-template-columns:1fr}
      .metricRow{grid-template-columns:1fr 1fr}
      .title{font-size:38px}
    }
  </style>
</head>
<body>
  <header class="nav">
    <div class="navInner wrap">
      <div class="brand">
        <div class="logo glow"></div>
        <div class="brandName">Emmanuel Ahishakiye</div>
      </div>
      <div class="spacer"></div>
      <a class="navBtn" href="#projects">Projects</a>
      <a class="navBtn" href="#experience">Experience</a>
      <a class="navBtn" href="#skills">Skills</a>
      <a class="navBtn" href="#contact">Contact</a>
      <a class="cta" href="doc/resume/Emmanuel_Ahishakiye_Resume.pdf" target="_blank" rel="noopener">Resume</a>
    </div>
  </header>

  <main>
    <!-- Hero -->
    <section class="hero wrap">
      <div class="heroGrid">
        <div>
          <h1 class="title">I build useful software with a <span>clear</span> focus on results</h1>
          <p class="subtitle">Product minded. Detail driven. Comfortable across the stack. I like clean interfaces, crisp data workflows, and results you can measure.</p>
          <div style="display:flex;gap:12px;margin-top:18px">
            <a class="cta" href="https://calendly.com/eahishak" target="_blank" rel="noopener">Book time</a>
            <a class="ghostBtn" href="https://eahishakiye.com" target="_blank" rel="noopener">Live site</a>
            <a class="ghostBtn" href="https://github.com/eahishak" target="_blank" rel="noopener">GitHub</a>
          </div>
          <div class="metricRow">
            <div class="metric">
              <div class="num" id="starsNum">0</div>
              <div class="cap">GitHub stars across work</div>
            </div>
            <div class="metric">
              <div class="num" id="projectsNum">0</div>
              <div class="cap">Public projects</div>
            </div>
            <div class="metric">
              <div class="num" id="streakNum">0</div>
              <div class="cap">Day streak best</div>
            </div>
          </div>
        </div>
        <div class="heroCard">
          <div class="statImg">
            <img alt="GitHub Stats" src="https://github-readme-stats.vercel.app/api?username=eahishak&show_icons=true&theme=radical&include_all_commits=true&count_private=true&custom_title=GitHub%20Stats&line_height=30"/>
          </div>
          <div style="height:10px"></div>
          <div class="statImg">
            <img alt="Top Langs" src="https://github-readme-stats.vercel.app/api/top-langs/?username=eahishak&layout=compact&theme=radical&langs_count=10"/>
          </div>
          <div style="height:10px"></div>
          <div class="statImg">
            <img alt="GitHub Streak" src="https://github-readme-streak-stats.herokuapp.com/?user=eahishak&theme=radical"/>
          </div>
        </div>
      </div>
    </section>

    <!-- Experience -->
    <section id="experience" class="section wrap">
      <div class="sectionHeader">
        <h2 class="h2">Experience snapshots</h2>
        <div class="fade">Highlights that matter</div>
      </div>
      <div class="card">
        <div class="shine"></div>
        <div class="cardInner">
          <div class="timeline">
            <div class="line"></div>

            <div class="item">
              <div class="dot"></div>
              <div>
                <div class="role">Foundly • Software Developer</div>
                <div class="time">Jan 2025 to present</div>
                <div class="cardText">React and Node with Firebase. Secure sign in with Google and campus logic. Maps and geolocation for faster item recovery. Matching services in Python with TensorFlow.</div>
              </div>
            </div>

            <div class="item">
              <div class="dot"></div>
              <div>
                <div class="role">Cendance Systems Inc • Salesforce Software Engineer Intern</div>
                <div class="time">Dec 2024 to May 2025</div>
                <div class="cardText">Microservices that improved forecast accuracy by 35. Internal React tools that increased engagement by 25.</div>
              </div>
            </div>

            <div class="item">
              <div class="dot"></div>
              <div>
                <div class="role">Jackal Tech Ltd • Founder and Product Lead part time</div>
                <div class="time">Nov 2021 to present</div>
                <div class="cardText">Six products shipped in health education and civic tech. Scalable back ends in Django and Node. Chat features that cut response times. Mentored builders through sprints and live sessions.</div>
              </div>
            </div>

            <div class="item">
              <div class="dot"></div>
              <div>
                <div class="role">Headstarter • Software Engineer Fellow</div>
                <div class="time">Jun 2024 to Oct 2024</div>
                <div class="cardText">Sign in systems and chat interfaces. Better deployment flows with higher reliability.</div>
              </div>
            </div>

          </div>
        </div>
      </div>
    </section>

    <!-- Projects -->
    <section id="projects" class="section wrap">
      <div class="sectionHeader">
        <h2 class="h2">Projects</h2>
        <div class="fade">Real work you can open</div>
      </div>
      <div class="grid">
        <article class="card">
          <div class="shine"></div>
          <div class="cardInner">
            <span class="chip">Real time</span>
            <h3 class="cardTitle">Weather App</h3>
            <p class="cardText">Forecasts and alerts with a clean map view.</p>
            <div class="cardFoot">
              <a class="ghostBtn" href="https://github.com/eahishak/weather-app" target="_blank" rel="noopener">Code</a>
            </div>
          </div>
        </article>
        <article class="card">
          <div class="shine"></div>
          <div class="cardInner">
            <span class="chip">Media</span>
            <h3 class="cardTitle">Marvel Streams</h3>
            <p class="cardText">Media viewer with smooth browsing.</p>
            <div class="cardFoot">
              <a class="ghostBtn" href="https://github.com/eahishak/marvel-streams" target="_blank" rel="noopener">Code</a>
            </div>
          </div>
        </article>
        <article class="card">
          <div class="shine"></div>
          <div class="cardInner">
            <span class="chip">Platform</span>
            <h3 class="cardTitle">Jackal Tech Web App</h3>
            <p class="cardText">Public platform for Jackal Tech.</p>
            <div class="cardFoot">
              <a class="ghostBtn" href="https://github.com/eahishak/jackal-tech-web" target="_blank" rel="noopener">Code</a>
            </div>
          </div>
        </article>
        <article class="card">
          <div class="shine"></div>
          <div class="cardInner">
            <span class="chip">Community</span>
            <h3 class="cardTitle">Afriverse</h3>
            <p class="cardText">Digital spaces for culture and makers.</p>
            <div class="cardFoot">
              <a class="ghostBtn" href="https://github.com/eahishak/afriverse" target="_blank" rel="noopener">Code</a>
            </div>
          </div>
        </article>
        <article class="card">
          <div class="shine"></div>
          <div class="cardInner">
            <span class="chip">Product</span>
            <h3 class="cardTitle">Foundly</h3>
            <p class="cardText">Smart lost and found for campuses and offices.</p>
            <div class="cardFoot">
              <a class="ghostBtn" href="https://foundlyhq.com" target="_blank" rel="noopener">Site</a>
            </div>
          </div>
        </article>
        <article class="card">
          <div class="shine"></div>
          <div class="cardInner">
            <span class="chip">Studio</span>
            <h3 class="cardTitle">Magic lab • Game studio</h3>
            <p class="cardText">Quick browser games. Good for a short break during an interview loop.</p>
            <div class="cardFoot">
              <a class="ghostBtn" href="https://eahishakiye.com#lab=games&g=twf&lang=en" target="_blank" rel="noopener">Open</a>
            </div>
          </div>
        </article>
      </div>
    </section>

    <!-- Education -->
    <section class="section wrap">
      <div class="sectionHeader">
        <h2 class="h2">Education</h2>
        <div class="fade">University of Rochester • Class of 2027</div>
      </div>
      <div class="card">
        <div class="shine"></div>
        <div class="cardInner">
          <div style="display:grid;grid-template-columns:1fr 1fr;gap:16px">
            <div>
              <div class="role">B Sc in Computer Science and Business</div>
              <div class="cardText">Relevant coursework</div>
              <ul class="cardText">
                <li>Data Structures and Algorithms</li>
                <li>Human Computer Interaction</li>
                <li>Artificial Intelligence</li>
                <li>Formal Systems</li>
                <li>Discrete Math</li>
                <li>Financial Accounting</li>
                <li>Statistical Methodology</li>
              </ul>
            </div>
            <div>
              <div class="role">Companies</div>
              <div class="cardText">Work and sites</div>
              <ul class="cardText">
                <li>Foundly • <a href="https://foundlyhq.com" target="_blank" rel="noopener">foundlyhq.com</a></li>
                <li>Jackal Tech Ltd • <a href="https://jackaltechltd.com" target="_blank" rel="noopener">jackaltechltd.com</a></li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills -->
    <section id="skills" class="section wrap">
      <div class="sectionHeader">
        <h2 class="h2">Skills focus</h2>
        <div class="fade">What I use often</div>
      </div>
      <div class="card">
        <div class="shine"></div>
        <div class="cardInner">
          <div style="display:grid;grid-template-columns:1fr 1fr 1fr;gap:16px">
            <div>
              <div class="role">Languages</div>
              <div class="skillWrap">
                <span class="skill">Python</span><span class="skill">Java</span><span class="skill">JavaScript</span><span class="skill">TypeScript</span><span class="skill">C++</span>
              </div>
            </div>
            <div>
              <div class="role">Frameworks</div>
              <div class="skillWrap">
                <span class="skill">React</span><span class="skill">Node.js</span><span class="skill">Django</span><span class="skill">FastAPI</span>
              </div>
            </div>
            <div>
              <div class="role">Data</div>
              <div class="skillWrap">
                <span class="skill">PostgreSQL</span><span class="skill">MySQL</span><span class="skill">Firebase</span><span class="skill">Supabase</span>
              </div>
            </div>
          </div>
          <div style="height:12px"></div>
          <div>
            <div class="role">Cloud and tools</div>
            <div class="skillWrap">
              <span class="skill">AWS</span><span class="skill">Git</span><span class="skill">Docker</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Stats strip -->
    <section class="section wrap">
      <div class="grid">
        <div class="card">
          <div class="shine"></div>
          <div class="cardInner">
            <div class="cardTitle">Live stats</div>
            <div class="cardText">Pulled from public endpoints at load time.</div>
            <div id="liveStats" class="skillWrap"></div>
          </div>
        </div>
        <div class="card">
          <div class="shine"></div>
          <div class="cardInner">
            <div class="cardTitle">Try a quick game</div>
            <div class="cardText">Open Magic lab then Game studio. You can deep link with a language and a game.</div>
            <a class="ghostBtn" href="https://eahishakiye.com#lab=games&g=twf&lang=en" target="_blank" rel="noopener">Open Magic lab</a>
          </div>
        </div>
        <div class="card">
          <div class="shine"></div>
          <div class="cardInner">
            <div class="cardTitle">How to run locally</div>
            <pre style="margin:10px 0;padding:12px;border-radius:12px;border:1px solid rgba(255,255,255,.10);background:#0a0d11;color:#cde6dd;overflow:auto"><code>git clone https://github.com/eahishak/emmanuel-ahishakiye.git
cd emmanuel-ahishakiye
python -m http.server
# open http://localhost:8000</code></pre>
            <a class="ghostBtn" href="https://github.com/eahishak/emmanuel-ahishakiye" target="_blank" rel="noopener">Repository</a>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact -->
    <section id="contact" class="section wrap">
      <div class="sectionHeader">
        <h2 class="h2">Contact</h2>
        <div class="fade">I reply fast</div>
      </div>
      <div class="card">
        <div class="shine"></div>
        <div class="cardInner" style="display:grid;grid-template-columns:1.2fr .8fr;gap:16px;align-items:center">
          <div>
            <div class="role">Links</div>
            <div class="skillWrap">
              <a class="skill" href="mailto:eahishak@u.rochester.edu">eahishak@u.rochester.edu</a>
              <a class="skill" href="https://linkedin.com/in/eahishak" target="_blank" rel="noopener">LinkedIn</a>
              <a class="skill" href="https://github.com/eahishak" target="_blank" rel="noopener">GitHub</a>
              <a class="skill" href="https://eahishakiye.com" target="_blank" rel="noopener">Website</a>
            </div>
          </div>
          <div style="display:flex;gap:12px;justify-content:end">
            <a class="ghostBtn" href="https://calendly.com/eahishak" target="_blank" rel="noopener">Calendly</a>
            <a class="cta" href="doc/resume/Emmanuel_Ahishakiye_Resume.pdf" target="_blank" rel="noopener">Resume</a>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer class="footer wrap">
    <span>© <span id="year"></span> Emmanuel Ahishakiye</span>
    <span>Built with care in plain HTML CSS JS</span>
  </footer>

  <script>
    // Motion shine for hover
    const cards = document.querySelectorAll('.card');
    cards.forEach(c=>{
      const s = c.querySelector('.shine');
      c.addEventListener('pointermove',e=>{
        const r = c.getBoundingClientRect();
        const x = ((e.clientX - r.left) / r.width) * 100;
        const y = ((e.clientY - r.top) / r.height) * 100;
        s.style.setProperty('--mx', x + '%');
        s.style.setProperty('--my', y + '%');
      });
    });

    // Live GitHub mini fetch for counts
    async function loadGit(){
      try{
        const u = await fetch('https://api.github.com/users/eahishak');
        const d = await u.json();
        const r = await fetch('https://api.github.com/users/eahishak/repos?per_page=100');
        const repos = await r.json();
        const stars = repos.reduce((a,b)=>a + (b.stargazers_count||0),0);
        document.getElementById('starsNum').textContent = stars.toLocaleString();
        document.getElementById('projectsNum').textContent = repos.length.toLocaleString();
        // best guess streak not available directly, show followers as social proof
        document.getElementById('streakNum').textContent = (d.followers||0).toLocaleString();
        const live = document.getElementById('liveStats');
        live.innerHTML = '';
        const bits = [
          ['Followers', d.followers],
          ['Following', d.following],
          ['Public repos', d.public_repos],
          ['Public gists', d.public_gists]
        ];
        bits.forEach(([k,v])=>{
          const el = document.createElement('span');
          el.className = 'skill';
          el.textContent = k + ': ' + (v||0);
          live.appendChild(el);
        });
      }catch(e){/* silent */}
    }
    loadGit();

    // Year
    document.getElementById('year').textContent = new Date().getFullYear();

    // Keyboard toy
    let keyPool = '';
    const magic = 'magic';
    window.addEventListener('keydown', e=>{
      keyPool += e.key.toLowerCase();
      if(keyPool.length > 8) keyPool = keyPool.slice(-8);
      if(keyPool.includes(magic)){
        document.body.animate([
          {filter:'saturate(100%)'},
          {filter:'saturate(400%)'},
          {filter:'saturate(100%)'}
        ], {duration:800, easing:'ease-out'});
      }
    });
  </script>
</body>
</html>
