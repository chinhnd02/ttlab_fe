<template>
  <v-app id="inspire" style="background-color: #f7f7f7">
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
      <v-list-item class="text-left" link title=""
        ><img
          class="mr-2 ml-1 text-list"
          style="margin: -5px"
          src="../assets/image/box.png"
          alt=""
        />Sản phẩm</v-list-item
      >
      <v-list-item class="text-left" link title=""
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

      <!-- <v-badge content="4">
        <v-avatar class="ml-4 mr-4"> -->
      <!-- <v-img
            src="https://cdn.vuetifyjs.com/images/john.jpg"
            alt="John"
          ></v-img> -->
      <!-- </v-avatar>
      </v-badge> -->
    </v-app-bar>
    <!-- style="background-color: #f7f7f7" -->
    <v-main class="custom-main ml-6" style="background-color: #f7f7f7">
      <!--  -->
      <v-row>
        <v-col cols="4" class="mt-4">
          <v-text-field
            :loading="loading"
            density="compact"
            variant="solo"
            label="Tìm kiếm"
            append-inner-icon="mdi-magnify"
            single-line
            hide-details
            @click:append-inner="onClick"
          ></v-text-field>
          <!-- <v-text-field
            class="search_input bg-white"
            v-model="message"
            density="compact"
            clearable
            label="Tìm kiếm"
            hide-details
            type="text"
            variant="solo"
            style="display: block"
          >
            <template v-slot:append-inner>
              <v-fade-transition leave-absolute>
                <v-progress-circular
                  v-if="loading"
                  color="info"
                  indeterminate
                  size="24"
                ></v-progress-circular>

                <img
                  v-else
                  height="15"
                  width="15"
                  src="../assets/image/Vector (3).png"
                  alt=""
                />
              </v-fade-transition>
            </template>

            <template v-slot:append>
              <v-menu>
                <v-card>
                  <v-card-text class="pa-6">
                    <v-btn
                      color="primary"
                      size="large"
                      variant="text"
                      @click="clickMe"
                    >
                      <v-icon icon="mdi-target" start></v-icon>

                      Click me
                    </v-btn>
                  </v-card-text>
                </v-card>
              </v-menu>
            </template>
          </v-text-field> -->
        </v-col>
        <v-col class="text-right mr-4 mt-5">
          <v-btn
            class="text-capitalize"
            color="primary"
            @click="dialogAdd = true"
            >+ Tạo mới</v-btn
          >
        </v-col>
      </v-row>

      <v-row class="mr-2">
        <v-col cols="12">
          <v-table style="border-radius: 12px 12px 0 0">
            <thead>
              <tr>
                <th colspan="2" class="text-table text-uppercase">
                  Tên sản phẩm
                </th>
                <th class="text-table text-uppercase">Giá</th>
                <th class="text-table text-uppercase">Số lượng</th>
                <th class="text-table text-uppercase">Mô tả</th>
                <th class="text-table text-uppercase">Ảnh</th>
                <th class="text-table text-uppercase">Actions</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(item, i) in 7" :key="i">
                <td colspan="2" class="text-left">Sản phẩm {{ ++i }}</td>
                <td class="text-left">$6.000</td>
                <td class="text-left">1</td>
                <td class="text-left">
                  Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                </td>
                <td class="text-left">
                  <img src="../assets/image/img.png" alt="" />
                </td>
                <td class="text-left">
                  <!-- <v-btn variant="text"> -->
                  <img
                    class="mt-1 mr-2"
                    src="../assets/image/edit.png"
                    alt=""
                  />
                  <!-- </v-btn> -->
                  <!-- <v-btn variant="text"> -->
                  <img src="../assets/image/trash.png" alt="" />
                  <!-- </v-btn> -->
                </td>
                <hr />
              </tr>
            </tbody>
          </v-table>
        </v-col>
        <!-- <v-data-table :items="items"></v-data-table>
         -->
      </v-row>
      <div
        style="background-color: white; border-radius: 0 0 12px 12px"
        class="mr-5 mb-10"
      >
        <v-row>
          <v-col cols="8" class="mt-7">
            <v-row>
              <p class="mt-5 ml-6 showing">Showing</p>
              <v-col cols="2">
                <!-- <v-select
                  density="compact"
                  label="--"
                  :items="['10', '20', '30', '40', '50', '60']"
                  variant="outlined"
                ></v-select> -->
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

    <add-new :dialogAdd="dialogAdd" @close="dialogAdd = false" />
  </v-app>
</template>
    
    <script setup>
import { ref } from "vue";
import AddNew from "./AddNew.vue";

const drawer = ref(null);
</script>
    
    <script>
export default {
  components: { AddNew },
  // data: () => ({ drawer: null, page: 1 }),
  // methods: {

  // }
  data() {
    return {
      drawer: null,
      dialogAdd: false,
      page: 1,
    };
  },
  methods: {},
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
.text-table {
  font-family: "Public Sans", sans-serif;
  font-weight: 500;
  font-size: 13px;
  line-height: 15.28px;
  color: #8b909a;
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