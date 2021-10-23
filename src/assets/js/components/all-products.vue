<template>
  <div id>
    <h1>All Products</h1>

    <router-link :to="{ name: 'create_product' }" class="btn btn-primary">Create Product</router-link>

    <table class="table table-hover">
      <thead>
        <tr>
          <td>ID</td>
          <td>Name</td>
          <td>Price</td>
          <td>Actions</td>
          <td>Hello</td>
        </tr>
      </thead>

      <tbody>
        <tr v-for="product in products" :key="product">
          <td>{{ product.id }}</td>
          <td>{{ product.name }}</td>
          <td>{{ product.price }}</td>
          <td>
            <p>Actions</p>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>

export default {
  data() {
    return {
      products: [],
      originProducts: []
    }
  },
  created: function () {
    this.ProductData();
  },
  methods: {
    ProductData: function () {
      this.$http.get('http://localhost:3000/api/products').then((response => {
        this.products = response.body;
        this.originProducts = this.products;
      }))
    }
  },
}
</script>
