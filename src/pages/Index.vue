<template>
    <Layout>
        <section>
            <g-link
                v-for="edge in $page.allProduct.edges"
                :key="edge.node.id"
                :to="edge.node.path"
                class="product"
            >
                <p>{{ edge.node.title }}</p>
            </g-link>
        </section>
    </Layout>
</template>

<!-- Query from local GraphQL data layer. -->
<page-query>
query Products {
      allProduct {
        edges {
          node {
            id,
            title,
            path,
            content,
            
          }
        }
      }
    }

</page-query>

<script>
export default {
    metaInfo: {
        title: "Hello, world!",
    },
};
</script>

<style>
.home-links a {
    margin-right: 1rem;
}
</style>
