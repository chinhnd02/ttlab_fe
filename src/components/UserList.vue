<template>
  <div>
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
        <v-btn class="text-capitalize" color="primary" @click="dialogAdd = true"
          >+ Tạo mới</v-btn
        >
      </v-col>
    </v-row>

    <v-row class="mr-2">
      <v-col cols="12">
        <v-table style="border-radius: 12px 12px 0 0">
          <thead>
            <tr>
              <th class="text-table text-uppercase">Avatar</th>
              <th class="text-table text-uppercase">Tên người dùng</th>
              <th class="text-table text-uppercase">Email</th>
              <th class="text-table text-uppercase">Ngày sinh</th>
              <th class="text-table text-uppercase">Số điện thoại</th>
              <th class="text-table text-uppercase">Hành động</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(item, i) in 7" :key="i">
              <!-- <td colspan="2" class="text-left">Sản phẩm {{ ++i }}</td> -->
              <td class="text-left">
                <img
                  style="width: 36px; height: 36px"
                  src="../assets/image/img (1).png"
                  alt=""
                />
              </td>
              <td class="text-left font-weight-bold">Arlene McCoy</td>
              <td class="text-left">georgia.young@example.com</td>
              <td class="text-left">1969/03/05</td>
              <td class="text-left">082-141-2567</td>

              <td class="text-left">
                <!-- <v-btn variant="text"> -->
                <img class="mt-1 mr-2" src="../assets/image/edit.png" alt="" />
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
    <!-- <add-new :dialogAdd="dialogAdd" @close="dialogAdd = false" /> -->
    <!-- <add-new :dialogAdd="dialogAdd" @close="dialogAdd = false" /> -->
    <add-user :dialogAdd="dialogAdd" @close="dialogAdd = false" />
  </div>
</template>

<script>
import AddUser from "./AddUser.vue";
export default {
  components: { AddUser },
  data() {
    return {
      dialogAdd: false,
    };
  },
};
</script>

<style scoped>
.text-table {
  font-family: "Public Sans", sans-serif;
  font-weight: 500;
  font-size: 13px;
  line-height: 15.28px;
  color: #8b909a;
}
</style>