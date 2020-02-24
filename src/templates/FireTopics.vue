<template>
  <main>
    <h1>{{topic.name}}</h1>
  </main>
</template>

<page-query>
query Topic ($id: ID!) {
  topic: fireTopics (id: $id) {
    id
    name
  }
}
</page-query>

<script>
export default {
  metaInfo() {
    return {
      title: this.topic.name
    };
  },
  computed: {
    topic() {
      return this.$page.topic;
    },
  },
};
</script>
