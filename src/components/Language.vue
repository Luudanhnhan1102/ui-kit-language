<template>
  <div>
    <el-dropdown trigger="click" @command="changeLang">
      <div class="d-inline-block el-dropdown-link">
        <div class="d-inline-block">
          <svg :width="size" :height="size">
            <image
              :xlink:href="currentLanguage.icon"
              :src="currentLanguage.icon"
              :width="size"
              :height="size"
            />
          </svg>
        </div>
        {{ currentLanguage.title }}
        <i class="el-icon-arrow-down el-icon--right"></i>
      </div>
      <el-dropdown-menu slot="dropdown">
        <el-dropdown-item
          v-for="item in languages"
          :key="item.name"
          :command="item"
        >
          <div class="d-inline-block">
            <svg :width="size" :height="size">
              <image
                :xlink:href="item.icon"
                :src="item.icon"
                :width="size"
                :height="size"
              />
            </svg>
          </div>
          {{ item.title }}
        </el-dropdown-item>
      </el-dropdown-menu>
    </el-dropdown>
  </div>
</template>

<script>
export default {
  props: {
    languages: {
      type: Array,
      default: () => [
        {
          title: "English",
          name: "eng",
          icon: "/static/flag_en.svg",
        },
        {
          title: "Việt Nam",
          name: "vni",
          icon: "/static/flag_fr.svg",
        },
      ],
    },
    size: {
      type: [String, Number],
      default: 30,
    },
  },
  data() {
    return {
      currentLanguage: this.languages[0],
    };
  },
  methods: {
    changeLang(command) {
      this.currentLanguage = command;
      this.$emit("change", command);
    },
  },
};
</script>
