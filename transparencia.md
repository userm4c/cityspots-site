---
layout: default
title: Transparência
permalink: /transparencia/
---

<style>
  .tr-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 10px; margin: 14px 0; }
  .tr-card { background: var(--surface); border: 1px solid var(--border); border-radius: 12px; padding: 12px 14px; }
  .tr-num { color: var(--heading); font-size: 26px; font-weight: 800; line-height: 1.2; font-variant-numeric: tabular-nums; }
  .tr-label { color: var(--muted); font-size: 13px; }
  .tr-zero .tr-num { color: #86efac; }
  .tr-note { color: var(--muted); font-size: 14px; }
  .tr-loading { color: var(--muted); }
  .tr-err { color: #fca5a5; }
  a.tr-card { display: block; text-decoration: none; color: inherit; }
  a.tr-card:hover { border-color: var(--purple); }
  a.tr-card .tr-label::after { content: ' ›'; color: var(--purple); }
  .tr-chips { display: flex; flex-wrap: wrap; gap: 8px; margin: 12px 0; }
  .tr-chip { background: transparent; border: 1px solid var(--border); color: var(--muted); border-radius: 16px; padding: 5px 12px; font: inherit; font-size: 14px; cursor: pointer; }
  .tr-chip.on { border-color: var(--purple); color: var(--heading); background: rgba(167, 139, 250, .12); }
  .tr-log { list-style: none; padding: 0; margin: 0; display: grid; gap: 8px; }
  .tr-log li { background: var(--surface); border: 1px solid var(--border); border-radius: 12px; padding: 10px 14px; margin: 0; }
  .tr-log .k { font-size: 12px; font-weight: 700; letter-spacing: .4px; text-transform: uppercase; }
  .tr-log .s { color: var(--heading); font-weight: 600; }
  .tr-log .r { color: var(--text); font-size: 14px; }
  .tr-log .d { color: var(--muted); font-size: 13px; }
  .tr-more { margin-top: 10px; background: transparent; border: 1px solid var(--border); color: var(--text); border-radius: 10px; padding: 8px 14px; font: inherit; cursor: pointer; }
</style>

Este é o relatório de transparência prometido no [Manifesto]({{ site.baseurl }}/manifesto/). Os números são **atualizados sozinhos** a partir do próprio CitySpots (a cada 10 minutos), são **totais anônimos** e não identificam ninguém.

<p class="tr-loading" id="tr-status">Carregando os números…</p>

<div id="tr" hidden>

<h2>Dinheiro e dados</h2>
<p>O CitySpots não existe para gerar lucro em cima de quem usa.</p>
<div class="tr-grid">
  <div class="tr-card tr-zero"><div class="tr-num">0</div><div class="tr-label">dados de usuários vendidos ou alugados, para ninguém</div></div>
  <div class="tr-card"><div class="tr-num" data-k="money.sponsorships"></div><div class="tr-label">patrocínios de mutirão aceitos, sempre em produtos, nunca em dinheiro</div></div>
  <div class="tr-card"><div class="tr-num" data-k="money.paid_campaigns"></div><div class="tr-label">anúncios pagos de comércios locais</div></div>
</div>
<p class="tr-note" id="tr-ads"></p>
<div id="tr-costs" hidden>
  <h3>Quanto custa manter o CitySpots</h3>
  <div class="table-wrap"><table><thead><tr><th>Item</th><th>Por mês</th></tr></thead><tbody id="tr-costs-body"></tbody></table></div>
</div>
<p class="tr-note" id="tr-money-note" hidden></p>

<h2>Moderação</h2>
<p>As regras são as mesmas para todo mundo e estão nas <a href="{{ site.baseurl }}/diretrizes/">Diretrizes da Comunidade</a>. Ninguém é moderado com mais rigor por causa das suas opiniões.</p>
<div class="tr-grid">
  <div class="tr-card"><div class="tr-num" data-k="moderation.reports"></div><div class="tr-label">denúncias recebidas desde o início</div></div>
  <div class="tr-card"><div class="tr-num" data-k="moderation.last_30d"></div><div class="tr-label">nos últimos 30 dias</div></div>
  <a class="tr-card" href="#registro" data-group="reports"><div class="tr-num" data-k="moderation.removed"></div><div class="tr-label">terminaram com o conteúdo removido</div></a>
  <a class="tr-card" href="#registro" data-group="reports"><div class="tr-num" data-k="moderation.kept"></div><div class="tr-label">terminaram com o conteúdo mantido</div></a>
  <div class="tr-card"><div class="tr-num" data-k="moderation.open"></div><div class="tr-label">em análise agora</div></div>
  <a class="tr-card" href="#registro" data-group="accounts"><div class="tr-num" data-k="moderation.users_suspended"></div><div class="tr-label">contas suspensas hoje</div></a>
  <a class="tr-card" href="#registro" data-group="accounts"><div class="tr-num" data-k="moderation.users_banned"></div><div class="tr-label">contas banidas</div></a>
  <a class="tr-card" href="#registro" data-group="spots"><div class="tr-num" data-k="moderation.spots_deactivated"></div><div class="tr-label">spots desativados pela equipe</div></a>
  <a class="tr-card" href="#registro" data-group="appeals"><div class="tr-num" data-k="moderation.appeals"></div><div class="tr-label">contestações de quem criou o spot</div></a>
  <a class="tr-card" href="#registro" data-group="appeals"><div class="tr-num" data-k="moderation.appeals_reverted"></div><div class="tr-label">contestações aceitas (o spot voltou)</div></a>
</div>

<h2 id="registro">Registro público de moderação</h2>
<p>Cada decisão da equipe, com o motivo. Spots são lugares públicos e aparecem pelo nome; contas nunca aparecem pelo nome, e o conteúdo denunciado e quem denunciou nunca são mostrados. As decisões são assinadas pela <strong>Equipe CitySpots</strong>. Quem criou um spot desativado pode contestar pelo app, e a revisão é feita por outra pessoa da equipe.</p>
<div class="tr-chips" id="tr-chips">
  <button class="tr-chip on" data-g="">Tudo</button>
  <button class="tr-chip" data-g="spots">Spots</button>
  <button class="tr-chip" data-g="appeals">Contestações</button>
  <button class="tr-chip" data-g="reports">Denúncias</button>
  <button class="tr-chip" data-g="accounts">Contas</button>
  <button class="tr-chip" data-g="legal">Pedidos legais</button>
</div>
<ul class="tr-log" id="tr-log"></ul>
<p class="tr-note" id="tr-log-empty" hidden>Nenhuma decisão registrada aqui ainda.</p>
<button class="tr-more" id="tr-more" hidden>Ver mais</button>

<h2>Pedidos de governos e da Justiça</h2>
<p>Quantas vezes algum governo, polícia ou juiz pediu ao CitySpots para retirar conteúdo ou entregar dados de alguém.</p>
<div class="tr-grid">
  <div class="tr-card"><div class="tr-num" data-k="legal_requests.content"></div><div class="tr-label">pedidos para retirar conteúdo</div></div>
  <div class="tr-card"><div class="tr-num" data-k="legal_requests.data"></div><div class="tr-label">pedidos de dados de usuários</div></div>
</div>

<h2>A cidade cuidada junto</h2>
<div class="tr-grid">
  <div class="tr-card"><div class="tr-num" data-k="care.bags"></div><div class="tr-label">sacos de lixo recolhidos</div></div>
  <div class="tr-card"><div class="tr-num" data-k="care.mutiroes"></div><div class="tr-label">mutirões feitos</div></div>
  <div class="tr-card"><div class="tr-num" data-k="care.care_resolved"></div><div class="tr-label">problemas resolvidos nos pontos de cuidado</div></div>
  <div class="tr-card"><div class="tr-num" data-k="care.adopted_places"></div><div class="tr-label">lugares adotados por guardiões</div></div>
  <div class="tr-card"><div class="tr-num" data-k="care.good_points"></div><div class="tr-label">pontos do bem no mapa</div></div>
</div>

<h2>A comunidade</h2>
<div class="tr-grid">
  <div class="tr-card"><div class="tr-num" data-k="community.people"></div><div class="tr-label">pessoas com conta ativa</div></div>
  <div class="tr-card"><div class="tr-num" data-k="community.cities"></div><div class="tr-label">cidades com spots</div></div>
  <div class="tr-card"><div class="tr-num" data-k="community.spots"></div><div class="tr-label">spots no mapa</div></div>
  <div class="tr-card"><div class="tr-num" data-k="community.checkins"></div><div class="tr-label">check-ins</div></div>
  <div class="tr-card"><div class="tr-num" data-k="team.staff"></div><div class="tr-label">pessoas na equipe de moderação</div></div>
</div>

<p class="tr-note" id="tr-updated"></p>

</div>

<script>
  (function () {
    var API = 'https://m4cserver.tail784c26.ts.net';
    var ADS = {
      off: 'Não há anúncios no app.',
      house: 'Os únicos anúncios no app são do próprio CitySpots e de comércios locais parceiros. A rede de anúncios do Google está desligada.',
      test: 'A rede de anúncios do Google está em teste, sem gerar dinheiro.',
      live: 'O app mostra anúncios da rede do Google, sem anúncios políticos, eleitorais ou religiosos.'
    };
    var fmt = function (n) { return Number(n || 0).toLocaleString('pt-BR'); };
    var get = function (o, path) { return path.split('.').reduce(function (a, k) { return a == null ? a : a[k]; }, o); };
    var status = document.getElementById('tr-status');
    var KIND = {
      spot_deactivated: ['Spot desativado', '#fbbf24'], spot_reactivated: ['Spot reativado', '#86efac'],
      report_removed: ['Denúncia: conteúdo removido', '#fca5a5'], report_kept: ['Denúncia: conteúdo mantido', '#94a3b8'],
      account_suspended: ['Conta suspensa', '#fbbf24'], account_banned: ['Conta banida', '#fca5a5'], account_restored: ['Conta restaurada', '#86efac'],
      appeal_upheld: ['Contestação: decisão mantida', '#94a3b8'], appeal_reverted: ['Contestação aceita: o spot voltou', '#86efac'],
      legal_request: ['Pedido de governo ou da Justiça', '#a78bfa']
    };
    var group = '', next = null;
    var logEl = document.getElementById('tr-log'), moreEl = document.getElementById('tr-more'), emptyEl = document.getElementById('tr-log-empty');
    function el(tag, cls, text) { var e = document.createElement(tag); if (cls) e.className = cls; if (text != null) e.textContent = text; return e; }
    function loadLog(reset) {
      if (reset) { logEl.innerHTML = ''; next = null; }
      var url = API + '/public/transparency/log?limit=30' + (group ? '&group=' + group : '') + (next ? '&before=' + encodeURIComponent(next) : '');
      fetch(url).then(function (r) { return r.json(); }).then(function (d) {
        d.entries.forEach(function (e) {
          var k = KIND[e.kind] || [e.kind, '#94a3b8'];
          var li = el('li');
          var kk = el('div', 'k', k[0]); kk.style.color = k[1]; li.appendChild(kk);
          li.appendChild(el('div', 's', e.subject));
          if (e.category_label) li.appendChild(el('div', 'r', e.category_label));
          if (e.reason) li.appendChild(el('div', 'r', '“' + e.reason + '”'));
          li.appendChild(el('div', 'd', new Date(e.created_at).toLocaleString('pt-BR', { dateStyle: 'short', timeStyle: 'short' }) + ' · Equipe CitySpots'));
          logEl.appendChild(li);
        });
        next = d.next;
        moreEl.hidden = !next;
        emptyEl.hidden = logEl.children.length > 0;
      }).catch(function () { emptyEl.hidden = false; emptyEl.textContent = 'Não foi possível carregar o registro agora.'; });
    }
    function setGroup(g) {
      group = g;
      document.querySelectorAll('#tr-chips .tr-chip').forEach(function (c) { c.classList.toggle('on', c.getAttribute('data-g') === g); });
      loadLog(true);
    }
    document.querySelectorAll('#tr-chips .tr-chip').forEach(function (c) { c.addEventListener('click', function () { setGroup(c.getAttribute('data-g')); }); });
    document.querySelectorAll('a[data-group]').forEach(function (a) { a.addEventListener('click', function () { setGroup(a.getAttribute('data-group')); }); });
    moreEl.addEventListener('click', function () { loadLog(false); });
    loadLog(true);
    fetch(API + '/public/transparency').then(function (r) {
      if (!r.ok) throw new Error(r.status);
      return r.json();
    }).then(function (d) {
      document.querySelectorAll('[data-k]').forEach(function (el) {
        var v = get(d, el.getAttribute('data-k'));
        el.textContent = fmt(v);
        if (Number(v) === 0) el.parentElement.classList.add('tr-zero');
      });
      document.getElementById('tr-ads').textContent = ADS[d.money.ads_mode] || '';
      var costs = d.money.costs || [];
      if (costs.length) {
        var body = document.getElementById('tr-costs-body');
        var total = 0;
        costs.forEach(function (c) {
          total += Number(c.monthly_brl || 0);
          var tr = document.createElement('tr');
          var a = document.createElement('td'); a.textContent = c.item;
          var b = document.createElement('td'); b.textContent = 'R$ ' + Number(c.monthly_brl || 0).toLocaleString('pt-BR', { minimumFractionDigits: 2 });
          tr.appendChild(a); tr.appendChild(b); body.appendChild(tr);
        });
        var tr = document.createElement('tr');
        tr.innerHTML = '<th>Total</th><th></th>';
        tr.lastChild.textContent = 'R$ ' + total.toLocaleString('pt-BR', { minimumFractionDigits: 2 });
        body.appendChild(tr);
        document.getElementById('tr-costs').hidden = false;
      }
      if (d.money.note) {
        var n = document.getElementById('tr-money-note');
        n.textContent = d.money.note; n.hidden = false;
      }
      var since = d.since ? new Date(d.since).toLocaleDateString('pt-BR', { month: 'long', year: 'numeric' }) : null;
      document.getElementById('tr-updated').textContent = 'Números de ' + new Date(d.updated_at).toLocaleString('pt-BR', { dateStyle: 'short', timeStyle: 'short' }) + (since ? ' · CitySpots desde ' + since : '') + '.';
      status.hidden = true;
      document.getElementById('tr').hidden = false;
    }).catch(function () {
      status.className = 'tr-err';
      status.textContent = 'Não foi possível carregar os números agora. Tente de novo em alguns minutos.';
    });
  })();
</script>
