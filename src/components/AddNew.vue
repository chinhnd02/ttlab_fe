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
        class="text-left title-addnew"
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
          class="font-weight-bold font-weight-medium text-medium-emphasis d-flex align-center text-name mb-2"
        >
          Tên sản phẩm
          <p class="ml-1" style="color: #0f60ff">*</p>
        </div>
        <v-text-field
          :loading="loading"
          density="compact"
          variant="solo"
          label="Nhập tên sản phẩm"
          single-line
          v-model="name"
          v-bind="nameAttrs"
          class="bg-white"
          hide-details
          style="border-radius: 6px; border: 1px solid rgb(231, 231, 231)"
          flat
          @click:append-inner="onClick"
        ></v-text-field>
        <span
          class="text-left"
          style="color: red; font-size: 12px; float: right"
          >{{ errors.name }}</span
        >

        <div
          class="text-medium-emphasis d-flex align-center font-weight-bold text-name mb-2 mt-4"
        >
          Giá
          <p class="ml-1" style="color: #0f60ff">*</p>
        </div>

        <v-text-field
          :loading="loading"
          density="compact"
          variant="solo"
          label="Nhập giá sản phẩm"
          single-line
          type="number"
          class="bg-white"
          v-model="price"
          v-bind="priceAttrs"
          hide-details
          flat
          style="border-radius: 6px; border: 1px solid rgb(231, 231, 231)"
          @click:append-inner="onClick"
        ></v-text-field>
        <span
          class="text-left"
          style="color: red; font-size: 12px; float: right"
          >{{ errors.price }}</span
        >

        <div
          class="text-medium-emphasis text-[14px] d-flex align-center font-weight-bold text-name mb-2 mt-4"
        >
          Số lượng
          <p class="ml-1" style="color: #0f60ff">*</p>
        </div>

        <v-text-field
          :loading="loading"
          density="compact"
          variant="solo"
          label="Nhập số lượng sản phẩm"
          single-line
          class="bg-white"
          flat
          v-model="quantity"
          v-bind="quantityAttrs"
          hide-details
          style="border-radius: 6px; border: 1px solid rgb(231, 231, 231)"
          @click:append-inner="onClick"
        ></v-text-field>
        <span
          class="text-left"
          style="color: red; font-size: 12px; float: right"
          >{{ errors.quantity }}</span
        >

        <div
          class="text-medium-emphasis text-[14px] d-flex align-center font-weight-bold text-name mb-2 mt-4"
        >
          Mô tả
        </div>
        <v-textarea
          label="Nhập mô tả"
          variant="solo"
          placeholder="Nhập mô tả"
          single-line
          v-bind="descriptionAttrs"
          v-model="description"
          class="text-area"
          style="
            margin-bottom: 16px;
            border-radius: 6px;
            border: 1px solid rgb(231, 231, 231);
          "
          flat
          hide-details
        ></v-textarea>
        <!-- <v-textarea label="Label" variant="solo" flat single-line></v-textarea> -->

        <div
          class="text-medium-emphasis text-[14px] d-flex align-center font-weight-bold text-name mb-2"
        >
          Ảnh sản phẩm
          <p class="ml-1" style="color: #0f60ff">*</p>
        </div>

        <v-text-field
          :loading="loading"
          density="compact"
          variant="solo"
          label="Nhập link ảnh sản phẩm"
          single-line
          class="bg-white mb-3"
          v-bind="imageAttrs"
          v-model="image"
          hide-details
          flat
          style="border-radius: 6px; border: 1px solid rgb(231, 231, 231)"
          @click:append-inner="onClick"
        ></v-text-field>

        <span
          class="text-left"
          style="color: red; font-size: 12px; float: right"
          >{{ errors.image }}</span
        >

        <!-- <v-card class="mb-12" color="surface-variant" variant="tonal"> </v-card> -->
      </div>
      <v-row
        style="
          padding-top: 8px;
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
            flat
            class="text-capitalize mr-4"
            @click="this.$emit('close')"
            style="border-radius: 6px; border: 1px solid rgb(222, 222, 222)"
            >Hủy</v-btn
          >
          <v-btn
            @click="onSubmit"
            width="105"
            color="#0f60ff"
            class="text-capitalize"
            flat
            style="border-radius: 6px; border: 1px solid rgb(231, 231, 231)"
            >Tạo
            <p class="text-lowercase">mới</p>
          </v-btn></v-col
        >
      </v-row>
    </v-dialog>
  </div>
</template>

<script setup>
import { useForm } from "vee-validate";
import * as yup from "yup";
const { errors, handleSubmit, defineField } = useForm({
  validationSchema: yup.object({
    name: yup.string().required("Không được để trống"),
    price: yup.string().required("Không được để trống"),
    quantity: yup.string().required("Không được để trống"),
    description: yup.string().max(255),
    image: yup.string().required("aalal"),
  }),
});

const onSubmit = handleSubmit((values) => {
  alert(JSON.stringify(values, null, 2));
});

const [name, nameAttrs] = defineField("name");
const [price, priceAttrs] = defineField("price");
const [quantity, quantityAttrs] = defineField("quantity");
const [description, descriptionAttrs] = defineField("description");
const [image, imageAttrs] = defineField("image");
</script>

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
  font-weight: 500;
}
.text-name {
  font-family: "Public Sans", sans-serif;
  font-size: 14px;
}
</style>