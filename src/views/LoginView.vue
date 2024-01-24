<template>
  <div>
    <v-card class="mx-auto pa-12 pb-8 mt-16" max-width="448" rounded="lg" flat>
      <img src="../assets/image/ttlab-logo.svg" alt="" />

      <p class="text-title mt-4">Đăng nhập</p>

      <div
        class="text-left text-medium-emphasis mb-1 font-weight-bold text-email"
      >
        Email
      </div>

      <v-text-field
        density="compact"
        placeholder="Nhập email"
        variant="outlined"
      ></v-text-field>

      <div
        class="text-email text-medium-emphasis mb-1 font-weight-bold d-flex align-center justify-space-between"
      >
        Mật khẩu

        <!-- <a
          class="text-caption text-decoration-none text-blue"
          href="#"
          rel="noopener noreferrer"
          target="_blank"
        >
          Forgot login password?</a
        > -->
      </div>

      <v-text-field
        :append-inner-icon="visible ? 'mdi-eye' : 'mdi-eye-off'"
        :type="visible ? 'text' : 'password'"
        density="compact"
        placeholder="••••••••••••••"
        variant="outlined"
        @click:append-inner="visible = !visible"
      ></v-text-field>

      <v-row>
        <v-checkbox
          label="Ghi nhớ Đăng nhập"
          class="font-weight-bold text-[10px]"
        ></v-checkbox>
        <p class="forgot-pass mt-4 mr-4">Quên mật khẩu?</p>
      </v-row>

      <!-- <v-card class="mb-12" color="surface-variant" variant="tonal">
        <v-card-text class="text-medium-emphasis text-caption">
          Warning: After 3 consecutive failed login attempts, you account will
          be temporarily locked for three hours. If you must login now, you can
          also click "Forgot login password?" below to reset the login password.
        </v-card-text>
      </v-card> -->

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
  </div>
</template>

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