<template>
  <div>
    <v-dialog
      class="mx-auto pb-6 mt-1"
      style="border-radius: 12px"
      max-width="448px"
      v-model="dialog"
    >
      <div
        style="
          background-color: white;
          padding: 17px 0 17px 20px;
          border-radius: 12px 12px 0 0;
        "
        class="text-left font-weight-medium title-addnew"
      >
        <!-- <p
          class="title-addnew"
          style="font-weight: 500; padding: 17px 0 0 20px; color: #1a2240"
        >
          
        </p> -->
        Tạo mới sản phẩm
      </div>
      <div style="background-color: #f7f7f7; padding: 16px 20px">
        <div
          style="color: #464f60"
          class="text-subtitle-1 font-weight-bold font-weight-medium text-medium-emphasis d-flex align-center text-name"
        >
          Tên sản phẩm
          <p class="ml-1" style="color: #0f60ff">*</p>
        </div>

        <!-- <v-text-field
          density="compact"
          placeholder="Nhập tên sản phẩm"
          variant="outlined"
          hide-details
          class="bg-white"
          style="margin-bottom: 16px"
        ></v-text-field> -->
        <v-text-field
          :loading="loading"
          density="compact"
          variant="solo"
          label="Nhập tên sản phẩm"
          single-line
          class="bg-white"
          hide-details
          style="margin-bottom: 16px"
          @click:append-inner="onClick"
        ></v-text-field>

        <div
          class="text-subtitle-1 text-medium-emphasis d-flex align-center font-weight-bold"
        >
          Giá
          <p class="ml-1" style="color: #0f60ff">*</p>
        </div>

        <!-- <v-text-field
          density="compact"
          placeholder="Nhập giá sản phẩm"
          variant="outlined"
          hide-details
          class="bg-white"
          style="margin-bottom: 16px"
        ></v-text-field> -->
        <v-text-field
          :loading="loading"
          density="compact"
          variant="solo"
          label="Nhập giá sản phẩm"
          single-line
          class="bg-white"
          hide-details
          style="margin-bottom: 16px"
          @click:append-inner="onClick"
        ></v-text-field>

        <div
          class="text-subtitle-1 text-medium-emphasis text-[14px] d-flex align-center font-weight-bold"
        >
          Số lượng
          <p class="ml-1" style="color: #0f60ff">*</p>
        </div>

        <!-- <v-text-field
          density="compact"
          placeholder="Nhập số lượng sản phẩm"
          variant="outlined"
          hide-details
          class="bg-white"
          style="margin-bottom: 16px"
        ></v-text-field> -->
        <v-text-field
          :loading="loading"
          density="compact"
          variant="solo"
          label="Nhập số lượng sản phẩm"
          single-line
          class="bg-white"
          hide-details
          style="margin-bottom: 16px"
          @click:append-inner="onClick"
        ></v-text-field>

        <div
          class="text-subtitle-1 text-medium-emphasis text-[14px] d-flex align-center font-weight-bold"
        >
          Mô tả
        </div>

        <!-- <v-textarea
          label=""
          placeholder="Nhập mô tả"
          variant="outlined"
          hide-details
          class="bg-white"
          style="margin-bottom: 16px"
        ></v-textarea> -->

        <v-textarea
          label="Nhập mô tả"
          variant="solo"
          placeholder="Nhập mô tả"
        ></v-textarea>

        <div
          class="text-subtitle-1 text-medium-emphasis text-[14px] d-flex align-center"
        >
          Ảnh sản phẩm
          <p class="ml-1" style="color: #0f60ff">*</p>
        </div>

        <!-- <v-text-field
          density="compact"
          placeholder="Nhập link ảnh sản phẩm"
          variant="outlined"
          hide-details
          class="bg-white"
          style="margin-bottom: 16px; border: none"
        ></v-text-field> -->
        <v-text-field
          :loading="loading"
          density="compact"
          variant="solo"
          label="Nhập ảnh sản phẩm"
          single-line
          class="bg-white"
          hide-details
          style="margin-bottom: 16px"
          @click:append-inner="onClick"
        ></v-text-field>

        <!-- <v-card class="mb-12" color="surface-variant" variant="tonal"> </v-card> -->
      </div>
      <v-row
        style="
          padding-top: 15px;
          background-color: white;
          width: 448px;
          margin-left: 0.5px;
          border-radius: 0 0 12px 12px;
        "
      >
        <v-col cols="6"></v-col>
        <v-col cols="6"
          ><v-btn
            width="70"
            class="text-capitalize mr-4"
            @click="this.$emit('close')"
            >Hủy</v-btn
          >
          <v-btn width="105" color="#0f60ff" class="text-capitalize"
            >Tạo
            <p class="text-lowercase">mới</p>
          </v-btn></v-col
        >
      </v-row>
    </v-dialog>
  </div>
</template>

<script>
export default {
  props: ["dialogAdd"],
  computed: {
    dialog: {
      get() {
        return this.dialogAdd;
      },
      set(value) {
        if (!value) {
          this.$emit("close");
        }
      },
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Public+Sans:wght@500&display=swap");
.title-addnew {
  font-family: "Public Sans", sans-serif;
  font-size: 18px;
}
.text-name {
  font-family: "Public Sans", sans-serif;
  font-size: 14px;
}
</style>