<template>
  <Layout>
    <ul>
      <li
        v-for="category in $page.allStrapiCategory.edges"
        :key="category.node.id"
      >
        {{ category.node.name }}
        <ul>
          <li
            v-for="subcategory in category.node.subcategories"
            :key="subcategory.id"
          >
            <g-link :to="'subcategories/' + subcategory.id">{{
              subcategory.name
            }}</g-link>
          </li>
        </ul>
      </li>
    </ul>
  </Layout>
</template>

<page-query>
  query {
      allStrapiCategory {
        edges {
          node {
            id
            name
            subcategories {
              id
              name
            }
          }
        }
      }
    }
</page-query>
