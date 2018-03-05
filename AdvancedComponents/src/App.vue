<template>
  <div id="app">
    <div class="container">
      <div class="col-xs-12">
        <button @click="selectedComponent = 'appQuote'">Quote</button>
        <button @click="selectedComponent = 'appAuthor'">Author</button>
        <button @click="selectedComponent = 'appNew'">New</button>
        <hr>
        <p>{{ selectedComponent }}</p>
        <keep-alive>
          <component :is="selectedComponent">
            <p>Default Content</p>
          </component>
        </keep-alive>
        <!-- <app-quote>
          <h2 slot="title">{{ quoteTitle }}</h2>
          <p>A wonderful Quote !</p>
        </app-quote> -->
      </div>
    </div>
  </div>
</template>

<script>
import Quote from './components/Quote'
import Author from './components/Author'
import New from './components/New'

export default {
  data() {
    return {
      quoteTitle: 'The Quote',
      selectedComponent: 'appQuote'
    }
  },
  components: {
    appQuote: Quote,
    appAuthor: Author,
    appNew: New
  }
}
</script>

<style scoped>
  h2 {
    color: red;
  }
</style>
