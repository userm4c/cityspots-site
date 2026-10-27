---
layout: default
title: Início
permalink: /
---

<style>
  main { max-width: 1000px; }
  .home h2 { border-top: 0; text-align: center; font-size: 26px; margin: 0 0 6px; text-wrap: balance; }
  .home .lead { text-align: center; color: var(--muted); max-width: 620px; margin: 0 auto 24px; }
  .home section { padding: 44px 0; border-top: 1px solid var(--border); }
  .home section:first-child { border-top: 0; padding-top: 8px; }

  .hero { max-width: 720px; }
  .hero h1 { font-size: clamp(30px, 6vw, 44px); line-height: 1.15; margin: 0 0 14px; text-wrap: balance; }
  .hero h1 em { font-style: normal; color: var(--gold); }
  .hero p { font-size: 18px; margin: 0 0 22px; max-width: 34em; }
  .cta-row { display: flex; flex-wrap: wrap; gap: 12px; align-items: center; }
  .btn { display: inline-flex; align-items: center; gap: 10px; text-decoration: none; font-weight: 700; border-radius: 14px; padding: 13px 22px; font-size: 17px; }
  .btn-main { background: #6C63FF; color: #fff; }
  .btn-main:hover { background: #5a52e0; }
  .btn-ghost { border: 1px solid var(--border); color: var(--text); }
  .btn-ghost:hover { border-color: var(--gold); color: var(--gold); }
  .small { font-size: 13px; color: var(--muted); }
  .stats { display: flex; flex-wrap: wrap; gap: 6px 22px; margin-top: 18px; color: var(--muted); font-size: 15px; }
  .stats b { color: var(--gold); font-size: 20px; }

  .steps { list-style: none; padding: 0; margin: 0; display: grid; grid-template-columns: repeat(4, 1fr); gap: 14px; counter-reset: step; }
  .steps li { margin: 0; background: var(--surface); border: 1px solid var(--border); border-radius: 16px; padding: 18px; counter-increment: step; position: relative; }
  .steps li::before { content: counter(step); position: absolute; top: 14px; right: 16px; font-size: 32px; font-weight: 800; color: var(--border); line-height: 1; }
  .steps .ti { width: 28px; height: 28px; color: var(--gold); }
  .steps h3 { margin: 10px 0 6px; font-size: 18px; }
  .steps p { margin: 0; font-size: 15px; color: var(--muted); }

  .cards { display: grid; grid-template-columns: repeat(3, 1fr); gap: 14px; }
  .card { background: var(--surface); border: 1px solid var(--border); border-radius: 16px; padding: 18px; min-width: 0; }
  .card .ti { width: 26px; height: 26px; color: var(--purple); }
  .care .card .ti { color: #4ade80; }
  .card h3 { margin: 8px 0 6px; font-size: 17px; }
  .card p { margin: 0; font-size: 15px; color: var(--muted); }

  .care-band { margin: 22px 0 0; background: linear-gradient(135deg, rgba(74, 222, 128, .12), rgba(108, 99, 255, .12)); border: 1px solid var(--border); border-radius: 16px; padding: 18px; text-align: center; }
  .care-band .nums { display: flex; flex-wrap: wrap; justify-content: center; gap: 8px 28px; margin-top: 6px; }
  .care-band b { display: block; font-size: 26px; color: #4ade80; }
  .more { text-align: center; margin-top: 22px; }

  .promises { display: grid; grid-template-columns: repeat(3, 1fr); gap: 14px; }
  .promise { border-left: 3px solid var(--gold); padding: 6px 0 6px 16px; }
  .promise strong { display: block; font-size: 17px; margin-bottom: 4px; }
  .promise span { color: var(--muted); font-size: 15px; }

  .faq { max-width: 720px; margin: 0 auto; }
  .faq details { border-bottom: 1px solid var(--border); padding: 14px 0; }
  .faq summary { cursor: pointer; font-weight: 700; color: var(--heading); }
  .faq details p { margin: 10px 0 0; color: var(--muted); }

  .final { text-align: center; }
  .final .cta-row { justify-content: center; margin-top: 18px; }
  .docs { display: flex; flex-wrap: wrap; justify-content: center; gap: 6px 18px; margin-top: 26px; font-size: 14px; }

  @media (max-width: 820px) {
    .steps { grid-template-columns: repeat(2, 1fr); }
    .cards, .promises { grid-template-columns: 1fr 1fr; }
  }
  @media (max-width: 560px) {
    .steps, .cards, .promises { grid-template-columns: 1fr; }
  }
</style>

<div class="home">

<section class="hero">
  <div>
    <h1>Descubra os lugares especiais da sua cidade. <em>Vá até eles. Ajude a cuidar.</em></h1>
    <p>O mirante escondido, o grafite bonito, o letreiro histórico, a praça que pouca gente conhece. No CitySpots, cada lugar desses é um <strong>spot</strong>, encontrado por quem esteve lá de verdade.</p>
    <div class="cta-row">
      <a class="btn btn-main" href="{{ site.baseurl }}/baixar/">{% include icons/download.svg %} Baixar o app</a>
      <a class="btn btn-ghost" href="#como-funciona">Como funciona</a>
    </div>
    <p class="small" style="margin-top:12px">Grátis · Android · em teste fechado (beta)</p>
    <div class="stats" id="stats" hidden>
      <span><b data-k="community.spots"></b> spots</span>
      <span><b data-k="community.cities"></b> cidades</span>
    </div>
  </div>
</section>

<section id="como-funciona">
  <h2>Como funciona</h2>
  <p class="lead">Nada de trapaça de casa: no CitySpots, só conta o que você viveu no lugar.</p>
  <ol class="steps">
    <li>{% include icons/map-2.svg %}<h3>Descubra</h3><p>O mapa mostra os spots perto de você, com fotos de quem já foi, horários e o nível de raridade: comum, incomum, raro ou lendário.</p></li>
    <li>{% include icons/map-pin.svg %}<h3>Vá até lá</h3><p>O check-in só vale no local: o GPS confirma que você está a até 50 metros. Em lugar fechado, vale o QR code do spot. Tire uma foto e pronto.</p></li>
    <li>{% include icons/camera.svg %}<h3>Compartilhe</h3><p>Achou um lugar que merece ser conhecido? Crie um spot estando lá. Pessoas de confiança da cidade confirmam que ele existe antes de ele entrar no mapa.</p></li>
    <li>{% include icons/trophy.svg %}<h3>Evolua</h3><p>Cada visita, spot e ajuda vale XP. São 50 níveis, de <em>Passante</em> a <em>A Origem</em>, títulos para colecionar e um passaporte que ganha carimbos.</p></li>
  </ol>
</section>

<section class="care">
  <h2>A cidade também é sua</h2>
  <p class="lead">Explorar a cidade dá vontade de cuidar dela. No CitySpots, cuidar também conta, e a cidade inteira vê o que foi feito.</p>
  <div class="cards">
    <div class="card">{% include icons/heart-handshake.svg %}<h3>Mutirões</h3><p>Alguém marca uma limpeza num lugar que precisa, a cidade se junta e todo mundo vê a foto do antes e do depois. Comércios apoiam com materiais, água e lanche, nunca com dinheiro.</p></div>
    <div class="card">{% include icons/trash.svg %}<h3>Pontos de cuidado</h3><p>Viu lixo acumulado, um buraco ou um poste apagado? Marque no mapa, sem o seu nome. Outras pessoas confirmam e o ponto fica resolvido quando alguém cuida dele.</p></div>
    <div class="card">{% include icons/shield-heart.svg %}<h3>Guardiões</h3><p>Adote um lugar que você ama: faça vistorias de vez em quando e avise quando algo não estiver bem.</p></div>
    <div class="card">{% include icons/leaf.svg %}<h3>Pontos do bem</h3><p>Geladeiras solidárias, bibliotecas livres, bebedouros, banheiros, pontos de coleta e de troca: lugares que ajudam alguém, marcados no mapa. E quem leva um lixo embora de um spot também é lembrado.</p></div>
    <div class="card">{% include icons/plant-2.svg %}<h3>Lugares frágeis</h3><p>Dunas, ninhos, recifes, cavernas e áreas protegidas: o app mostra onde é preciso visitar com cuidado, com as regras e a época sensível de cada lugar.</p></div>
    <div class="card">{% include icons/book.svg %}<h3>Memória da cidade</h3><p>Conte a lenda do bairro ou o nome antigo de uma rua, e mostre a foto antiga de um lugar ao lado da de hoje. A história da cidade fica guardada por quem a viveu.</p></div>
  </div>
  <div class="care-band" id="care-band" hidden>
    <strong>O que as cidades já fizeram juntas</strong>
    <div class="nums">
      <span><b data-k="care.mutiroes"></b> mutirões</span>
      <span><b data-k="care.bags"></b> sacos de lixo</span>
      <span><b data-k="care.care_resolved"></b> pontos resolvidos</span>
      <span><b data-k="care.adopted_places"></b> lugares adotados</span>
    </div>
  </div>
  <p class="more"><a class="btn btn-ghost" href="{{ site.baseurl }}/comunidade/">Conheça a comunidade</a>&nbsp; <a href="{{ site.baseurl }}/patrocine/">Tem um comércio? Apoie um mutirão</a></p>
</section>

<section>
  <h2>Para explorar</h2>
  <p class="lead">Sempre tem um lugar novo, mesmo na cidade onde você nasceu.</p>
  <div class="cards">
    <div class="card">{% include icons/route.svg %}<h3>Trilhas</h3><p>Roteiros a pé ligando vários spots, com o caminho pelas ruas. Complete todos e ganhe a conquista.</p></div>
    <div class="card">{% include icons/bolt.svg %}<h3>Acontecendo agora</h3><p>A feira de domingo, o artista de rua, o pôr do sol no mirante: alguns spots só existem em certas horas, e o app avisa quando estão rolando.</p></div>
    <div class="card">{% include icons/dice-5.svg %}<h3>Me surpreenda</h3><p>Um spot sorteado por dia, perto de você e que você ainda não visitou. E desafios novos toda segunda-feira.</p></div>
    <div class="card">{% include icons/map-2.svg %}<h3>Conhecimento popular</h3><p>Relatos de lugares esquecidos, com uma área aproximada no mapa. Quem encontra cria o spot, e quem contou ganha junto.</p></div>
    <div class="card">{% include icons/brand-whatsapp.svg %}<h3>Junto com as redes</h3><p>Viu um lugar no Instagram ou no TikTok? Guarde no app com o link do post. Chame os amigos para um rolê por um link que abre até sem o app.</p></div>
    <div class="card">{% include icons/flame.svg %}<h3>Seu passaporte</h3><p>Seu perfil é um passaporte: carimbos de cada estado, vistos de cada país, títulos, selos e as cores que você escolher.</p></div>
  </div>
</section>

<section>
  <h2>O que prometemos</h2>
  <p class="lead">Escrito no nosso <a href="{{ site.baseurl }}/manifesto/">Manifesto</a>, que não muda em silêncio.</p>
  <div class="promises">
    <div class="promise"><strong>Você vê o que acontece</strong><span>O feed é em ordem cronológica: quem você segue e o que acontece perto. Nenhum critério escondido escolhe por você.</span></div>
    <div class="promise"><strong>Seus dados não estão à venda</strong><span>Nem para anunciantes, nem para ninguém. Você pode baixar tudo e ir embora quando quiser.</span></div>
    <div class="promise"><strong>Moderação com regras públicas</strong><span>Toda decisão da equipe fica no <a href="{{ site.baseurl }}/transparencia/">registro público</a>, e você pode contestar pelo app.</span></div>
  </div>
</section>

<section>
  <h2>Perguntas frequentes</h2>
  <div class="faq">
    <details><summary>O CitySpots é de graça?</summary><p>Sim, e vai continuar sendo. O app se sustenta com anúncios e parcerias, nunca vendendo os seus dados.</p></details>
    <details><summary>Tem para iPhone?</summary><p>Ainda não. Por enquanto o CitySpots é só para Android, em teste fechado (beta).</p></details>
    <details><summary>Por que eu preciso estar no lugar?</summary><p>Porque é isso que faz o mapa ser confiável: cada spot e cada check-in vêm de alguém que esteve lá de verdade. Em lugares fechados, onde o GPS falha, o check-in pode ser pelo QR code do spot.</p></details>
    <details><summary>Quem aprova os spots novos?</summary><p>Membros de confiança da própria cidade confirmam que o lugar existe e que as informações estão certas. Onde ainda não há gente suficiente, a equipe do CitySpots revisa.</p></details>
    <details><summary>Minha localização fica pública?</summary><p>Não. O app usa a sua localização só com ele aberto, para mostrar spots perto e confirmar o check-in. Os outros veem o spot, nunca o ponto exato onde você estava, e você escolhe quem vê os seus check-ins. Rostos nas fotos são desfocados automaticamente.</p></details>
    <details><summary>Preciso de idade mínima?</summary><p>Sim: 13 anos. Entre 13 e 17 anos, com autorização do responsável.</p></details>
    <details><summary>Como ajudo no meu bairro?</summary><p>Marque pontos de cuidado, participe ou proponha um mutirão, adote um lugar como guardião ou registre um ponto do bem. Tudo isso está na aba Comunidade do app.</p></details>
  </div>
</section>

<section class="final">
  <h2>Bora conhecer a sua cidade de outro jeito?</h2>
  <div class="cta-row">
    <a class="btn btn-main" href="{{ site.baseurl }}/baixar/">{% include icons/download.svg %} Baixar o app</a>
  </div>
  <div class="docs">
    <a href="{{ site.baseurl }}/manifesto/">Manifesto</a>
    <a href="{{ site.baseurl }}/transparencia/">Transparência</a>
    <a href="{{ site.baseurl }}/comunidade/">Comunidade</a>
    <a href="{{ site.baseurl }}/patrocine/">Patrocine um mutirão</a>
    <a href="{{ site.baseurl }}/termos/">Termos de Uso</a>
    <a href="{{ site.baseurl }}/privacidade/">Política de Privacidade</a>
    <a href="{{ site.baseurl }}/diretrizes/">Diretrizes da Comunidade</a>
  </div>
</section>

</div>

<script>
  (function () {
    var API = 'https://api.cityspots.com.br';
    function get(o, path) { return path.split('.').reduce(function (a, k) { return a == null ? a : a[k]; }, o); }
    fetch(API + '/public/transparency').then(function (r) { if (!r.ok) throw new Error(r.status); return r.json(); }).then(function (d) {
      document.querySelectorAll('[data-k]').forEach(function (el) {
        el.textContent = Number(get(d, el.getAttribute('data-k')) || 0).toLocaleString('pt-BR');
      });
      if (d.community && d.community.spots > 0) document.getElementById('stats').hidden = false;
      // Números de cuidado só aparecem quando já há algo para mostrar.
      var c = d.care || {};
      if ((c.mutiroes || 0) + (c.care_resolved || 0) + (c.adopted_places || 0) > 0) document.getElementById('care-band').hidden = false;
    }).catch(function () {});
  })();
</script>
