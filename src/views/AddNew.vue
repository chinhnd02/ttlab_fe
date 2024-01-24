<template>
  <div>
    <v-card
      class="mx-auto pa-10 pb-6 mt-6"
      elevation="8"
      max-width="448"
      rounded="lg"
    >
      <v-card-title style="padding: 0" class="text-left mb-5"
        >Tạo mới sản phẩm</v-card-title
      >
      <div>
        <div class="text-subtitle-1 text-medium-emphasis d-flex align-center">
          Tên sản phẩm
          <p class="ml-1" style="color: #0f60ff">*</p>
        </div>

        <v-text-field
          density="compact"
          placeholder="Nhập tên sản phẩm"
          variant="outlined"
        ></v-text-field>

        <div class="text-subtitle-1 text-medium-emphasis d-flex align-center">
          Giá
          <p class="ml-1" style="color: #0f60ff">*</p>
        </div>

        <v-text-field
          density="compact"
          placeholder="Nhập giá sản phẩm"
          variant="outlined"
        ></v-text-field>

        <div class="text-subtitle-1 text-medium-emphasis d-flex align-center">
          Mô tả
        </div>

        <v-textarea
          label=""
          placeholder="Nhập mô tả"
          variant="outlined"
        ></v-textarea>

        <div class="text-subtitle-1 text-medium-emphasis d-flex align-center">
          Ảnh sản phẩm
          <p class="ml-1" style="color: #0f60ff">*</p>
        </div>

        <v-text-field
          density="compact"
          placeholder="Nhập link ảnh sản phẩm"
          variant="outlined"
        ></v-text-field>

        <!-- <v-card class="mb-12" color="surface-variant" variant="tonal"> </v-card> -->
      </div>
      <v-row>
        <v-col cols="5"></v-col>
        <v-col cols="7"
          ><v-btn width="70" class="text-capitalize mr-5">Hủy</v-btn>
          <v-btn width="105" color="#0f60ff" class="text-capitalize"
            >Tạo mới</v-btn
          ></v-col
        >
      </v-row>
    </v-card>
  </div>
</template>

<script>
export default {};
</script>

<style>
</style>