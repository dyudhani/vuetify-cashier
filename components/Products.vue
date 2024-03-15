<template>
  <v-row>
    <v-row>
      <v-col cols="10">
        <v-autocomplete
          label="Products"
          placeholder="Start typing to search"
          :search-input.sync="search"
          :loading="isLoading"
          :items="itemsSearch"
          item-text="title"
          item-value="id"
          v-model="selectedSearch"
          return-object
        >
        </v-autocomplete>
      </v-col>
      <v-col cols="2">
        <v-menu>
          <template v-slot:activator="{ on: category }">
            <v-btn v-on="category" color="primary">Category</v-btn>
          </template>

          <v-list>
            <v-list-item-group v-model="categoryId">
              <v-list-item
                v-for="(category, index) in categories"
                :value="category.id"
                :disabled="category.id == categoryId"
                :key="index"
              >
                <v-list-item-title>{{ category.title }}</v-list-item-title>
              </v-list-item>
            </v-list-item-group>
          </v-list>
        </v-menu>
      </v-col>
    </v-row>

    <v-row>
      <v-col v-for="(product, index) in filteredProducts" cols="2" :key="index">
        <v-card :title="product.title" ripple="true">
          <v-card-actions>
            <v-img
              :src="require(`@/assets/images/products/${product.thumbnail}`)"
            >
            </v-img
          ></v-card-actions>
          <v-card-text align="center" class="product-title">
            {{ product.title }}
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      categoryId: false,
      categories: [
        {
          id: false,
          title: 'All',
        },
        {
          id: 1,
          title: 'Smartphones',
        },
        {
          id: 2,
          title: 'Camera',
        },
        {
          id: 3,
          title: 'Televisions',
        },
      ],
      products: [
        {
          id: 1,
          title: 'Asus Zenfone',
          thumbnail: 'asus-zenfone.png',
          price: 909090,
          categoryId: 1,
        },
        {
          id: 2,
          title: 'Canon EOS 700d',
          thumbnail: 'canon-eos-700d.png',
          price: 909090,
          categoryId: 2,
        },
        {
          id: 3,
          title: 'Canon EOS 700d',
          thumbnail: 'canon-eos-750d.png',
          price: 909090,
          categoryId: 2,
        },
        {
          id: 4,
          title: 'Iphone 6',
          thumbnail: 'iphone-6-silver.png',
          price: 909090,
          categoryId: 1,
        },
        {
          id: 5,
          title: 'Lenovo A7000',
          thumbnail: 'Lenovo-A7000.png',
          price: 909090,
          categoryId: 1,
        },
        {
          id: 6,
          title: 'lg-32-led-tv-32LF550A',
          thumbnail: 'lg-32-led-tv-32LF550A.png',
          price: 909090,
          categoryId: 3,
        },
        {
          id: 7,
          title: 'lg-led-tv32-32LF520A',
          thumbnail: 'lg-led-tv32-32LF520A.png',
          price: 909090,
          categoryId: 3,
        },
        {
          id: 8,
          title: 'mi-4i',
          thumbnail: 'mi-4i.png',
          price: 909090,
          categoryId: 1,
        },
        {
          id: 9,
          title: 'nikon-d3200',
          thumbnail: 'nikon-d3200.png',
          price: 909090,
          categoryId: 2,
        },
        {
          id: 10,
          title: 'nikon-d5200',
          thumbnail: 'nikon-d5200.png',
          price: 909090,
          categoryId: 2,
        },
        {
          id: 10,
          title: 'nikon-d5200',
          thumbnail: 'nikon-d5200.png',
          price: 909090,
          categoryId: 2,
        },
        {
          id: 10,
          title: 'nikon-d5200',
          thumbnail: 'nikon-d5200.png',
          price: 909090,
          categoryId: 2,
        },
        {
          id: 10,
          title: 'nikon-d5200',
          thumbnail: 'nikon-d5200.png',
          price: 909090,
          categoryId: 2,
        },
        {
          id: 14,
          title: 'nikon-d5200',
          thumbnail: 'nikon-d5200.png',
          price: 909090,
          categoryId: 2,
        },
        {
          id: 15,
          title: 'nikon-d5200',
          thumbnail: 'nikon-d5200.png',
          price: 909090,
          categoryId: 2,
        },
      ],
      search: null,
      isLoading: false,
      itemsSearch: [],
      selectedSearch: null,
    }
  },
  computed: {
    filteredProducts() {
      if (this.categoryId) {
        return this.products.filter((s) => s.categoryId == this.categoryId)
      } else if (this.selectedSearch) {
        return this.products.filter((s) => s.title == this.selectedSearch.title)
      }
      return this.products
    },
  },
  watch: {
    search(val) {
      this.isLoading = true

      setTimeout(() => {
        this.itemsSearch = this.products.filter((e) => {
          this.isLoading = false
          return e.title
        })
      }, 1000)
    },
  },
}
</script>

<style scoped>
.product-title {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>
