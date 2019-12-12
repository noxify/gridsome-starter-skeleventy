<template>
  <Layout>
    <section id="container-centre" class="column centre flex-1">
      <h1
        class="page-title text-purple-900 text-3xl md:text-center md:text-5xl mb-16 lg:mb-24 lg:text-6xl"
      >Tag — {{ $page.tag.title }}</h1>
      <div class="posts">
        <article
          class="text-gray-500 mb-8 pb-8 border-b border-gray-200"
          v-for="element in $page.tag.belongsTo.edges"
          :key="element.node.id"
        >
          <h2 class="text-4xl mb-3">
            <g-link
              class="block text-pink-500 hover:text-purple-900"
              :to="element.node.path"
            >{{ element.node.title }}</g-link>
          </h2>
          <time :datetime="element.node.datetime">{{ element.node.humanTime}}</time>
        </article>
      </div>
    </section>
  </Layout>
</template>


<page-query>
  query($id: ID!) {
    
    
    tag(id: $id) {
      title
      belongsTo {
        edges {
          node {
            ... on Blog {
              id
              title
              path 
              humanTime : created(format:"Do MMMM YYYY")
              datetime : created(format:"ddd MMM DD YYYY hh:mm:ss zZ")
            }
          }
        }
      }
    }
    
  }
</page-query>

<script>
export default {
  metaInfo: {
    title: "Tags"
  }
};
</script>
