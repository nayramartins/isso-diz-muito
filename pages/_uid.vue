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
          <h3>{{ $prismic.asText(document.data.sidebar_title) }}</h3>

          <prismic-rich-text :field="document.data.replace_options" />
        </div>
      </aside>
      <section class="generic-page__content">
        <h2>"{{ $prismic.asText(document.data.title) }}"</h2>

        <prismic-rich-text :field="document.data.description" />
    </section>
    </section>
    <footer>Juliana Bezerra • Todos os direitos reservados • 2020 - 2021</footer>
	</main>
</template>

<script>
export default {
  async asyncData({ $prismic, params, error }) {
    const document = await $prismic.api.getByUID('page', params.uid)

    if (document) {
      return { document }
    } else {
      error({ statusCode: 404, message: 'Page not found' })
    }
  }
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