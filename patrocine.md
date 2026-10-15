---
layout: default
title: Patrocine um mutirão
permalink: /patrocine/
---

<style>
  .sp-hero h1 { display: flex; align-items: center; gap: 10px; }
  .sp-hero .ti { color: var(--gold); width: 1.3em; height: 1.3em; }
  .sp-list { display: grid; gap: 12px; margin: 18px 0; }
  .sp-card { background: var(--surface); border: 1px solid var(--border); border-radius: 14px; padding: 14px 16px; cursor: pointer; }
  .sp-card:hover, .sp-card.on { border-color: var(--purple); }
  .sp-card h3 { margin: 0 0 4px; color: var(--heading); font-size: 17px; }
  .sp-meta { color: var(--muted); font-size: 14px; }
  .sp-pill { display: inline-block; font-size: 12px; font-weight: 700; padding: 2px 8px; border-radius: 10px; background: rgba(108, 99, 255, .2); color: var(--purple); margin-right: 6px; }
  .sp-pill.gold { background: rgba(251, 191, 36, .15); color: var(--gold); }
  .sp-form { background: var(--surface); border: 1px solid var(--purple); border-radius: 14px; padding: 18px; margin: 18px 0; }
  .sp-form h2 { margin-top: 0; }
  .sp-form label { display: block; font-size: 14px; color: var(--muted); margin: 10px 0 4px; }
  .sp-form input[type=text], .sp-form input[type=email], .sp-form input[type=tel], .sp-form textarea {
    width: 100%; background: var(--bg); border: 1px solid var(--border); border-radius: 10px; color: var(--text); padding: 10px 12px; font: inherit;
  }
  .sp-form textarea { min-height: 80px; }
  .sp-grid { display: grid; gap: 0 14px; }
  @media (min-width: 640px) { .sp-grid { grid-template-columns: 1fr 1fr; } }
  .sp-kinds { display: flex; flex-wrap: wrap; gap: 8px 16px; margin-top: 4px; }
  .sp-kinds label, .sp-check { display: flex; align-items: flex-start; gap: 8px; color: var(--text); margin: 0; font-size: 15px; }
  .sp-check { margin-top: 14px; }
  .sp-btn { margin-top: 16px; background: #6C63FF; color: #fff; border: 0; border-radius: 12px; padding: 12px 22px; font: inherit; font-weight: 700; cursor: pointer; }
  .sp-btn:disabled { opacity: .5; cursor: default; }
  .sp-msg { margin-top: 12px; padding: 10px 14px; border-radius: 10px; display: none; }
  .sp-msg.ok { display: block; background: rgba(34, 197, 94, .12); color: #86efac; }
  .sp-msg.err { display: block; background: rgba(239, 68, 68, .12); color: #fca5a5; }
  .sp-hp { position: absolute; left: -9999px; }
  .sp-ba { display: grid; grid-template-columns: 1fr 1fr; gap: 6px; margin: 12px 0; }
  .sp-ba figure { margin: 0; position: relative; }
  .sp-ba img { width: 100%; height: 220px; object-fit: cover; border-radius: 10px; display: block; }
  .sp-ba figcaption { position: absolute; left: 8px; bottom: 8px; background: #475569; color: #fff; font-size: 12px; font-weight: 800; padding: 2px 8px; border-radius: 8px; }
  .sp-ba figure + figure figcaption { background: #16a34a; }
  .sp-sponsors { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 8px; }
  .sp-sponsor { display: flex; align-items: center; gap: 8px; background: var(--bg); border: 1px solid var(--border); border-radius: 10px; padding: 6px 10px; font-size: 14px; }
  .sp-sponsor img { width: 28px; height: 28px; object-fit: contain; background: #fff; border-radius: 6px; }
  .note { background: var(--surface); border: 1px solid var(--border); border-left: 3px solid var(--gold); border-radius: 0 12px 12px 0; padding: 12px 16px; margin: 16px 0; }
</style>

<div class="sp-hero">
<p>No CitySpots, a comunidade se junta para limpar praças, praias e lugares que precisam de cuidado. Sua empresa pode apoiar doando o que faz falta no dia: <strong>sacos de lixo, luvas, água, lanche, ferramentas ou brindes</strong>. Em troca, o nome da sua empresa aparece no mutirão, no registro de antes e depois e na página do resultado.</p>
</div>

<div class="note">
<strong>Como funciona:</strong> você escolhe um mutirão e conta o que pode oferecer. A equipe do CitySpots da região confere a empresa e quem organiza o mutirão confirma. Aí vocês combinam a entrega direto. O apoio é <strong>só em produtos</strong>: o CitySpots não recebe nem repassa dinheiro. Até 3 empresas por mutirão.
</div>

<div id="sp-result"></div>

<h2 id="sp-list-title">Mutirões abertos para apoio</h2>
<div id="sp-list" class="sp-list"><p class="sp-meta">Carregando…</p></div>

<form id="sp-form" class="sp-form" style="display:none" autocomplete="on">
  <h2>Quero apoiar: <span id="sp-chosen"></span></h2>
  <div class="sp-grid">
    <div><label for="f-company">Nome da empresa *</label><input type="text" id="f-company" maxlength="80" required></div>
    <div><label for="f-sector">Ramo / setor *</label><input type="text" id="f-sector" maxlength="60" placeholder="Ex.: padaria, mercado, construção" required></div>
    <div><label for="f-doc">CNPJ (opcional)</label><input type="text" id="f-doc" maxlength="20"></div>
    <div><label for="f-site">Site ou Instagram (opcional)</label><input type="text" id="f-site" maxlength="200" placeholder="@suaempresa"></div>
    <div><label for="f-name">Seu nome *</label><input type="text" id="f-name" maxlength="80" autocomplete="name" required></div>
    <div><label for="f-email">E-mail *</label><input type="email" id="f-email" maxlength="120" autocomplete="email" required></div>
    <div><label for="f-phone">WhatsApp ou telefone (opcional)</label><input type="tel" id="f-phone" maxlength="30" autocomplete="tel"></div>
  </div>
  <label>O que pode oferecer *</label>
  <div class="sp-kinds">
    <label><input type="checkbox" value="materiais"> Materiais (sacos, luvas)</label>
    <label><input type="checkbox" value="agua"> Água</label>
    <label><input type="checkbox" value="lanche"> Lanche</label>
    <label><input type="checkbox" value="ferramentas"> Ferramentas</label>
    <label><input type="checkbox" value="brindes"> Brindes</label>
  </div>
  <label for="f-offer">Conte com detalhes *</label>
  <textarea id="f-offer" maxlength="500" placeholder="Ex.: 50 sacos de lixo de 100 L, 20 pares de luvas e 2 fardos de água." required></textarea>
  <input type="text" id="f-hp" class="sp-hp" tabindex="-1" autocomplete="off" aria-hidden="true">
  <label class="sp-check"><input type="checkbox" id="f-rules"> <span>Confirmo que a empresa não é do ramo de bebida alcoólica, cigarro ou vape, apostas, partidos ou campanhas políticas ou instituições religiosas; que o apoio é só em produtos; e concordo que o CitySpots e quem organiza o mutirão usem estes dados de contato para combinar o apoio (veja a <a href="{{ site.baseurl }}/privacidade/">Política de Privacidade</a> e os <a href="{{ site.baseurl }}/termos/">Termos de Uso</a>).</span></label>
  <button type="submit" class="sp-btn" id="f-send">Enviar pedido de apoio</button>
  <div id="sp-msg" class="sp-msg"></div>
</form>

<script>
(function () {
  var API = 'https://m4cserver.tail784c26.ts.net';
  var chosen = null;
  var $ = function (id) { return document.getElementById(id); };
  function esc(s) { return String(s == null ? '' : s).replace(/[&<>"']/g, function (c) { return { '&': '&amp;', '<': '&lt;', '>': '&gt;', '"': '&quot;', "'": '&#39;' }[c]; }); }
  function when(a, b) {
    var s = new Date(a), e = new Date(b);
    var d = s.toLocaleDateString('pt-BR', { weekday: 'long', day: '2-digit', month: '2-digit' });
    var t = function (x) { return x.toLocaleTimeString('pt-BR', { hour: '2-digit', minute: '2-digit' }); };
    return d + ', ' + t(s) + '–' + t(e);
  }
  function sponsorsHtml(list) {
    if (!list || !list.length) return '';
    return '<div class="sp-sponsors">' + list.map(function (s) {
      return '<span class="sp-sponsor">' + (s.logo_url ? '<img src="' + esc(s.logo_url) + '" alt="">' : '') + esc(s.name) + '</span>';
    }).join('') + '</div>';
  }
  function choose(m) {
    chosen = m;
    $('sp-chosen').textContent = m.title;
    $('sp-form').style.display = 'block';
    $('sp-msg').className = 'sp-msg';
    document.querySelectorAll('.sp-card').forEach(function (c) { c.classList.toggle('on', c.dataset.id === m.id); });
    $('sp-form').scrollIntoView({ behavior: 'smooth', block: 'start' });
  }
  function card(m) {
    var el = document.createElement('div');
    el.className = 'sp-card'; el.dataset.id = m.id;
    el.innerHTML = '<h3>' + esc(m.title) + '</h3>' +
      '<div class="sp-meta">' + (m.official ? '<span class="sp-pill">Oficial</span>' : '') + '<span class="sp-pill gold">' + (m.slots_left > 0 ? m.slots_left + ' vaga(s) para apoio' : 'Apoio completo') + '</span></div>' +
      '<div class="sp-meta">' + esc(when(m.starts_at, m.ends_at)) + '</div>' +
      '<div class="sp-meta">' + esc(m.spot_title) + (m.city ? ' · ' + esc(m.city) : '') + (m.state ? ' / ' + esc(m.state) : '') + ' · ' + m.going + ' pessoa(s) confirmada(s)</div>' +
      (m.items && m.items.length ? '<div class="sp-meta">Precisa de: ' + m.items.map(esc).join(', ') + '</div>' : '') +
      sponsorsHtml(m.sponsors);
    if (m.slots_left > 0) el.addEventListener('click', function () { choose(m); });
    return el;
  }
  function showResult(m) {
    var done = m.status === 'done';
    var html = '<div class="sp-form" style="border-color:' + (done ? '#16a34a' : 'var(--purple)') + '">' +
      '<h2>' + esc(m.title) + '</h2><div class="sp-meta">' + esc(m.spot_title) + (m.city ? ' · ' + esc(m.city) : '') + ' · ' + esc(when(m.starts_at, m.ends_at)) + '</div>';
    if (done) {
      if (m.before_photo_url && m.after_photo_url) html += '<div class="sp-ba"><figure><img src="' + esc(m.before_photo_url) + '" alt="Antes"><figcaption>Antes</figcaption></figure><figure><img src="' + esc(m.after_photo_url) + '" alt="Depois"><figcaption>Depois</figcaption></figure></div>';
      html += '<p><strong>' + m.present + ' pessoas</strong> ajudaram' + (m.result_bags ? ' e recolheram <strong>' + m.result_bags + ' sacos de lixo</strong>' : '') + '.' + (m.result_note ? ' ' + esc(m.result_note) : '') + '</p>';
      if (m.sponsors.length) html += '<p class="sp-meta">Com o apoio de:</p>' + sponsorsHtml(m.sponsors);
    } else {
      if (m.description) html += '<p>' + esc(m.description) + '</p>';
      html += '<p class="sp-meta">' + m.going + ' pessoa(s) confirmada(s).</p>' + sponsorsHtml(m.sponsors);
    }
    $('sp-result').innerHTML = html + '</div>';
    return !done && m.open_for_sponsors && m.slots_left > 0;
  }

  var params = new URLSearchParams(location.search);
  var wanted = params.get('m');

  fetch(API + '/public/mutiroes').then(function (r) { return r.json(); }).then(function (d) {
    var list = $('sp-list'); list.innerHTML = '';
    if (!d.mutiroes.length) { list.innerHTML = '<p class="sp-meta">Nenhum mutirão marcado no momento. Volte em breve!</p>'; }
    d.mutiroes.forEach(function (m) { list.appendChild(card(m)); });
    if (wanted) {
      var m = d.mutiroes.filter(function (x) { return x.id === wanted; })[0];
      if (m && m.slots_left > 0) choose(m);
    }
  }).catch(function () { $('sp-list').innerHTML = '<p class="sp-meta">Não foi possível carregar os mutirões agora. Tente de novo em alguns minutos.</p>'; });

  // Link de um mutirão específico (do app, ou o resultado depois que acontece).
  if (wanted && /^[0-9a-f-]{36}$/i.test(wanted)) {
    fetch(API + '/public/mutiroes/' + wanted).then(function (r) { return r.ok ? r.json() : null; }).then(function (d) {
      if (d && d.mutirao) showResult(d.mutirao);
    }).catch(function () {});
  }

  $('sp-form').addEventListener('submit', function (e) {
    e.preventDefault();
    if (!chosen) return;
    var msg = $('sp-msg');
    if (!$('f-rules').checked) { msg.className = 'sp-msg err'; msg.textContent = 'Marque a confirmação das regras para enviar.'; return; }
    var kinds = Array.prototype.slice.call(document.querySelectorAll('.sp-kinds input:checked')).map(function (i) { return i.value; });
    var body = {
      company_name: $('f-company').value.trim(), sector: $('f-sector').value.trim(), company_doc: $('f-doc').value.trim() || undefined,
      website: $('f-site').value.trim() || undefined, contact_name: $('f-name').value.trim(), contact_email: $('f-email').value.trim(),
      contact_phone: $('f-phone').value.trim() || undefined, offer: $('f-offer').value.trim(), offer_kinds: kinds, accept_rules: true, hp: $('f-hp').value
    };
    $('f-send').disabled = true;
    fetch(API + '/public/mutiroes/' + chosen.id + '/sponsor', { method: 'POST', headers: { 'Content-Type': 'application/json' }, body: JSON.stringify(body) })
      .then(function (r) { return r.json().then(function (j) { return { ok: r.ok, j: j }; }); })
      .then(function (res) {
        if (res.ok) {
          msg.className = 'sp-msg ok';
          msg.textContent = 'Pedido enviado! A equipe do CitySpots vai conferir e, depois que quem organiza confirmar, vocês combinam a entrega. Obrigado por cuidar da cidade junto com a gente.';
          $('sp-form').reset();
        } else { msg.className = 'sp-msg err'; msg.textContent = res.j.error || 'Não foi possível enviar.'; $('f-send').disabled = false; }
      })
      .catch(function () { msg.className = 'sp-msg err'; msg.textContent = 'Sem conexão com o CitySpots agora. Tente de novo em alguns minutos.'; $('f-send').disabled = false; });
  });
})();
</script>
