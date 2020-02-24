<template>
  <main>
    <h1>Project to Make an Impact on Future Generations</h1>

    <h2>Topics</h2>

    <ul>
      <li v-for="topic in topics" :key="topic.id">
        <g-link :to="topic.path">{{topic.name}}</g-link>
      </li>
    </ul>
  </main>
</template>

<page-query>
query Topics {
  allFireTopics {
    edges {
      node {
        id
        name
        path
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: "Home"
  },
  computed: {
    topics() {
      return (
        this.$page.allFireTopics.edges &&
        this.$page.allFireTopics.edges.map(e => e.node)
      );
    }
  }
};
</script>
