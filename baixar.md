---
layout: default
title: Baixar o app
permalink: /baixar/
---

<style>
  .dl-hero { text-align: center; padding: 8px 0 4px; }
  .dl-hero p { color: var(--muted); margin: 6px 0 22px; }
  .dl-btn {
    display: inline-flex; align-items: center; gap: 10px; background: #6C63FF; color: #fff !important;
    text-decoration: none; font-weight: 700; font-size: 18px; padding: 16px 28px; border-radius: 14px;
    box-shadow: 0 10px 30px rgba(108, 99, 255, .35);
  }
  .dl-btn:hover { background: #7c74ff; }
  .dl-meta { margin-top: 12px; font-size: 13px; color: var(--muted); min-height: 20px; }
  .dl-qr { display: none; margin: 28px auto 0; width: max-content; text-align: center; font-size: 13px; color: var(--muted); }
  .dl-qr img { width: 160px; height: 160px; border-radius: 12px; background: #fff; padding: 8px; display: block; margin: 0 auto 8px; }
  @media (min-width: 820px) { .dl-qr { display: block; } }
  .steps { counter-reset: step; list-style: none; padding: 0; }
  .steps li { counter-increment: step; position: relative; padding: 12px 14px 12px 52px; margin: 10px 0; background: var(--surface); border: 1px solid var(--border); border-radius: 12px; }
  .steps li::before {
    content: counter(step); position: absolute; left: 14px; top: 12px; width: 26px; height: 26px; border-radius: 50%;
    background: rgba(108, 99, 255, .2); color: var(--purple); font-weight: 800; font-size: 14px; text-align: center; line-height: 26px;
  }
  .note { background: var(--surface); border: 1px solid var(--border); border-left: 3px solid var(--gold); border-radius: 0 12px 12px 0; padding: 12px 16px; margin: 16px 0; }
</style>

<div class="dl-hero">
  <p>Beta fechado para Android · gratuito</p>
  <a class="dl-btn" id="dl" href="https://github.com/userm4c/cityspots-releases/releases/latest/download/CitySpots.apk">
    {% include icons/download.svg %} Baixar para Android
  </a>
  <div class="dl-meta" id="meta">Versão mais recente · Android 7.0 ou mais novo</div>
  <div class="dl-qr">
    <img src="{{ site.baseurl }}/assets/qr-baixar.png" alt="QR code desta página">
    Está no computador? Aponte a câmera do celular.
  </div>
</div>

## Como instalar

<ol class="steps">
  <li><strong>Baixe o arquivo</strong> no botão acima, pelo navegador do celular (Chrome, por exemplo). Ele se chama <code>CitySpots.apk</code>.</li>
  <li><strong>Abra o arquivo</strong> quando o download terminar (pela notificação ou na pasta <em>Downloads</em>).</li>
  <li>Se o Android pedir, <strong>permita instalar apps desta fonte</strong>: toque em <em>Configurações</em>, ative <em>Permitir desta fonte</em> e volte.</li>
  <li>Toque em <strong>Instalar</strong>. Se aparecer um aviso do <em>Play Protect</em> dizendo que o app é desconhecido, toque em <em>Mais detalhes → Instalar mesmo assim</em>: isso acontece com todo app que ainda não está na Play Store.</li>
  <li><strong>Abra o CitySpots</strong> e crie sua conta.</li>
</ol>

<div class="note">
  <strong>Por que não está na Play Store?</strong> O CitySpots está em teste fechado. Por enquanto, a instalação é por este arquivo, publicado só aqui. Não baixe o app de outros sites.
</div>

## Entrando no beta

- **Com código de convite** (algum membro te passou um <code>CS-XXXX-XXXX</code>): use no cadastro e a conta já entra aprovada.
- **Sem convite:** crie a conta normalmente. Ela fica aguardando a aprovação da equipe, e você recebe o acesso assim que for aprovada.
- É preciso ter **13 anos ou mais**. De 13 a 17 anos, com autorização do responsável.

## Atualizações

O próprio app avisa quando sai uma versão nova e baixa a atualização (também dá para conferir em *Configurações → Atualizações*). Você não precisa voltar a este site.

## Precisa de ajuda?

- No app: **Configurações → Ajuda e suporte**.
- Não consegue entrar? Na tela de login, toque em **Precisa de ajuda? Fale com o suporte**.

Ao usar o CitySpots, você concorda com os [Termos de Uso]({{ site.baseurl }}/termos/), a [Política de Privacidade]({{ site.baseurl }}/privacidade/) e as [Diretrizes da Comunidade]({{ site.baseurl }}/diretrizes/).

<script>
  // Versão, tamanho e data da versão mais recente (API pública do GitHub).
  fetch('https://api.github.com/repos/userm4c/cityspots-releases/releases/latest')
    .then(function (r) { return r.ok ? r.json() : null })
    .then(function (rel) {
      if (!rel) return
      var apk = (rel.assets || []).filter(function (a) { return a.name === 'CitySpots.apk' })[0]
      var when = new Date(rel.published_at).toLocaleDateString('pt-BR')
      var size = apk ? ' · ' + Math.round(apk.size / 1048576) + ' MB' : ''
      document.getElementById('meta').textContent = 'Versão ' + String(rel.tag_name).replace(/^v/, '') + size + ' · publicada em ' + when + ' · Android 7.0 ou mais novo'
    })
    .catch(function () {})
</script>
