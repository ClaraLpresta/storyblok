<template>
  <div v-editable="blok">
    <component
      v-for="blok in blok.body"
      :key="blok._uid"
      :blok="blok"
      :is="blok.component"
    />
    <div class="container container-header" :style="{backgroundColor: blok.background[0].colors}" style="display: flex; align-items: center; width: 100vw">
      <div class="col-lg-6 col-md-6 col-xs-12">
        <div class="header-content-details">
          <h1 class="headings h1 font-weight-semibold header-title">
            {{blok.title}}
          </h1>

          <div class="primary-text sub2 header-description">
            <p>
              {{blok.description}}
            </p>
          </div>
        </div>

        <div class="header-buttons">
          <div class="container-buttons">
            <div class="prestashop-link primary-link">
              <a :href="blok.cta[0].link.url" target="">
                {{blok.cta[0].text}}
              </a>
            </div>
          </div>

          <!-- Example on download page (legal text and link) -->
        </div>
      </div>

      <div class="col-lg-6 col-md-6 col-xs-12">
        <div class="img-container">
          <img
            class="no-src lazyloaded"
            :src="blok.image.filename"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    blok: {
      type: Object,
      required: true
    }
  }
};
</script>

<style scoped>
  #homepage .container-header .headings {
      font-family: Montserrat,Helvetica,Verdana,sans-serif;
      font-size: 48px;
      line-height: 58px;
  }
</style>