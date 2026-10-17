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
  <div class="tr-card"><div class="tr-num" data-k="moderation.removed"></div><div class="tr-label">terminaram com o conteúdo removido</div></div>
  <div class="tr-card"><div class="tr-num" data-k="moderation.kept"></div><div class="tr-label">terminaram com o conteúdo mantido</div></div>
  <div class="tr-card"><div class="tr-num" data-k="moderation.open"></div><div class="tr-label">em análise agora</div></div>
  <div class="tr-card"><div class="tr-num" data-k="moderation.users_suspended"></div><div class="tr-label">contas suspensas hoje</div></div>
  <div class="tr-card"><div class="tr-num" data-k="moderation.users_banned"></div><div class="tr-label">contas banidas</div></div>
  <div class="tr-card"><div class="tr-num" data-k="moderation.spots_deactivated"></div><div class="tr-label">spots desativados pela equipe</div></div>
</div>

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
