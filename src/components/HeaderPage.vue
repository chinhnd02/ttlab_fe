<template>
  <div class="bg-black header">
    <v-container style="height: 100vh">
      <v-row>
        <v-col cols="3"
          ><p class="text-left text-size-12">
            Mon-Thu:
            <b class="text-time"
              >9:00 AM - 5:30 PM <v-icon icon="mdi mdi-chevron-down"></v-icon
            ></b></p
        ></v-col>
        <v-col>
          <p class="text-center text-address align-center">
            Visit our showroom in 1234 Street Adress City Address, 1234
            <b class="text-decoration-underline text-contact">Contact Us</b>
          </p>
        </v-col>
        <v-col cols="3">
          <v-row
            ><p class="text-call">Call Us: (00) 1234 5678</p>
            <v-icon
              class="icon-fb mt-2 mr-2 ml-2"
              icon="mdi mdi-facebook"
            ></v-icon>
            <v-icon class="icon-ig mt-2" icon="mdi mdi-instagram"></v-icon
          ></v-row>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.header {
  height: 44px;
}
.text-size-12 {
  font-size: 12px;
  line-height: 13px;
  color: #a2a6b0;
  /* height: 100vh; */
}
.text-time {
  color: #ffffff;
}
.text-address {
  font-weight: 600;
  font-size: 12px;
  line-height: 13px;
  color: #acacac;
}
.text-contact {
  color: #ffffff;
}
.text-call {
  font-weight: 600;
  font-size: 12px;
  line-height: 38px;
  text-align: center;
}
.icon-fb,
.icon-ig {
  font-size: 20px;
}
</style>