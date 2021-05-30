<template>
  <main class="home">
    <section class="home-content">
      <div class="home-title">
        <div class="home-title__box">
          <h1>ISSO DIZ MUITO</h1>
          <h2>Se faz alguém, nem que seja uma única pessoa, se sentir mal, não deveria caber na nosso vocabulário. O que se tornou popular há alguns anos, pode ser ofensivo hoje. O que era só uma piada ontem, pode pode ser um símbolo de homofobia, transfobia, racismo, falta de consciência de classe, xenofobia, gordofobia ou capacitismo.</h2>
        </div>
      </div>
      <div class="home-snippet">
        <ul class="home-snippet__list">
          <li>
            <h3>"Homossexualismo"</h3>
            <p>As duas palavras, segundo o dicionário, estão corretas. Mas, você sabia que o prefixo ”-ismo” é usado também para designar doenças?</p>
          </li>
          <li>
            <h3>"Dar uma de joão-sem-braço"</h3>
            <p>Uma pessoa que se esquiva de fazer algo dando desculpas que não justificam é bem diferente de uma pessoa que não faz determinada ação por uma deficiência, certo?</p>
          </li>
        </ul>
      </div>
    </section>
    <footer>Juliana Bezerra • Todos os direitos reservados • 2020 - 2021</footer>
  </main>
</template>

<script>
export default {}
</script>

<style>
.home {
  height: 100vh;
}

.home-content {
  align-items: center;
  box-sizing: border-box;
  display: grid;
  grid-template-columns: 50% 50%;
  height: calc(100vh - 40px);
}

.home-title__box {
  background-color: #363636;
  padding: 120px;
}

.home-title__box h1 {
  color: #EB8762;
  font-size: 72px;
}

.home-title__box h2 {
  color: #ffffff;
  font-size: 18px;
  font-weight: 400;
}

.home-snippet {
  margin: 12px 64px;
}

.home-snippet__list {
  border-left: 2px solid #363636;
}

.home-snippet__list h3 {
  font-style: italic;
}

footer {
  color: #808080;
  font-size: 14px;
  text-align: center;
}
</style>
