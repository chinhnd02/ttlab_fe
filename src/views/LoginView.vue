<template>
  <div>
    <form action="" @submit="onSubmit">
      <v-card
        class="mx-auto pa-10 pb-7 mt-16"
        max-width="448"
        rounded="lg"
        flat
      >
        <img src="../assets/image/ttlab-logo.svg" alt="" />

        <p class="text-title mt-4">Đăng nhập</p>

        <div
          class="text-email text-medium-emphasis mb-1 font-weight-bold d-flex align-center justify-space-between"
        >
          Email
        </div>

        <v-text-field
          density="compact"
          placeholder="Nhập email"
          variant="outlined"
          type="email"
          v-model="email"
          v-bind="emailAttrs"
          single-line
          hide-details
        >
        </v-text-field>
        <span
          class="text-left"
          style="color: red; font-size: 12px; float: left"
          >{{ errors.email }}</span
        >

        <div
          class="text-email text-medium-emphasis mb-1 font-weight-bold d-flex align-center justify-space-between mt-6"
        >
          Mật khẩu
        </div>

        <v-text-field
          :append-inner-icon="visible ? 'mdi-eye' : 'mdi-eye-off'"
          :type="visible ? 'text' : 'password'"
          density="compact"
          placeholder="••••••••••••••"
          variant="outlined"
          v-model="password"
          v-bind="passwordAttrs"
          @click:append-inner="visible = !visible"
          single-line
          hide-details
        ></v-text-field>
        <span
          class="text-left"
          style="color: red; font-size: 12px; float: left"
        >
          {{ errors.password }}
        </span>

        <v-row class="mt-5">
          <v-checkbox
            label="Ghi nhớ Đăng nhập"
            class="font-weight-bold"
          ></v-checkbox>

          <p class="forgot-pass mt-5 mr-4">Quên mật khẩu?</p>
        </v-row>

        <v-btn
          block
          class="mb-4 text-login text-lowercase"
          color="primary"
          size="large"
        >
          <p class="text-uppercase">Đ</p>
          ăng nhập
        </v-btn>

        <v-card-text class="text-center ml-10" style="display: flex">
          <!-- <v-row> -->
          <p class="cctk">Bạn chưa có tài khoản?</p>
          <p class="ml-2 register">Đăng ký</p>
          <!-- </v-row> -->
        </v-card-text>
      </v-card>
    </form>
  </div>
</template>

<script setup>
import { useForm } from "vee-validate";
import * as yup from "yup";
const { errors, handleSubmit, defineField } = useForm({
  validationSchema: yup.object({
    email: yup.string().email("Email không hợp lệ"),
    password: yup.string().min(8, "Mật khẩu phải trên 8 kí tự"),
  }),
});

const onSubmit = handleSubmit((values) => {
  alert(JSON.stringify(values, null, 2));
});

const [email, emailAttrs] = defineField("email");
const [password, passwordAttrs] = defineField("password");
</script>

<script>
export default {
  data() {
    return {
      visible: false,
    };
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Public+Sans&display=swap");
.text-title {
  font-family: "Public Sans", sans-serif;
  font-size: 32px;
  font-weight: 600;
  line-height: 48px;
}
.text-email {
  font-family: "Public Sans", sans-serif;
  font-size: 14px;
  font-weight: 500;
  color: #464f60;
  line-height: 20px;
}
.forgot-pass {
  font-family: "Public Sans", sans-serif;
  font-weight: 600;
  font-size: 14px;
  line-height: 20px;
  color: #0f60ff;
}
.text-login {
  font-family: "Public Sans", sans-serif;
  font-weight: 500;
  font-size: 16px;
  line-height: 20px;
}
.cctk {
  font-family: "Public Sans", sans-serif;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  color: #5a5c6f;
}
.register {
  font-family: "Public Sans", sans-serif;
  font-weight: 600;
  font-size: 14px;
  line-height: 20px;
  color: #0f60ff;
}
</style>