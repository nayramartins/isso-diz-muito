<template>
	<main class="generic-page">
    <section class="generic-page__main">
      <aside class="generic-page__sidebar">
        <h1>
          <NuxtLink to="/">
            Isso diz <br /> muito
          </NuxtLink>
        </h1>

        <div class="generic-page__sidebar--list">
          <h3>prefira falar/escrever</h3>

          <ul>
            <li>Homossexualidade</li>
          </ul>
        </div>
      </aside>
      <section class="generic-page__content">
        <h2>"Homossexualismo"</h2>

        <h3>Por que não usar essa expressão?</h3>
        <p>As duas palavras, segundo o dicionário, estão corretas. Mas, você sabia que o prefixo ” -ismo” é usado para designar doenças? Infelizmente, antigamente a homossexualidade já foi considerada uma doença psíquica. Mas, em 1973 ela foi retirada do CID (Código Internacional de Doenças) e, em 1990, riscada da lista da OMS (Organização Mundial de Saúde). Assim, quando a palavra ”homossexualismo” foi cunhada, ela veio com essas conotações patológicas. Sabemos também que o prefixo “ - ismo” não tem essa única função. De toda forma, é como sempre trazemos aqui para as nossas análise: se tem um significado histórico tão doloroso para algumas pessoas e, se temos alternativas a essa palavra, por que não adotá -las no dia a dia?</p>
    </section>
    </section>
    <footer>Juliana Bezerra • Todos os direitos reservados • 2020 - 2021</footer>
	</main>
</template>

<script>
export default {

}
</script>

<style>
.generic-page {
  background-color: #ec9372;
  height: 100vh;
}

.generic-page__main {
  display: grid;
  gap: 72px;
  grid-template-columns: 420px auto;
  height: calc(100vh - 50px);
  padding: 0 112px;
}

.generic-page__sidebar {
  margin-top: 72px;
}

.generic-page__sidebar h1 a {
  background-color: #2F2F2F;
  border-radius: 5px;
  color: #EB8762;
  display: inline-block;
  font-size: 36px;
  margin-bottom: 74px;
  padding: 22px;
  text-decoration: none;
  text-transform: uppercase;
  width: 100%;
}

.generic-page__sidebar--list li {
  color: #363636;
  font-weight: 700;
  padding-bottom: 8px;
}

.generic-page__sidebar--list h3 {
  font-size: 26px;
}

.generic-page__sidebar--list li::before {
  content: '>';
  margin-right: 12px;
}

.generic-page__content {
  margin-top: 280px;
  line-height: 1.5;
}

.generic-page__content h2 {
  margin-bottom: 16px;
  font-style: italic;
}

.generic-page__content h3 {
  font-size: 16px;
  margin: 32px 0 16px;
  text-transform: uppercase;
}

@media (max-width: 1080px) {
  .generic-page,
  .generic-page__main {
    height: auto;
  }

  .generic-page__main {
    grid-template-columns: 100%;
    padding: 0 56px;
  }

  .generic-page__content {
    margin-top: 0;
  }

  .generic-page footer {
    margin-top: 64px;
  }
}
</style>