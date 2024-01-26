<template>
  <div class="mt-8">
    <v-container>
      <div class="headerPage">
        <div style="box-shadow: 1px 5px 8px #888888; border-radius: 6px">
          <v-row>
            <v-col cols="2" class="ml-5">
              <v-select
                width="136"
                class="text-uppercase text-subtitle-1"
                label="Sort by"
                density="compact"
                :items="[
                  'California',
                  'Colorado',
                  'Florida',
                  'Georgia',
                  'Texas',
                  'Wyoming',
                ]"
                variant="outlined"
              ></v-select>
            </v-col>
            <v-col cols="2">
              <v-select
                label="Condition"
                density="compact"
                :items="[
                  'California',
                  'Colorado',
                  'Florida',
                  'Georgia',
                  'Texas',
                  'Wyoming',
                ]"
                variant="outlined"
              ></v-select>
            </v-col>
            <v-col cols="2">
              <v-select
                label="Delivery Options"
                density="compact"
                :items="[
                  'California',
                  'Colorado',
                  'Florida',
                  'Georgia',
                  'Texas',
                  'Wyoming',
                ]"
                variant="outlined"
              ></v-select>
            </v-col>
            <v-col class="py-2 mt-2">
              <v-btn-toggle v-model="text" rounded="0" color="#FFFFFF" group>
                <v-btn
                  style="font-size: 14px; border-radius: 2px"
                  class="text-capitalize"
                  height="36"
                  width="85"
                  variant="elevated"
                  :elevation="buttonHightlight == 3 ? 1 : 0"
                  @click="this.buttonHightlight = 3"
                  :class="buttonHightlight == 3 ? 'highlight' : 'not_highlight'"
                >
                  Show all
                </v-btn>

                <v-btn
                  style="font-size: 14px; border-radius: 2px"
                  class="text-capitalize"
                  height="36"
                  width="85"
                  variant="elevated"
                  :elevation="buttonHightlight == 1 ? 1 : 0"
                  @click="this.buttonHightlight = 1"
                  :class="buttonHightlight == 1 ? 'highlight' : 'not_highlight'"
                >
                  Aution
                </v-btn>

                <v-btn
                  style="font-size: 14px; border-radius: 2px"
                  class="text-capitalize"
                  height="36"
                  width="85"
                  :elevation="buttonHightlight == 2 ? 1 : 0"
                  variant="elevated"
                  @click="this.buttonHightlight = 2"
                  :class="buttonHightlight == 2 ? 'highlight' : 'not_highlight'"
                >
                  Buy now
                </v-btn>
              </v-btn-toggle>
            </v-col>
            <v-col cols="2" class="mt-1 mr-2">
              <v-btn-toggle v-model="options" rounded="0" color="#FFFFFF" group>
                <v-btn
                  style="font-size: 14px; border-radius: 2px"
                  class="text-capitalize"
                  height="36"
                  width="85"
                  v-model="buttonR"
                  :class="buttonR == 1 ? 'not_highlight' : ''"
                >
                  <img src="../assets/imageList/Vector.png" alt="" />
                </v-btn>

                <v-btn
                  style="font-size: 14px; border-radius: 2px"
                  class="text-capitalize mr-3"
                  height="36"
                  width="85"
                  color="white"
                  v-model="buttonR"
                  :elevation="buttonR == 1 ? 1 : 0"
                >
                  <img src="../assets/imageList/Vector (1).png" alt="" />
                </v-btn>
              </v-btn-toggle>
            </v-col>
          </v-row>
          <v-row>
            <p
              class="mr-5 ml-8"
              style="line-height: 46px; font-weight: 600; font-size: 14px"
            >
              Related
            </p>
            <v-chip-group>
              <v-chip style="font-size: 14px; font-weight: 400"
                >worldwide shipping</v-chip
              >

              <v-chip style="font-size: 14px; font-weight: 400"
                >under $50</v-chip
              >

              <v-chip style="font-size: 14px; font-weight: 400"
                >plastic plugs</v-chip
              >
              <v-chip style="font-size: 14px; font-weight: 400"
                >pucker shoes</v-chip
              >
              <v-chip style="font-size: 14px; font-weight: 400"
                >vintage typewriter</v-chip
              >
            </v-chip-group>
          </v-row>
          <v-row>
            <v-card
              width="260"
              height="480"
              v-for="(index, i) in 12"
              class="ml-7 mt-7 mb-2"
              :key="i"
              flat
              :class="['item', { hovered: activeIndex === index }]"
              @mouseover="setActiveIndex(index)"
              @mouseout="setActiveIndex(null)"
            >
              <img src="../assets/imageList/Image.png" alt="" />

              <!-- <v-card-title> -->
              <!-- <span style="font-size: 16px; font-weight: 400; line-height: 24px"
                  >Vintage Typewriter to post awesome stories about UI design and
                  webdev.</span
                > -->
              <v-card-text
                class="text-left"
                style="font-size: 16px; font-weight: 400; line-height: 24px"
              >
                Vintage Typewriter to post awesome stories about UI design and
                webdev.
              </v-card-text>
              <!-- </v-card-title> -->
              <!-- <v-card-item> -->
              <v-card-text style="padding: 0">
                <p
                  class="text-left"
                  style="
                    font-weight: 700;
                    font-size: 24px;
                    line-height: 36px;
                    padding: 0 15px 8px 15px;
                  "
                >
                  $49.50
                </p>
                <p
                  class="text-left"
                  style="padding: 0 15px 8px 15px; color: #787885"
                >
                  Eligible for Shipping To Mars or somewhere else
                </p>
              </v-card-text>
              <v-row class="mb-1">
                <!-- <v-col> -->
                <div class="rating" style="padding: 15px 15px 15px 26px">
                  <input value="5" name="rate" id="star5" type="radio" />
                  <label title="text" for="star5"></label>
                  <input value="4" name="rate" id="star4" type="radio" />
                  <label title="text" for="star4"></label>
                  <input
                    value="3"
                    name="rate"
                    id="star3"
                    type="radio"
                    checked=""
                  />
                  <label title="text" for="star3"></label>
                  <input value="2" name="rate" id="star2" type="radio" />
                  <label title="text" for="star2"></label>
                  <input value="1" name="rate" id="star1" type="radio" />
                  <label title="text" for="star1"></label>
                </div>
                <p style="font-size: 14px; font-weight: 500; padding: 18px 0">
                  4.05
                </p>
                <!-- </v-col> -->
                <!-- <v-col> -->
                <v-btn
                  variant="outlined"
                  color="#2264D1"
                  width="88"
                  height="32"
                  class="text-capitalize mt-3 ml-8 mr-2"
                  style="font-size: 14px"
                >
                  <v-icon
                    icon="mdi mdi-heart-outline"
                    small
                    class="mr-1"
                  ></v-icon>
                  Watch
                </v-btn>
                <!-- </v-col> -->
              </v-row>
              <!-- </v-card-item> -->
            </v-card>
          </v-row>
        </div>

        <v-row class="mt-10 mb-8">
          <v-card
            class="ml-7"
            style="background-color: #ededf0; width: 360px; height: 160px"
          >
            <img
              style="width: 36px; height: 36px"
              class="mt-8"
              src="../assets/imageList/Vector (4).png"
              alt=""
            />
            <v-card-item>
              <p
                style="
                  font-weight: 700;
                  font-size: 20px;
                  line-height: 30px;
                  color: #000000;
                "
              >
                Clear & Usable user flows
              </p>
              <p
                style="
                  font-weight: 400;
                  font-size: 14px;
                  line-height: 30px;
                  color: #5a5b6a;
                "
              >
                Let’s boost yout marketplace
              </p>
            </v-card-item>
          </v-card>
          <v-card
            class="ml-7 mr-7"
            style="background-color: #ededf0; width: 360px; height: 160px"
          >
            <img
              class="mt-8"
              style="widows: 36px; height: 36px"
              src="../assets/imageList/Vector (5).png"
              alt=""
            />
            <v-card-item>
              <p
                style="
                  font-weight: 700;
                  font-size: 20px;
                  line-height: 30px;
                  color: #000000;
                "
              >
                Fine & Styled components
              </p>
              <p
                style="
                  font-weight: 400;
                  font-size: 14px;
                  line-height: 30px;
                  color: #5a5b6a;
                "
              >
                Speed up with Setproduct templates
              </p>
            </v-card-item>
          </v-card>
          <v-card
            style="background-color: #ededf0; width: 360px; height: 160px"
          >
            <img class="mt-8" src="../assets/imageList/Vector (2).png" alt="" />
            <v-card-item>
              <p
                style="
                  font-weight: 700;
                  font-size: 20px;
                  line-height: 30px;
                  color: #000000;
                "
              >
                Customizable & Reusable
              </p>
              <p
                style="
                  font-weight: 400;
                  font-size: 14px;
                  line-height: 30px;
                  color: #5a5b6a;
                "
              >
                Take our UX patterns and rebuild
              </p>
            </v-card-item>
          </v-card>
        </v-row>
      </div>
    </v-container>
  </div>
</template>
  
  <script>
export default {
  data() {
    return {
      text: "center",
      icon: "justify",
      toggle_none: null,
      toggle_one: 0,
      toggle_exclusive: 2,
      toggle_multiple: [0, 1, 2],
      options: "left",
      buttonHightlight: 1,
      buttonR: 1,
      activeIndex: null,
      // products: [
      //   {
      //     img:
      //   }
      // ]
    };
  },
  methods: {
    setActiveIndex(index) {
      this.activeIndex = index;
    },
  },
};
</script>
  
  <style scoped>
.rating:not(:checked) > input {
  position: absolute;
  appearance: none;
}

.rating:not(:checked) > label {
  float: right;
  cursor: pointer;
  font-size: 16px;
  color: #666;
}

.rating:not(:checked) > label:before {
  content: "★";
}

.rating > input:checked + label:hover,
.rating > input:checked + label:hover ~ label,
.rating > input:checked ~ label:hover,
.rating > input:checked ~ label:hover ~ label,
.rating > label:hover ~ input:checked ~ label {
  color: #e58e09;
}

.rating:not(:checked) > label:hover,
.rating:not(:checked) > label:hover ~ label {
  color: #ff9e0b;
}

.rating > input:checked ~ label {
  color: #ffa723;
}

.highlight {
  background-color: white;
  color: #2264d1;
}
.not_highlight {
  background: #ebf2ff;
  color: #5a5b6a;
}
.item {
  padding: 10px;
  margin: 5px;
  /* border: 1px solid #ccc; */
  transition: background-color 0.3s;
}

.item.hovered {
  /* background-color: #e0e0e0; */
  box-shadow: 1px 5px 8px #888888;
  /* border: 1px solid #ccc; */
}
</style>