<template>
    <div class="admin">
      <h2 class="section-title">Admin Dashboard</h2>
      <div class="admin-actions">
        <router-link to="/admin/users" class="btn">Manage Users</router-link>
        <!-- <EditUserComp /> 
        <AddUserComp />
        <UsersListComp /> -->
        <router-link to="/admin/products" class="btn">Manage Products</router-link>
        <!-- <EditProductComp />
        <AddProductComp />
        <ProductListComp /> -->
      </div>
    </div>
  </template>
  
  <script>
  import UsersListComp from "@/views/ProductList.vue"; // Make sure to provide the correct path to your UserList.vue file
  import ProductListComp from "@/views/ProductList.vue"; // Make sure to provide the correct path to your ProductList.vue file
  
  export default {
    // Your component options
    components: {
      UsersListComp,

      ProductListComp,

    },
  };
  </script>
  
  <style scoped>
  .admin {
    padding: 4rem 0;
    text-align: center;
  }
  
  .section-title {
    font-size: 2rem;
    margin-bottom: 2rem;
  }
  
  .admin-actions {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 2rem;
    margin-top: 2rem;
  }
  
  .btn {
    background-color: #ff69b4;
    color: white;
    padding: 0.5rem 1rem;
    border: none;
    border-radius: 5px;
    text-decoration: none;
    font-size: 1rem;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  .btn:hover {
    background-color: #ff3385;
  }
  </style>
  