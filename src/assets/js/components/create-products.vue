<template>
  <div id="create-product">
    <h1>Create-Product</h1>
    <router-link :to="{ name: 'all_products' }" class="btn btn-info">Return</router-link>
  </div>

  <form v-on:submit.prevent="addProduct">
    <div class="form-group">
      <label>ID</label>
      <input type="text" class="form-control" disabled v-model="product.id" id="product_id" />
    </div>
    <div class="form-group">
      <label>Name</label>
      <input type="text" class="form-control" v-model="product.name" id="product_name" required />
    </div>
    <div class="form-group">
      <label>Name</label>
      <input type="text" class="form-control" v-model="product.name" id="product_name" required />
    </div>
    <div class="form-group">
      <button class="btn btn-primary">Create</button>
    </div>
  </form>
</template>

<script>

export default {
  data() {
    return {
      product: {},
      notifications: []
    }
  },

  methods: {
    addProduct: function () {
      // Validation
      // var price = parseFloat(this.product.price);
      this.product.price = this.product.price;
      // if (isNaN(price)) {
      //   this.notifications.push({
      //     type: 'danger',
      //     message: 'Price must be a number'
      //   });
      //   return false;
      // } else {
      //   this.product.price = this.product.price;
      // }

      this.$http.post('http://localhost:3000/api/product/create', this.product, {
        headers: {
          'Content-Type': 'application/json'
        }
      })
        .then((response) => {
          this.product.push()
        })
    }
  },

  // components: {
  //   'notification': Notification
  // }
}

</script>
