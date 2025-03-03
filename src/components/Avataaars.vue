<template>
  <svg
    xmlns="http://www.w3.org/2000/svg"
    :width="width"
    :height="height"
    :viewBox="`0 0 ${maxWidth} ${maxHeight}`"
    :aria-labelledby="iconName"
    role="avatar"
  >
    <title :id="iconName" lang="en">
      {{ iconName }}
    </title>

    <Background
      :type="avatarOptions.backgroundType"
      :color="avatarOptions.backgroundColor"
    />

    <Body :color="avatarOptions.skinColor" />

    <Clothes
      :type="avatarOptions.clothesType"
      :color="avatarOptions.clothesColor"
      :graphic="avatarOptions.clothesGraphicsType"
    />

    <Face
      :eyebrowType="avatarOptions.eyebrowType"
      :eyesType="avatarOptions.eyesType"
      :mouthType="avatarOptions.mouthType"
      :facialHairType="avatarOptions.facialHairType"
      :facialHairColor="avatarOptions.facialHairColor"
      :topType="avatarOptions.topType"
      :topColor="avatarOptions.topColor"
    />

    <Accessories :type="avatarOptions.accessoriesType" />
  </svg>
</template>

<script>
// import { mapState } from 'vuex'

import Background from "vue-avataaars/src/icons/background/Background";
import Body from "vue-avataaars/src/icons/Body";
import Clothes from "vue-avataaars/src/icons/clothes/Clothes";
import Face from "vue-avataaars/src/icons/face/Face";
import Accessories from "vue-avataaars/src/icons/top/accessories/Accessories";

import optionsJSON from "vue-avataaars/src/avataaarsOptions.json";

export default {
  name: "Avataaars",
  components: {
    Background,
    Body,
    Clothes,
    Face,
    Accessories,
  },
  props: {
    iconName: {
      type: String,
      default: "avatar",
      required: false,
    },
    width: {
      type: Number,
      default: 264,
      required: false,
    },
    height: {
      type: Number,
      default: 280,
      required: false,
    },
    maxWidth: {
      type: Number,
      default: 264,
      required: false,
    },
    maxHeight: {
      type: Number,
      default: 280,
      required: false,
    },
    avatarOptions: {
      type: Object,
      required: false,
    },
  },
  data() {
    return {
      options: optionsJSON.tabs,
    };
  },
  methods: {
    forceUpdate() {
      this.$forceUpdate();
    },
  },
};
</script>

<style scoped></style>
