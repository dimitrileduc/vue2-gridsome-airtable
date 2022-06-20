<template>
    <Layout>
        <h1>{{ $page.product.title }}</h1>
        <p>
            {{ $page.product.content }}
        </p>
    </Layout>
</template>

<script>
export default {
    metaInfo: {
        title: "Product",
    },
};
</script>

<!-- Query from local GraphQL data layer. -->
<page-query>
query Product ($path: String!) {
      product(path: $path) {
        id,
        title,
        path,
        content,
      }
    }

</page-query>
