<template>
  <div class="home">
    <NewsList :newsUrl="newsUrl"/>
  </div>
</template>

<script lang="ts">
import NewsList from '@/components/NewsList.vue';
import { Component, Prop, Vue } from 'vue-property-decorator';
import axios from 'axios';

@Component({
  components: {
    NewsList,
  },
})
export default class Home extends Vue {
  private get newsUrl() {
    return new URL(`${axios.defaults.baseURL}/api/news`);
  }
}
</script>

// https://newsapi.org/v2/everything?q=test&sortBy=publishedAt&apiKey=[key]
