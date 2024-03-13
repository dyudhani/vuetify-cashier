<template>
  <v-row>
    <v-col v-for="(product, index) in products" cols="2">
      <v-card :title="product.title">
        <v-card-actions>
          <v-img
            :src="require(`@/assets/images/products/${product.thumbnail}`)"
          >
          </v-img
        ></v-card-actions>
        <v-card-text align="center">
          {{ product.title }}
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      product: [
        {
          id: 1,
          title: 'Asus Zenfone',
          thumbnail: 'asus-zenfone.png',
          price: 909090,
          category: 1,
        },
        {
          id: 2,
          title: 'Canon EOS 700d',
          thumbnail: 'canon-eos-700d.png',
          price: 909090,
          category: 1,
        },
        {
          id: 3,
          title: 'Canon EOS 700d',
          thumbnail: 'canon-eos-750d.png',
          price: 909090,
          category: 1,
        },
        {
          id: 4,
          title: 'Iphone 6',
          thumbnail: 'iphone-6-silver.png',
          price: 909090,
          category: 1,
        },
        {
          id: 5,
          title: 'Lenovo A7000',
          thumbnail: 'Lenovo-A7000.png',
          price: 909090,
          category: 1,
        },
        {
          id: 6,
          title: 'LG 32',
          thumbnail: 'lg-32-led-tv-32LF550A.png',
          price: 909090,
          category: 1,
        },
        {
          id: 1,
          title: 'Asus Zenfone',
          thumbnail: 'asus-zenfone.png',
          price: 909090,
          category: 1,
        },
        {
          id: 1,
          title: 'Asus Zenfone',
          thumbnail: 'asus-zenfone.png',
          price: 909090,
          category: 1,
        },
        {
          id: 1,
          title: 'Asus Zenfone',
          thumbnail: 'asus-zenfone.png',
          price: 909090,
          category: 1,
        },
        {
          id: 1,
          title: 'Asus Zenfone',
          thumbnail: 'asus-zenfone.png',
          price: 909090,
          category: 1,
        },
      ],
    }
  },
}
</script>
