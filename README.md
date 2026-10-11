# klass-konekte
Plateforme éducative pour les élèves
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Klass Konekte | Apprenons ensemble</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: 'Segoe UI', Arial, sans-serif;
      background: #f3f6fc;
      color: #243247;
      line-height: 1.6;
    }
    header {
      background: white;
      padding: 18px 6%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 12px;
      box-shadow: 0 2px 10px #142b4a12;
    }
    .logo { font-size: 23px; font-weight: bold; color: #142b4a; }
    .logo span { color: #00a5b5; }
    button, .btn {
      border: 0;
      border-radius: 8px;
      padding: 11px 16px;
      font-size: 15px;
      font-weight: bold;
      cursor: pointer;
      text-decoration: none;
      display: inline-block;
      font-family: inherit;
    }
    .primary { background: #00a5b5; color: white; }
    .outline { background: white; color: #00a5b5; border: 1px solid #00a5b5; }
    .hero {
      text-align: center;
      padding: 75px 20px;
      background: linear-gradient(135deg, #e0f7fa, #f8fbff);
    }
    .tag {
      display: inline-block;
      background: #d0f0f3;
      color: #007a87;
      padding: 6px 13px;
      border-radius: 25px;
      margin-bottom: 18px;
      font-size: 13px;
    }
    h1 { font-size: clamp(34px, 6vw, 52px); color: #142b4a; line-height: 1.2; }
    .hero p { max-width: 650px; margin: 20px auto; color: #53647b; font-size: 18px; }
    .actions { display: flex; justify-content: center; gap: 12px; flex-wrap: wrap; }
    section { padding: 50px 6%; }
    h2 { text-align: center; color: #142b4a; margin-bottom: 12px; font-size: 29px; }
    .description { text-align: center; max-width: 650px; margin: 0 auto 30px; color: #64748b; }
    .features {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 20px;
      max-width: 1100px;
      margin: auto;
    }
    .card {
      background: white;
      border: 1px solid #e5eaf3;
      border-radius: 14px;
      padding: 24px;
    }
    .card .icon { font-size: 30px; }
    .card h3 { color: #142b4a; margin: 10px 0; }
    .card p { color: #64748b; }
    .community { background: white; text-align: center; }
    .community-box {
      max-width: 750px;
      margin: auto;
      padding: 25px;
      border-radius: 14px;
      background: #f3f6fc;
    }
    .community-box p { margin: 12px 0; }
    .reward { background: #effcf3; }
    footer { background: #142b4a; color: white; text-align: center; padding: 30px 15px; }
    footer p { margin-top: 8px; color: #d6e0ef; }
    #userInfo {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-size: 14px;
      color: #142b4a;
      margin-left: 8px;
      flex-wrap: wrap;
    }
    .auth-modal {
      display: none;
      position: fixed;
      inset: 0;
      background: linear-gradient(135deg, #d4f5f8, #f3f6fc);
      z-index: 9999;
      align-items: center;
      justify-content: center;
      padding: 20px;
      overflow-y: auto;
    }
    .auth-modal.open { display: flex; }
    .auth-container {
      background: white;
      width: 100%;
      max-width: 900px;
      min-height: 500px;
      border-radius: 24px;
      box-shadow: 0 25px 70px rgba(0, 122, 135, 0.2);
      display: flex;
      overflow: hidden;
      position: relative;
    }
    .auth-panel {
      width: 45%;
      background: linear-gradient(135deg, #00c9d4, #007a87);
      color: white;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: 40px 30px;
      text-align: center;
      border-radius: 0 60% 60% 0 / 0 50% 50% 0;
      position: relative;
      z-index: 2;
    }
    .auth-panel h2 { color: white; font-size: 32px; margin-bottom: 10px; text-align: center; }
    .auth-panel p { font-size: 14px; opacity: 0.9; margin-bottom: 22px; }
    .auth-panel button {
      background: transparent;
      color: white;
      border: 2px solid white;
      padding: 11px 32px;
      border-radius: 30px;
      font-weight: bold;
      font-size: 15px;
      cursor: pointer;
      transition: all 0.3s;
    }
    .auth-panel button:hover { background: white; color: #007a87; }
    .auth-form-box { flex: 1; padding: 50px 45px; display: flex; flex-direction: column; justify-content: center; }
    .auth-form-box h2 { text-align: center; color: #142b4a; font-size: 30px; margin-bottom: 30px; }
    .input-group { position: relative; margin-bottom: 18px; }
    .input-group input {
      width: 100%;
      padding: 14px 45px 14px 18px;
      border: 1px solid #e0e6ef;
      background: #f7f9fc;
      border-radius: 12px;
      font-size: 15px;
      font-family: inherit;
      transition: all 0.2s;
    }
    .input-group input:focus { outline: none; border-color: #00a5b5; background: white; }
    .input-group .input-icon {
      position: absolute;
      right: 16px;
      top: 50%;
      transform: translateY(-50%);
      font-size: 17px;
      color: #94a3b8;
      pointer-events: none;
    }
    .forgot-link {
      display: block;
      text-align: right;
      color: #64748b;
      font-size: 13px;
      margin-bottom: 18px;
      cursor: pointer;
    }
    .forgot-link:hover { color: #00a5b5; }
    .auth-error { color: #dc2626; font-size: 14px; margin: 0 0 12px; min-height: 18px; text-align: center; }
    .auth-success { color: #16a34a; font-size: 14px; margin: 0 0 12px; min-height: 18px; text-align: center; }
    .submit-btn {
      background: linear-gradient(135deg, #00c9d4, #007a87);
      color: white;
      width: 100%;
      padding: 14px;
      border-radius: 30px;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      border: 0;
      transition: transform 0.2s, box-shadow 0.2s;
    }
    .submit-btn:hover { transform: translateY(-1px); box-shadow: 0 8px 20px rgba(0, 165, 181, 0.3); }
    .social-divider { text-align: center; color: #94a3b8; font-size: 13px; margin: 22px 0 16px; }
    .social-buttons { display: flex; justify-content: center; gap: 12px; }
    .social-buttons button {
      width: 46px;
      height: 46px;
      border-radius: 12px;
      border: 1px solid #e0e6ef;
      background: white;
      font-size: 20px;
      font-weight: bold;
      cursor: pointer;
      color: #142b4a;
      transition: all 0.2s;
    }
    .social-buttons button:hover { border-color: #00a5b5; color: #00a5b5; transform: translateY(-1px); }
    .close-btn {
      position: absolute;
      top: 16px;
      right: 20px;
      font-size: 28px;
      cursor: pointer;
      color: #64748b;
      line-height: 1;
      z-index: 10;
      background: transparent;
      border: 0;
      padding: 4px 8px;
      border-radius: 50%;
      transition: background 0.2s;
    }
    .close-btn:hover { color: #142b4a; background: #f3f6fc; }
    .profile-modal {
      display: none;
      position: fixed;
      inset: 0;
      background: #142b4a99;
      z-index: 10000;
      align-items: center;
      justify-content: center;
      padding: 20px;
    }
    .profile-modal.open { display: flex; }
    .profile-box {
      background: white;
      border-radius: 14px;
      padding: 28px;
      max-width: 400px;
      width: 100%;
      position: relative;
      box-shadow: 0 20px 60px #142b4a40;
    }
    .profile-box h2 { text-align: left; margin-bottom: 16px; color: #142b4a; font-size: 22px; }
    .profile-box input {
      width: 100%;
      padding: 12px;
      margin-bottom: 10px;
      border: 1px solid #d6dfec;
      border-radius: 8px;
      font-size: 15px;
      font-family: inherit;
    }
    .profile-box input:focus { outline: none; border-color: #00a5b5; }
    .profile-box button.primary { width: 100%; }
    .profile-close {
      position: absolute;
      top: 10px;
      right: 16px;
      font-size: 26px;
      cursor: pointer;
      color: #64748b;
      line-height: 1;
    }
    .discussion { background: #f8fafc; }
    .discussion-container { max-width: 800px; margin: auto; }
    .new-post-box {
      background: white;
      border-radius: 14px;
      padding: 24px;
      box-shadow: 0 4px 20px #142b4a0d;
      margin-bottom: 30px;
      border: 1px solid #e5eaf3;
    }
    .new-post-box h3 { color: #142b4a; margin-bottom: 14px; font-size: 18px; }
    .new-post-box input,
    .new-post-box textarea {
      width: 100%;
      padding: 12px 14px;
      margin-bottom: 12px;
      border: 1px solid #d6dfec;
      border-radius: 10px;
      font-size: 15px;
      font-family: inherit;
      background: #f7f9fc;
      transition: all 0.2s;
    }
    .new-post-box input:focus,
    .new-post-box textarea:focus { outline: none; border-color: #00a5b5; background: white; }
    .new-post-box textarea { min-height: 90px; resize: vertical; }
    .post-actions { display: flex; justify-content: space-between; align-items: center; gap: 12px; }
    .post-error { color: #dc2626; font-size: 14px; min-height: 18px; }
    .login-notice {
      background: #fff7ed;
      border: 1px solid #fed7aa;
      border-radius: 14px;
      padding: 20px;
      margin-bottom: 30px;
      text-align: center;
      color: #9a3412;
    }
    .login-notice button { margin-top: 12px; }
    .posts-list { display: flex; flex-direction: column; gap: 16px; }
    .post-card {
      background: white;
      border: 1px solid #e5eaf3;
      border-radius: 14px;
      padding: 22px;
      transition: box-shadow 0.2s;
    }
    .post-card:hover { box-shadow: 0 6px 24px #142b4a10; }
    .post-header { display: flex; justify-content: space-between; align-items: flex-start; gap: 12px; margin-bottom: 12px; flex-wrap: wrap; }
    .post-author { display: flex; align-items: center; gap: 10px; }
    .avatar {
      width: 42px;
      height: 42px;
      border-radius: 50%;
      background: linear-gradient(135deg, #00c9d4, #007a87);
      color: white;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      font-size: 18px;
      flex-shrink: 0;
    }
    .author-info { display: flex; flex-direction: column; }
    .author-name { font-weight: bold; color: #142b4a; font-size: 15px; }
    .author-meta { font-size: 12px; color: #94a3b8; }
    .post-date { font-size: 12px; color: #94a3b8; }
    .post-title { color: #142b4a; font-size: 18px; margin-bottom: 8px; font-weight: bold; }
    .post-content { color: #475569; font-size: 15px; margin-bottom: 14px; white-space: pre-wrap; word-wrap: break-word; }
    .post-footer { display: flex; justify-content: space-between; align-items: center; border-top: 1px solid #f1f5f9; padding-top: 12px; gap: 10px; flex-wrap: wrap; }
    .post-owner-actions { display: flex; gap: 8px; }
    .post-owner-actions button {
      padding: 6px 12px;
      font-size: 13px;
      border-radius: 6px;
      background: #fef2f2;
      color: #dc2626;
      border: 1px solid #fecaca;
      cursor: pointer;
    }
    .post-owner-actions button:hover { background: #fee2e2; }
    .empty-state {
      text-align: center;
      padding: 50px 20px;
      color: #94a3b8;
      background: white;
      border-radius: 14px;
      border: 1px dashed #cbd5e1;
    }
    .empty-state .icon { font-size: 40px; margin-bottom: 10px; }
    .avatar-btn { width:42px; height:42px; border-radius:50%; padding:0; background:linear-gradient(135deg,#00c9d4,#007a87); color:white; font-size:18px; display:inline-flex; align-items:center; justify-content:center; border:2px solid #d0f0f3; }
    .filters { display:flex; gap:8px; flex-wrap:wrap; justify-content:center; margin-bottom:22px; }
    .chip { background:white; color:#007a87; border:1px solid #cfe9ed; padding:7px 14px; border-radius:25px; font-size:13px; }
    .chip.active { background:#00a5b5; color:white; border-color:#00a5b5; }
    .class-badge { display:inline-block; background:#d0f0f3; color:#007a87; font-size:11px; padding:2px 9px; border-radius:20px; font-weight:bold; }
    .comments { border-top:1px solid #f1f5f9; margin-top:14px; padding-top:14px; }
    .comments-title { font-size:13px; color:#64748b; margin-bottom:10px; font-weight:bold; }
    .comment { display:flex; gap:10px; margin-bottom:12px; }
    .avatar.small { width:32px; height:32px; font-size:14px; }
    .comment-body { background:#f7f9fc; border-radius:12px; padding:10px 14px; flex:1; min-width:0; }
    .comment-head { font-size:13px; color:#142b4a; font-weight:bold; }
    .comment-head small { font-weight:normal; color:#94a3b8; margin-left:4px; }
    .comment-text { font-size:14px; color:#475569; white-space:pre-wrap; word-wrap:break-word; }
    .comment-actions { display:flex; gap:8px; margin-top:6px; flex-wrap:wrap; }
    .mini-btn { padding:4px 10px; font-size:12px; border-radius:20px; background:white; border:1px solid #d6dfec; color:#475569; cursor:pointer; }
    .mini-btn.on { background:#effcf3; border-color:#86efac; color:#15803d; }
    .mini-btn.del { color:#dc2626; border-color:#fecaca; background:#fef2f2; }
    .reply-row { display:flex; gap:8px; margin-top:6px; }
    .reply-row input { flex:1; min-width:0; padding:10px 12px; border:1px solid #d6dfec; border-radius:10px; font-size:14px; font-family:inherit; background:#f7f9fc; }
    .reply-row input:focus { outline:none; border-color:#00a5b5; background:white; }
    .reply-row button { padding:9px 14px; font-size:14px; }
    .reply-hint { font-size:13px; color:#94a3b8; }
    .profile-box select { width:100%; padding:12px; margin-bottom:10px; border:1px solid #d6dfec; border-radius:8px; font-size:15px; font-family:inherit; background:white; }
    .lb-wrap { max-width:600px; margin:auto; }
    .lb-row { display:flex; align-items:center; gap:12px; background:#f3f6fc; border:1px solid #e5eaf3; border-radius:12px; padding:12px 16px; margin-bottom:10px; text-align:left; }
    .lb-rank { font-size:22px; width:34px; text-align:center; }
    .lb-info { flex:1; min-width:0; }
    .lb-name { font-weight:bold; color:#142b4a; }
    .lb-meta { font-size:12px; color:#94a3b8; }
    .lb-points { font-weight:bold; color:#007a87; font-size:14px; white-space:nowrap; }
    .star { background:none; border:0; padding:0 1px; font-size:20px; color:#d6dfec; cursor:pointer; line-height:1; border-radius:0; }
    span.star { cursor:default; }
    .star.on { color:#fbbf24; }
    .star.mine { color:#f59e0b; }
    .rating-row { display:flex; align-items:center; gap:6px; flex-wrap:wrap; margin-top:6px; }
    .rating-text { font-size:12px; color:#64748b; }
    .correct-badge { background:#effcf3; color:#15803d; border:1px solid #86efac; font-size:12px; border-radius:20px; padding:2px 10px; font-weight:bold; }
    .comment.is-correct .comment-body { background:#effcf3; border:1px solid #bbf7d0; }
    .space-label { font-size:13px; color:#64748b; margin-bottom:12px; }
    .space-note { background:white; border:1px solid #cfe9ed; color:#007a87; border-radius:12px; padding:10px 14px; font-size:13px; text-align:center; margin-bottom:6px; }
    @media (max-width: 700px) {
      .auth-container { flex-direction: column; min-height: auto; }
      .auth-panel { width: 100%; border-radius: 0 0 40% 40% / 0 0 20% 20%; padding: 30px 20px; }
      .auth-panel h2 { font-size: 24px; }
      .auth-form-box { padding: 35px 25px; }
      .auth-form-box h2 { font-size: 24px; margin-bottom: 22px; }
    }
    @media (max-width: 500px) {
      header { justify-content: center; }
      .hero { padding: 50px 18px; }
      section { padding: 40px 5%; }
      .post-header { flex-direction: column; }
    }
  </style>
</head>
<body>
  <header>
    <div class="logo">Klass <span>Konekte</span></div>
    <div>
      <button class="outline" onclick="showMessage('Inscription')">S'inscrire</button>
      <button class="primary" onclick="showMessage('Connexion')">Se connecter</button>
    </div>
  </header>

  <main>
    <section class="hero">
      <span class="tag">La communauté éducative haïtienne</span>
      <h1>Apprenons ensemble, réussissons ensemble.</h1>
      <p>Pose tes questions, partage tes connaissances et aide les autres élèves à comprendre leurs cours.</p>
      <div class="actions">
        <button class="primary" onclick="showMessage('Inscription')">Rejoindre la communauté</button>
        <a href="#discussions" class="btn outline">Voir les discussions</a>
      </div>
    </section>

    <section id="fonctionnalites">
      <h2>Apprendre ensemble</h2>
      <p class="description">Un espace pour poser des questions, partager des cours et s'entraider.</p>
      <div class="features">
        <article class="card">
          <div class="icon">📚</div>
          <h3>Cours et devoirs</h3>
          <p>Partage tes notes et demande de l'aide pour tes exercices.</p>
        </article>
        <article class="card">
          <div class="icon">💬</div>
          <h3>Discussions</h3>
          <p>Échange avec les élèves de ta classe et d'autres établissements.</p>
        </article>
        <article class="card">
          <div class="icon">🤝</div>
          <h3>Entraide</h3>
          <p>Explique ce que tu comprends et aide tes camarades à progresser.</p>
        </article>
        <article class="card">
          <div class="icon">🏆</div>
          <h3>Récompenses</h3>
          <p>Cinq élèves pourront être récompensés chaque semaine dans chaque classe.</p>
        </article>
      </div>
    </section>

    <section class="discussion" id="discussions">
      <h2>💬 Discussions</h2>
      <p class="description">Pose tes questions, partage tes connaissances et aide les autres élèves.</p>
      <div class="discussion-container">
        <div class="filters" id="classFilters"></div>
        <div class="new-post-box" id="newPostBox" style="display:none;">
          <h3>✍️ Nouvelle publication</h3>
          <p class="space-label" id="spaceLabel"></p>
          <input type="text" id="postTitle" placeholder="Titre de ta question ou publication" maxlength="120">
          <textarea id="postContent" placeholder="Écris ton message ici... Explique bien ta question ou partage ton idée." maxlength="2000"></textarea>
          <div class="post-actions">
            <span class="post-error" id="postError"></span>
            <button class="primary" onclick="createPost()">Publier</button>
          </div>
        </div>
        <div class="login-notice" id="loginNotice">
          <strong>Connecte-toi pour participer aux discussions</strong>
          <p>Rejoins la communauté pour poser tes questions et aider les autres.</p>
          <button class="primary" onclick="showMessage('Connexion')">Se connecter</button>
        </div>
        <div class="posts-list" id="postsList">
          <div class="empty-state">
            <div class="icon">💭</div>
            <p>Chargement des discussions...</p>
          </div>
        </div>
      </div>
    </section>

    <section class="community">
      <h2>🏆 Classement de la semaine</h2>
      <p class="description">Les 5 élèves les plus utiles, dans la communauté générale et dans ta classe.</p>
      <div class="lb-wrap">
        <div class="filters" id="lbFilters"></div>
        <div id="lbList"></div>
      </div>
    </section>

    <section class="reward">
      <h2>Chaque classe compte</h2>
      <p class="description">1 réponse = 1 point · chaque étoile reçue = 1 point · réponse validée ✅ = +5 points. Le classement repart à zéro chaque lundi.</p>
    </section>
  </main>

  <footer>
    <div class="logo" style="color:white">Klass <span>Konekte</span></div>
    <p>Aprann ansanm, grandi ansanm.</p>
    <p>© <span id="year"></span> Klass Konekte</p>
  </footer>

  <div class="auth-modal" id="authModal">
    <div class="auth-container">
      <button class="close-btn" onclick="closeAuth()">×</button>
      <div class="auth-panel">
        <h2 id="panelTitle">Bonjour,<br>Bienvenue</h2>
        <p id="panelText">Vous n'avez pas de compte ?</p>
        <button onclick="switchAuth()" id="panelBtn">S'inscrire</button>
      </div>
      <div class="auth-form-box">
        <h2 id="authTitle">Se connecter</h2>
        <form onsubmit="event.preventDefault(); submitAuth();">
          <div class="input-group">
            <input type="email" id="authEmail" placeholder="Email" autocomplete="email">
            <span class="input-icon">✉</span>
          </div>
          <div class="input-group">
            <input type="password" id="authPassword" placeholder="Mot de passe" autocomplete="current-password">
            <span class="input-icon">🔒</span>
          </div>
        </form>
        <span class="forgot-link" id="forgotLink" onclick="resetPassword()">Mot de passe oublié ?</span>
        <p id="authError" class="auth-error"></p>
        <button class="submit-btn" id="authSubmit" onclick="submitAuth()">Se connecter</button>
        <p class="social-divider">ou connectez-vous avec</p>
        <div class="social-buttons">
          <button onclick="socialMsg('Google')">G</button>
          <button onclick="socialMsg('Facebook')">f</button>
          <button onclick="socialMsg('GitHub')">⌨</button>
          <button onclick="socialMsg('LinkedIn')">in</button>
        </div>
      </div>
    </div>
  </div>

  <div class="profile-modal" id="profileModal">
    <div class="profile-box">
      <span class="profile-close" onclick="closeProfile()">×</span>
      <h2>Mon profil</h2>
      <p style="color:#64748b; font-size:14px; margin-bottom:14px;">
        Complète tes informations pour rejoindre ta classe.
      </p>
      <input type="text" id="profileName" placeholder="Nom complet">
      <select id="profileClass"></select>
      <input type="text" id="profileSchool" placeholder="École">
      <p id="profileError" style="color:#dc2626; font-size:14px; margin: 4px 0 12px; min-height:18px;"></p>
      <button class="primary" onclick="saveProfile()">Enregistrer</button>
    </div>
  </div>

  <script src="https://www.gstatic.com/firebasejs/10.12.2/firebase-app-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.12.2/firebase-auth-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.12.2/firebase-firestore-compat.js"></script>
  <script>
    const firebaseConfig = {
      apiKey: "AIzaSyAvIWkk5fTSPtV_Y2_ZNDkNubvkZ-A6_pc",
      authDomain: "klass-konekte.firebaseapp.com",
      projectId: "klass-konekte",
      storageBucket: "klass-konekte.firebasestorage.app",
      messagingSenderId: "902584495528",
      appId: "1:902584495528:web:698d8c900316e3c0b5819d",
      measurementId: "G-BWW4KJT3NH"
    };

    firebase.initializeApp(firebaseConfig);
    const auth = firebase.auth();
    const db = firebase.firestore();

    let authMode = "login";
    let currentUserProfile = null;
    let currentUser = null;
    const CLASSES = ["7ème", "8ème", "9ème", "Seconde", "Rhéto", "Philo", "Université"];
    let currentSpace = "general";
    let lbTab = "general";
    let postsCache = [];
    let commentsCache = [];

    function showMessage(action) {
      if (action === "Inscription") {
        authMode = "signup";
        openAuth();
      } else if (action === "Connexion") {
        authMode = "login";
        openAuth();
      } else {
        alert(action + " sera disponible dans une prochaine version de Klass Konekte.");
      }
    }

    function openAuth() {
      updateAuthUI();
      document.getElementById("authError").textContent = "";
      document.getElementById("authError").className = "auth-error";
      document.getElementById("authEmail").value = "";
      document.getElementById("authPassword").value = "";
      document.getElementById("authModal").classList.add("open");
    }

    function closeAuth() {
      document.getElementById("authModal").classList.remove("open");
    }

    function switchAuth() {
      authMode = authMode === "signup" ? "login" : "signup";
      updateAuthUI();
    }

    function updateAuthUI() {
      const isSignup = authMode === "signup";
      document.getElementById("authTitle").textContent = isSignup ? "S'inscrire" : "Se connecter";
      document.getElementById("authSubmit").textContent = isSignup ? "S'inscrire" : "Se connecter";
      document.getElementById("panelTitle").innerHTML = isSignup ? "Bon retour !" : "Bonjour,<br>Bienvenue";
      document.getElementById("panelText").textContent = isSignup ? "Vous avez déjà un compte ?" : "Vous n'avez pas de compte ?";
      document.getElementById("panelBtn").textContent = isSignup ? "Se connecter" : "S'inscrire";
      document.getElementById("forgotLink").style.display = isSignup ? "none" : "block";
      document.getElementById("authPassword").setAttribute("autocomplete", isSignup ? "new-password" : "current-password");
    }

    function submitAuth() {
      const email = document.getElementById("authEmail").value.trim();
      const password = document.getElementById("authPassword").value;
      const errorEl = document.getElementById("authError");
      errorEl.textContent = "";
      errorEl.className = "auth-error";

      if (!email || !password) {
        errorEl.textContent = "Entrez un email et un mot de passe.";
        return;
      }
      if (password.length < 6) {
        errorEl.textContent = "Le mot de passe doit faire au moins 6 caractères.";
        return;
      }

      const promise = authMode === "signup"
        ? auth.createUserWithEmailAndPassword(email, password)
        : auth.signInWithEmailAndPassword(email, password);

      promise
        .then(() => { closeAuth(); })
        .catch(err => { errorEl.textContent = translateError(err.code); });
    }

    async function resetPassword() {
      const email = document.getElementById("authEmail").value.trim();
      const errorEl = document.getElementById("authError");
      errorEl.className = "auth-error";
      errorEl.textContent = "";
      if (!email) {
        errorEl.textContent = "Entrez votre email d'abord, puis cliquez sur 'Mot de passe oublié'.";
        return;
      }
      try {
        await auth.sendPasswordResetEmail(email);
        errorEl.className = "auth-success";
        errorEl.textContent = "Email de réinitialisation envoyé ! Vérifiez votre boîte.";
      } catch (err) {
        errorEl.textContent = translateError(err.code);
      }
    }

    function socialMsg(name) {
      alert("La connexion avec " + name + " sera disponible bientôt.");
    }

    function translateError(code) {
      const map = {
        "auth/email-already-in-use": "Cet email est déjà utilisé.",
        "auth/invalid-email": "L'email n'est pas valide.",
        "auth/weak-password": "Mot de passe trop faible (min. 6 caractères).",
        "auth/user-not-found": "Aucun compte avec cet email.",
        "auth/wrong-password": "Mot de passe incorrect.",
        "auth/invalid-credential": "Email ou mot de passe incorrect.",
        "auth/too-many-requests": "Trop de tentatives. Réessayez plus tard.",
        "auth/network-request-failed": "Problème de connexion internet.",
        "auth/operation-not-allowed": "Méthode Email/Password non activée dans Firebase."
      };
      return map[code] || "Une erreur est survenue. Réessayez.";
    }

    async function openProfile() {
      const user = auth.currentUser;
      if (!user) return;
      document.getElementById("profileError").textContent = "";
      fillClassSelect("");
      try {
        const docSnap = await db.collection("users").doc(user.uid).get();
        if (docSnap.exists) {
          const p = docSnap.data();
          document.getElementById("profileName").value = p.nom || "";
          fillClassSelect(p.classe || "");
          document.getElementById("profileSchool").value = p.ecole || "";
        } else {
          document.getElementById("profileName").value = "";
          fillClassSelect("");
          document.getElementById("profileSchool").value = "";
        }
      } catch (err) {
        console.error("Erreur lecture profil:", err);
      }
      document.getElementById("profileModal").classList.add("open");
    }

    function closeProfile() {
      document.getElementById("profileModal").classList.remove("open");
    }

    async function saveProfile() {
      const user = auth.currentUser;
      if (!user) return;
      const nom = document.getElementById("profileName").value.trim();
      const classe = document.getElementById("profileClass").value.trim();
      const ecole = document.getElementById("profileSchool").value.trim();
      const errorEl = document.getElementById("profileError");
      errorEl.textContent = "";
      if (!nom || !classe || !ecole) {
        errorEl.textContent = "Remplis tous les champs.";
        return;
      }
      try {
        await db.collection("users").doc(user.uid).set({
          nom: nom,
          classe: classe,
          ecole: ecole,
          email: user.email,
          creeLe: firebase.firestore.FieldValue.serverTimestamp()
        }, { merge: true });
        closeProfile();
        location.reload();
      } catch (e) {
        console.error("Erreur sauvegarde:", e);
        errorEl.textContent = "Erreur: " + e.message;
      }
    }

    function formatDate(timestamp) {
      if (!timestamp) return "à l'instant";
      const date = timestamp.toDate ? timestamp.toDate() : new Date(timestamp);
      const now = new Date();
      const diff = Math.floor((now - date) / 1000);
      if (diff < 60) return "à l'instant";
      if (diff < 3600) return "il y a " + Math.floor(diff / 60) + " min";
      if (diff < 86400) return "il y a " + Math.floor(diff / 3600) + " h";
      if (diff < 604800) return "il y a " + Math.floor(diff / 86400) + " j";
      return date.toLocaleDateString("fr-FR", { day: "numeric", month: "short", year: "numeric" });
    }

    function escapeHtml(text) {
      const div = document.createElement("div");
      div.textContent = text;
      return div.innerHTML;
    }

    async function createPost() {
      const user = auth.currentUser;
      if (!user) return;
      const title = document.getElementById("postTitle").value.trim();
      const content = document.getElementById("postContent").value.trim();
      const errorEl = document.getElementById("postError");
      errorEl.textContent = "";

      if (!title || !content) {
        errorEl.textContent = "Remplis le titre et le message.";
        return;
      }
      if (!currentUserProfile) { openProfile(); return; }
      const space = currentSpace === "class" ? currentUserProfile.classe : "general";

      try {
        await db.collection("posts").add({
          space: space,
          title: title,
          content: content,
          authorId: user.uid,
          authorName: currentUserProfile.nom,
          authorClass: currentUserProfile.classe,
          authorSchool: currentUserProfile?.ecole || "",
          createdAt: firebase.firestore.FieldValue.serverTimestamp()
        });
        document.getElementById("postTitle").value = "";
        document.getElementById("postContent").value = "";
        loadPosts();
      } catch (e) {
        console.error("Erreur création post:", e);
        errorEl.textContent = "Erreur: " + e.message;
      }
    }

    async function deletePost(postId) {
      if (!confirm("Veux-tu vraiment supprimer cette publication ?")) return;
      try {
        await db.collection("posts").doc(postId).delete();
        loadPosts();
      } catch (e) {
        alert("Erreur: " + e.message);
      }
    }

    function fillClassSelect(selected) {
      const sel = document.getElementById("profileClass");
      const list = CLASSES.slice();
      if (selected && !list.includes(selected)) list.push(selected);
      sel.innerHTML = '<option value="">Choisis ta classe</option>' +
        list.map(c => `<option value="${escapeHtml(c).replace(/"/g, "&quot;")}"${c === selected ? " selected" : ""}>${escapeHtml(c)}</option>`).join("");
    }

    function ts(c) { return c.createdAt && c.createdAt.toMillis ? c.createdAt.toMillis() : Date.now(); }
    function myClass() { return currentUserProfile && currentUserProfile.classe ? currentUserProfile.classe : null; }
    function activeSpaceKey() { return currentSpace === "general" ? "general" : myClass(); }

    function renderTabs() {
      const mc = myClass();
      const classLabel = mc ? "🎓 Classe " + escapeHtml(mc) : "🎓 Ma classe";
      document.getElementById("classFilters").innerHTML =
        `<button class="chip${currentSpace === "general" ? " active" : ""}" onclick="setSpace('general')">🌍 Communauté générale</button>` +
        `<button class="chip${currentSpace === "class" ? " active" : ""}" onclick="setSpace('class')">${classLabel}</button>`;
      document.getElementById("lbFilters").innerHTML =
        `<button class="chip${lbTab === "general" ? " active" : ""}" onclick="setLbTab('general')">🌍 Général</button>` +
        `<button class="chip${lbTab === "class" ? " active" : ""}" onclick="setLbTab('class')">${classLabel}</button>`;
      const lbl = document.getElementById("spaceLabel");
      if (lbl) lbl.textContent = currentSpace === "general"
        ? "Tu publies dans la communauté générale (visible par tous)."
        : "Tu publies dans la classe " + (mc || "") + " (visible seulement par ta classe).";
    }

    function setSpace(sp) {
      if (sp === "class") {
        if (!currentUser) { showMessage("Connexion"); return; }
        if (!myClass()) { openProfile(); return; }
      }
      currentSpace = sp;
      renderTabs();
      renderPosts();
    }
    function setLbTab(t) { lbTab = t; renderTabs(); renderLeaderboard(); }

    async function loadPosts() {
      const listEl = document.getElementById("postsList");
      renderTabs();
      try {
        const mc = myClass();
        const q = (col, space) => db.collection(col).where("space", "==", space).get();
        const jobs = [q("posts", "general"), q("comments", "general")];
        if (mc) {
          jobs.push(q("posts", mc).catch(() => null));
          jobs.push(q("comments", mc).catch(() => null));
        }
        const res = await Promise.all(jobs);
        const toArr = r => r ? r.docs.map(d => Object.assign({ id: d.id }, d.data())) : [];
        postsCache = toArr(res[0]).concat(toArr(res[2]));
        commentsCache = toArr(res[1]).concat(toArr(res[3]));
        postsCache.sort((a, b) => ts(b) - ts(a));
        renderPosts();
        renderLeaderboard();
      } catch (e) {
        console.error("Erreur chargement posts:", e);
        listEl.innerHTML = `
          <div class="empty-state">
            <div class="icon">⚠️</div>
            <p>Impossible de charger les discussions.</p>
            <p style="font-size:13px;margin-top:8px;color:#dc2626;">${escapeHtml(e.message)}</p>
          </div>`;
      }
    }

    function ratingInfo(c) {
      const vals = Object.values(c.ratings || {});
      const sum = vals.reduce((a, b) => a + b, 0);
      return { n: vals.length, sum: sum, avg: vals.length ? sum / vals.length : 0 };
    }

    function starsHtml(c, uid, mine) {
      const r = ratingInfo(c);
      const my = uid && c.ratings ? (c.ratings[uid] || 0) : 0;
      const filled = my || Math.round(r.avg);
      let h = "";
      for (let i = 1; i <= 5; i++) {
        const cls = "star" + (i <= filled ? (my ? " on mine" : " on") : "");
        h += mine
          ? `<span class="${cls}">★</span>`
          : `<button class="${cls}" onclick="rateComment('${c.id}', ${i})" title="${i}/5">★</button>`;
      }
      const label = r.n ? `${r.avg.toFixed(1)} (${r.n} vote${r.n > 1 ? "s" : ""})` : "Aucun vote";
      return `<div class="rating-row">${h}<span class="rating-text">${label}${my ? " · ta note : " + my + "/5" : ""}</span></div>`;
    }

    function renderPosts() {
      const listEl = document.getElementById("postsList");
      const key = activeSpaceKey();
      const posts = postsCache.filter(p => p.space === key).slice(0, 100);
      const note = currentSpace === "class"
        ? `<div class="space-note">🔒 Espace de la classe ${escapeHtml(key || "")} : seuls les élèves de ta classe voient ces discussions.</div>`
        : "";
      if (!posts.length) {
        listEl.innerHTML = note + `
          <div class="empty-state">
            <div class="icon">💭</div>
            <p>Aucune discussion pour le moment${currentSpace === "class" ? " dans ta classe" : ""}.</p>
            <p style="font-size:14px;margin-top:8px;">Sois le premier à poser une question !</p>
          </div>`;
        return;
      }
      const uid = currentUser ? currentUser.uid : null;
      listEl.innerHTML = note + posts.map(p => {
        const isOwner = uid && p.authorId === uid;
        const initial = (p.authorName || "?").charAt(0).toUpperCase();
        const comments = commentsCache.filter(c => c.postId === p.id).sort((a, b) => ts(a) - ts(b));

        const commentsHtml = comments.map(c => {
          const mine = uid && c.authorId === uid;
          let actions = "";
          if (mine) actions += `<button class="mini-btn del" onclick="deleteComment('${c.id}')">🗑 Supprimer</button>`;
          if (isOwner && !mine) actions += `<button class="mini-btn${c.correct ? " on" : ""}" onclick="toggleCorrect('${c.id}')">${c.correct ? "✅ Réponse validée" : "Valider cette réponse"}</button>`;
          return `
            <div class="comment${c.correct ? " is-correct" : ""}">
              <div class="avatar small">${escapeHtml((c.authorName || "?").charAt(0).toUpperCase())}</div>
              <div class="comment-body">
                <div class="comment-head">${escapeHtml(c.authorName || "Anonyme")}<small>${escapeHtml(c.authorClass || "")} · ${formatDate(c.createdAt)}</small> ${c.correct ? '<span class="correct-badge">✅ Réponse correcte</span>' : ""}</div>
                <div class="comment-text">${escapeHtml(c.content)}</div>
                ${starsHtml(c, uid, mine)}
                ${actions ? `<div class="comment-actions">${actions}</div>` : ""}
              </div>
            </div>`;
        }).join("");

        const replyHtml = currentUser
          ? `<div class="reply-row">
               <input type="text" id="reply-${p.id}" placeholder="Écris ta réponse..." maxlength="1000" onkeydown="if(event.key==='Enter'){addComment('${p.id}')}">
               <button class="primary" onclick="addComment('${p.id}')">Répondre</button>
             </div>`
          : `<p class="reply-hint">Connecte-toi pour répondre et noter les réponses.</p>`;

        return `
          <article class="post-card">
            <div class="post-header">
              <div class="post-author">
                <div class="avatar">${escapeHtml(initial)}</div>
                <div class="author-info">
                  <span class="author-name">${escapeHtml(p.authorName || "Anonyme")} ${p.authorClass ? `<span class="class-badge">${escapeHtml(p.authorClass)}</span>` : ""}</span>
                  <span class="author-meta">${escapeHtml(p.authorSchool || "")}</span>
                </div>
              </div>
              <span class="post-date">${formatDate(p.createdAt)}</span>
            </div>
            <h3 class="post-title">${escapeHtml(p.title)}</h3>
            <p class="post-content">${escapeHtml(p.content)}</p>
            ${isOwner ? `
              <div class="post-footer">
                <div></div>
                <div class="post-owner-actions">
                  <button onclick="deletePost('${p.id}')">🗑 Supprimer</button>
                </div>
              </div>` : ""}
            <div class="comments">
              <div class="comments-title">💬 ${comments.length} réponse${comments.length > 1 ? "s" : ""}</div>
              ${commentsHtml}
              ${replyHtml}
            </div>
          </article>`;
      }).join("");
    }

    async function addComment(postId) {
      const user = auth.currentUser;
      if (!user) { showMessage("Connexion"); return; }
      if (!currentUserProfile) { openProfile(); return; }
      const post = postsCache.find(x => x.id === postId);
      const input = document.getElementById("reply-" + postId);
      if (!post || !input) return;
      const content = input.value.trim();
      if (!content) return;
      try {
        await db.collection("comments").add({
          postId: postId,
          space: post.space,
          content: content,
          authorId: user.uid,
          authorName: currentUserProfile.nom,
          authorClass: currentUserProfile.classe,
          authorSchool: currentUserProfile.ecole,
          ratings: {},
          correct: false,
          createdAt: firebase.firestore.FieldValue.serverTimestamp()
        });
        await loadPosts();
      } catch (e) {
        alert("Erreur: " + e.message);
      }
    }

    async function rateComment(commentId, stars) {
      const user = auth.currentUser;
      if (!user) { showMessage("Connexion"); return; }
      try {
        await db.collection("comments").doc(commentId).update({ ["ratings." + user.uid]: stars });
        await loadPosts();
      } catch (e) {
        alert("Erreur: " + e.message);
      }
    }

    async function toggleCorrect(commentId) {
      const c = commentsCache.find(x => x.id === commentId);
      if (!c) return;
      try {
        await db.collection("comments").doc(commentId).update({ correct: !c.correct });
        await loadPosts();
      } catch (e) {
        alert("Erreur: " + e.message);
      }
    }

    async function deleteComment(commentId) {
      if (!confirm("Supprimer cette réponse ?")) return;
      try {
        await db.collection("comments").doc(commentId).delete();
        await loadPosts();
      } catch (e) {
        alert("Erreur: " + e.message);
      }
    }

    function weekStart() {
      const d = new Date();
      d.setHours(0, 0, 0, 0);
      d.setDate(d.getDate() - ((d.getDay() + 6) % 7));
      return d.getTime();
    }

    function renderLeaderboard() {
      const el = document.getElementById("lbList");
      const key = lbTab === "general" ? "general" : myClass();
      if (!key) {
        el.innerHTML = `<div class="empty-state"><div class="icon">🎓</div><p>Connecte-toi et choisis ta classe pour voir le classement de ta classe.</p></div>`;
        return;
      }
      const start = weekStart();
      const scores = {};
      commentsCache.forEach(c => {
        if (c.space !== key || ts(c) < start) return;
        if (!scores[c.authorId]) scores[c.authorId] = { name: c.authorName, cls: c.authorClass, school: c.authorSchool, answers: 0, stars: 0, correct: 0 };
        const x = scores[c.authorId];
        x.answers += 1;
        x.stars += ratingInfo(c).sum;
        if (c.correct) x.correct += 1;
      });
      const top = Object.values(scores)
        .map(x => Object.assign(x, { points: x.answers + x.stars + x.correct * 5 }))
        .sort((a, b) => b.points - a.points)
        .slice(0, 5);
      if (!top.length) {
        el.innerHTML = `<div class="empty-state"><div class="icon">🏆</div><p>Pas encore de classement cette semaine.</p><p style="font-size:14px;margin-top:8px;">Réponds aux questions pour gagner des points !</p></div>`;
        return;
      }
      const medals = ["🥇", "🥈", "🥉", "4", "5"];
      el.innerHTML = top.map((x, i) => `
        <div class="lb-row">
          <div class="lb-rank">${medals[i]}</div>
          <div class="lb-info">
            <div class="lb-name">${escapeHtml(x.name || "Anonyme")}</div>
            <div class="lb-meta">${escapeHtml([x.cls, x.school].filter(Boolean).join(" · "))} · ${x.answers} réponse${x.answers > 1 ? "s" : ""} · ⭐ ${x.stars} · ✅ ${x.correct}</div>
          </div>
          <div class="lb-points">${x.points} pts</div>
        </div>`).join("");
    }

    auth.onAuthStateChanged(async user => {
      currentUser = user;
      const signupBtn = document.querySelector('button[onclick*="Inscription"]');
      const loginBtn = document.querySelector('button[onclick*="Connexion"]');
      const existingInfo = document.getElementById("userInfo");
      if (existingInfo) existingInfo.remove();

      const newPostBox = document.getElementById("newPostBox");
      const loginNotice = document.getElementById("loginNotice");

      if (user) {
        if (signupBtn) signupBtn.style.display = "none";
        if (loginBtn) loginBtn.style.display = "none";

        const headerDiv = (loginBtn || signupBtn).parentElement;
        const info = document.createElement("div");
        info.id = "userInfo";
        info.innerHTML = `
          <button class="avatar-btn" id="avatarBtn" onclick="openProfile()" title="Mon profil">👤</button>
          <button class="outline" onclick="logout()">Déconnexion</button>
        `;
        headerDiv.appendChild(info);

        newPostBox.style.display = "block";
        loginNotice.style.display = "none";

        try {
          const docSnap = await db.collection("users").doc(user.uid).get();
          if (docSnap.exists) {
            currentUserProfile = docSnap.data();
            const p = currentUserProfile;
            const av = document.getElementById("avatarBtn");
            av.textContent = (p.nom || "?").trim().charAt(0).toUpperCase();
            av.title = p.nom + " (" + p.classe + ")";
          } else {
            currentUserProfile = null;
            openProfile();
          }
        } catch (err) {
          console.error("Erreur chargement profil:", err);
          openProfile();
        }
      } else {
        if (signupBtn) signupBtn.style.display = "";
        if (loginBtn) loginBtn.style.display = "";
        currentUserProfile = null;
        currentSpace = "general";
        newPostBox.style.display = "none";
        loginNotice.style.display = "block";
      }

      loadPosts();
    });

    function logout() {
      auth.signOut();
    }

    document.getElementById("authModal").addEventListener("click", e => {
      if (e.target.id === "authModal") closeAuth();
    });
    document.getElementById("profileModal").addEventListener("click", e => {
      if (e.target.id === "profileModal") closeProfile();
    });
    document.getElementById("authPassword").addEventListener("keydown", e => {
      if (e.key === "Enter") { e.preventDefault(); submitAuth(); }
    });

    document.getElementById("year").textContent = new Date().getFullYear();
  </script>
</body>
</html>
