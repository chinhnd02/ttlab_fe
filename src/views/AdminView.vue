<template>
  <v-app id="inspire" style="background-color: #f7f7f7; max-height: 100vh">
    <v-navigation-drawer v-model="drawer">
      <!-- 
       -->
      <img src="../assets/image/ttlab - logo ngang.svg" alt="" />
      <v-list-item
        title=""
        subtitle=""
        class="text-uppercase text-left text-manager"
        >Quản lý sản phẩm</v-list-item
      >
      <v-list-item class="text-left" link title="" @click="showProduct"
        ><img
          class="mr-2 ml-1 text-list"
          style="margin: -5px"
          src="../assets/image/box.png"
          alt=""
        />Sản phẩm</v-list-item
      >
      <v-list-item class="text-left" link title="" @click="showUser"
        ><img
          class="mr-2 ml-1 text-list"
          style="margin: -5px"
          src="../assets/image/users.png"
          alt=""
        />User</v-list-item
      >
    </v-navigation-drawer>

    <v-app-bar flat style="background-color: #f7f7f7">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-app-bar-title class="text-left">Danh sách sản phẩm</v-app-bar-title>

      <v-badge content="4" overlap color="red">
        <v-icon icon="mdi mdi-bell-outline"></v-icon>
      </v-badge>
      <v-badge
        class="ml-4 mr-4"
        offset-x="100%"
        offset-y="50%"
        overlap
        color="green"
        dot
      >
        <v-avatar>
          <v-img
            src="https://cdn.vuetifyjs.com/images/john.jpg"
            alt="John"
          ></v-img>
        </v-avatar>
      </v-badge>
    </v-app-bar>

    <v-main class="custom-main ml-6" style="background-color: #f7f7f7">
      <!--  -->

      <div v-if="(showProductList = true)">
        <product-list />
      </div>
      <div v-else-if="(showUserList = true)">
        <user-list />
      </div>

      <div
        style="background-color: white; border-radius: 0 0 12px 12px"
        class="mr-5 mb-10"
      >
        <v-row>
          <v-col cols="8" class="mt-7">
            <v-row>
              <p class="mt-5 ml-6 showing">Showing</p>
              <v-col cols="2">
                <v-select
                  :items="['10', '20']"
                  density="compact"
                  label=""
                  variant="solo"
                ></v-select>
              </v-col>
              <p class="mt-5 showing">of 50</p>
            </v-row>
          </v-col>
          <v-col cols="4" class="text-right">
            <v-pagination
              active-color="#0F60FF"
              v-model="page"
              :length="4"
              color="#F1F2F6"
              variant="elevated"
              density="compact"
            ></v-pagination>
          </v-col>
        </v-row>
      </div>
    </v-main>

    <!-- <add-new :dialogAdd="dialogAdd" @close="dialogAdd = false" /> -->
  </v-app>
</template>
    
    <script setup>
import { ref } from "vue";
import ProductList from "../components/ProductList.vue";
import UserList from "../components/UserList.vue";

const drawer = ref(null);
</script>
    
    <script>
export default {
  components: { ProductList, UserList },
  // data: () => ({ drawer: null, page: 1 }),
  // methods: {

  // }
  data() {
    return {
      drawer: null,
      // dialogAdd: false,
      page: 1,
      showProductList: true,
      showUserList: false,
    };
  },
  methods: {
    showProduct() {
      this.showProductList = true;
      this.showUserList = false;
      console.log(this.showProductList, this.showUserList);
    },
    showUser() {
      this.showUserList = true;
      this.showProductList = false;
      console.log(this.showUserList, this.showProductList);
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Public+Sans&display=swap");

.text-manager {
  font-family: "Public Sans", sans-serif;
  font-weight: 400;
  font-size: 11px;
  line-height: 14px;
  color: #8b909a;
}
.text-list {
  font-family: "Public Sans", sans-serif;
  font-weight: 600;
  font-size: 15px;
  line-height: 22px;
  color: #23272e;
}

.showing {
  font-family: "Public Sans", sans-serif;
  font-weight: 500;
  font-size: 15px;
  color: #8b909a;
}
/* element.style {
  bottom: calc(100% - 37px);
  left: calc(100% - 25px);
} */
</style>