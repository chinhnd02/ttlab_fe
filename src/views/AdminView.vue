<template>
  <v-app id="inspire" style="background-color: #f7f7f7; max-height: 778px">
    <!-- <v-layout> -->
    <v-navigation-drawer
      width="260"
      v-model="drawer"
      :rail="rail"
      permanent
      @click="rail = false"
      style="padding: 0"
    >
      <v-list-item>
        <template v-slot:append>
          <img
            class="text-left"
            style="width: 140px; padding: 20px 0 20px 0"
            src="../assets/image/ttlab - logo ngang.svg"
            alt=""
          />
          <v-btn variant="text" @click.stop="rail = !rail"
            ><img src="../assets/image/indent-decrease.png" alt=""
          /></v-btn>
        </template>
      </v-list-item>

      <!-- <v-divider></v-divider> -->

      <v-list density="compact">
        <v-list-item
          title=""
          subtitle=""
          style="padding: 7px 0 15px 30px"
          class="text-uppercase text-left text-manager"
          :class="rail == true ? 'none-text' : ''"
          >Quản lý sản phẩm</v-list-item
        >

        <v-list-item
          style="width: 232px; margin-left: 14px"
          value="product"
          class="text-left mb-2"
          @click="showProduct"
          :class="showProductList == true ? 'text-navbar' : ''"
          ><img
            class="mr-2 ml-1"
            style="margin: -5px"
            :class="rail == true ? 'none-text' : ''"
            src="../assets/image/box.png"
            alt=""
          />
          <span :class="rail == true ? 'none-text' : ''"
            >Sản phẩm</span
          ></v-list-item
        >
        <v-list-item
          class="text-left"
          style="width: 232px; margin-left: 14px"
          value="users"
          @click="showUser"
          :class="showProductList == false ? 'text-navbar' : ''"
          ><img
            class="mr-2 ml-1"
            style="margin: -5px"
            src="../assets/image/users.png"
            :class="rail == true ? 'none-text' : ''"
            alt=""
          /><span :class="rail == true ? 'none-text' : ''"
            >User</span
          ></v-list-item
        >
      </v-list>
    </v-navigation-drawer>

    <v-app-bar flat style="background-color: #f7f7f7">
      <v-app-bar-title class="text-left ml-6 text-title-nav-bar">{{
        this.showProductList == true
          ? "Danh sách sản phẩm"
          : "Danh sách người dùng"
      }}</v-app-bar-title>

      <v-badge content="4" overlap color="red">
        <v-icon icon="mdi mdi-bell-outline"></v-icon>
        <!-- <img src="../assets/image/indent-decrease.png" alt=""> -->
      </v-badge>

      <v-badge
        class="ml-4 mr-4"
        offset-x="100%"
        offset-y="100%"
        overlap
        color="green"
        dot
      >
        <v-avatar>
          <v-img
            style="width: 38px; height: 38px"
            src="https://cdn.vuetifyjs.com/images/john.jpg"
            alt="John"
          ></v-img>
        </v-avatar>
      </v-badge>
    </v-app-bar>

    <v-main class="custom-main ml-6" style="background-color: #f7f7f7">
      <!--  -->

      <div>
        <ProductList v-if="showProductList" />
        <UserList v-else />
      </div>
      <!-- <div v-else-if="(showUserList = true)">
          <user-list />
        </div> -->

      <v-divider :width="rail == false ? wn : wl"></v-divider>

      <div
        style="background-color: white; border-radius: 0 0 12px 12px"
        class="mr-5 mb-10"
      >
        <v-row>
          <v-col cols="7" class="mt-7">
            <v-row>
              <p class="mt-5 ml-6 showing" style="padding-left: 24px">
                Showing
              </p>
              <v-col cols="2">
                <v-select
                  :items="['10', '20']"
                  density="compact"
                  single-line
                  label="10"
                  variant="outlined"
                ></v-select>
              </v-col>
              <p class="mt-5 showing">of 50</p>
            </v-row>
          </v-col>
          <v-col cols="1"></v-col>
          <v-col cols="4">
            <!-- <v-pagination
              active-color="#0F60FF"
              v-model="page"
              :length="5"
              color="#F1F2F6"
              variant="elevated"
              density="compact"
              class="text-right"
              style="box-shadow: none"
            ></v-pagination> -->
            <div class="text-xs-center">
              <v-pagination
                :length="5"
                active-color="#0F60FF"
                color="#F1F2F6"
                v-model="page"
                density="compact"
                variant="flat"
              ></v-pagination>
            </div>
          </v-col>
        </v-row>
      </div>
    </v-main>
    <!-- </v-layout> -->

    <!-- <add-new :dialogAdd="dialogAdd" @close="dialogAdd = false" /> -->
  </v-app>
</template>
    
    <script setup>
import { ref } from "vue";
import ProductList from "../components/ProductList.vue";
import UserList from "../components/UserList.vue";

const drawer = ref(null);
const rail = ref(false);
// const showProductList = ref(true);
// const showUserList = ref(false);
</script>
    
    <script>
export default {
  components: { ProductList, UserList },
  // data: () => ({ drawer: null, page: 1 }),
  // methods: {

  // }
  data() {
    return {
      // dialogAdd: false,
      page: 1,
      showProductList: true,
      showUserList: false,
      wn: 1210,
      wl: 1413,
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

.text-title-nav-bar {
  font-family: "Public Sans", sans-serif;
  font-weight: 600;
  font-size: 24px;
  line-height: 22px;
  color: #23272e;
}
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
.text-navbar {
  font-family: "Public Sans", sans-serif;
  font-size: 15px !important;
  font-weight: 600;
}
.v-pagination {
  box-shadow: none;
}
.none-text {
  display: none;
}
.none-nav {
  float: right;
}
.display-nav {
  margin: -5px;
}
.addmargin {
  margin-left: 14px;
}

/* .v-pagination {
  display: flex;
  justify-content: center;
  margin: 0;
  padding: 0;
}

.v-pagination > div {
  margin: 0;
  padding: 0;
}

.v-pagination__item {
  margin: 0;
  padding: 0;
} */
</style>