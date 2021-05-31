<template>
  <main class="home">
    <section class="home-content">
      <div class="home-title">
        <div class="home-title__box">
          <h1>ISSO DIZ MUITO</h1>
          <h2>Se faz alguém, nem que seja uma única pessoa, se sentir mal, não deveria caber no nosso vocabulário. O que se tornou popular há alguns anos, pode ser ofensivo hoje. O que era só uma piada ontem, pode pode ser um símbolo de homofobia, transfobia, racismo, falta de consciência de classe, xenofobia, gordofobia ou capacitismo.</h2>
        </div>
      </div>
      <div class="home-snippet">
        <ul class="home-snippet__list">
          <li v-for="result in document.results" :key="result.id">
            <h3>"{{ $prismic.asText(result.data.title) }}"</h3>
            <p>{{ result.data.home_snippet }}</p>

            <NuxtLink :to="result.uid" class="home-snippet__list--see-more">ver mais >></NuxtLink>
          </li>
        </ul>
      </div>
    </section>
    <footer>Juliana Bezerra • Todos os direitos reservados • 2020 - 2021</footer>
  </main>
</template>

<script>
export default {
  async asyncData({ $prismic, _, error }) {
    const document = await $prismic.api.query(
      $prismic.predicates.at('document.type', 'page')
    )

    console.log(document)

    if (document) {
      return { document }
    } else {
      error({ statusCode: 404, message: 'Page not found' })
    }
  }
}
</script>

<style>
.home {
  background-color: #ec9372;
  height: 100vh;
}

.home-content {
  align-items: center;
  box-sizing: border-box;
  display: grid;
  grid-template-columns: 50% 50%;
  height: calc(100vh - 50px);
}

.home-title {
    background-image: url('../assets/images/dots-white-bg.svg'),
      url('../assets/images/dots-orange-dark-bg.svg');
    background-position: 0 580px, right 30px;
    height: 100%;
    background-repeat: no-repeat;
    display: flex;
    align-items: center;
}

.home-title__box {
  background-color: #363636;
  border-radius: 0 10px 10px 0;
  padding: 112px;
}

.home-title__box h1 {
  color: #EB8762;
  font-size: 72px;
  font-weight: 700;
  line-height: 1;
  margin-bottom: 24px;
}

.home-title__box h2 {
  color: #ffffff;
  font-size: 16px;
  font-weight: 400;
  line-height: 1.5;
}

.home-snippet {
  margin: 12px 112px 12px 64px;
}

.home-snippet__list {
  border-left: 2px solid #363636;
  max-height: 50vh;
  overflow: auto;
}

.home-snippet__list::-webkit-scrollbar {
  background: transparent;
  width: 4px;
}

.home-snippet__list::-webkit-scrollbar-thumb {
  background: #c36e4f;
  border-radius: 12px;
}

.home-snippet__list h3 {
  font-size: 18px;
  font-style: italic;
  font-weight: 700;
  margin-bottom: 8px;
  text-transform: uppercase;
}

.home-snippet__list li {
  padding: 24px 0;
  position: relative;
}

.home-snippet__list li::after {
  background-image: url('../assets/images/dot-single.svg');
  background-repeat: no-repeat;
  bottom: -12px;
  content: '';
  left: 50%;
  margin-left: -26px;
  height: 4px;
  position: absolute;
  width: 52px;
}

.home-snippet__list--see-more {
  border-bottom: 2px solid #000000;
  color: #000000;
  display: inline-block;
  font-family: 'Source Sans Pro', sans-serif;
  font-size: 14px;
  font-weight: 600;
  margin-top: 16px;
  text-decoration: none;
  text-transform: uppercase;
}

footer {
  color: #2F2F2F;
  font-size: 14px;
  padding-bottom: 32px;
  text-align: center;
}

@media (max-width: 1080px) {
  .home {
    height: auto;
  }

  .home-content {
    grid-template-columns: 100%;
    height: auto;
  }
}
</style>
