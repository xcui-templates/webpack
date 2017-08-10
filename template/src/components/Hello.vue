<template>
  <div class="hello">
    <h1>\{{ greeting }}</h1>
    <ul>
      <li>
        <x-button type="primary" @click="welcome"> Hello World </x-button>
      </li>
      <li>
        Xcui is a Vue.js 2.x desktop components collection.
      </li>
      <li>
        To learn more about xcui, visit
        <a :href="docsURL" target="_blank">
          \{{ humanizeURL(docsURL) }}
        </a>
      </li>
      <li>
        Github:
        <a :href="docsURL" target="_blank">
          \{{ humanizeURL(repoURL) }}
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data{{#unless_eq lintConfig "airbnb"}} {{/unless_eq}}() {
    return {
      greeting: 'Welcome to Your Vue.js & xcui App',
      docsURL: 'https://wmfe.github.io/xcui/',
      repoURL: 'https://github.com/wmfe/xcui'{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
    }{{#if_eq lintConfig "airbnb"}};{{/if_eq}}
  },
  methods: {
    humanizeURL(url) {
      return url
        .replace(/^https?:\/\//, '')
        .replace(/\/$/, ''){{#if_eq lintConfig "airbnb"}};{{/if_eq}}
    },
    welcome() {
      this.$Message.info('Hello World!'){{#if_eq lintConfig "airbnb"}};{{/if_eq}}
    }
  }{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
}{{#if_eq lintConfig "airbnb"}};{{/if_eq}}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: block;
  margin: 15px;
}

a {
  color: #42b983;
}
</style>
