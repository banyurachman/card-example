<template>
  <div role="button" class="button">
    <component :is="name" fillColor="#949494" :size="20" @click="clickFunction" />
  </div>
</template>

<script>
import FacebookIcon from 'vue-material-design-icons/Facebook.vue';
import TwitterIcon from 'vue-material-design-icons/Twitter.vue';
import InstagramIcon from 'vue-material-design-icons/Instagram.vue';
import YoutubeIcon from 'vue-material-design-icons/Youtube.vue';
import LinkIcon from 'vue-material-design-icons/Link.vue';

export default {
  name: 'SocmedButton',
  props: {
    name: String,
    clickFunction: Function
  },
  components: {
    FacebookIcon,
    TwitterIcon,
    InstagramIcon,
    YoutubeIcon,
    LinkIcon
  }
}
</script>

<style lang="scss" scoped>
@import "@/assets/global.scss";
@import "socmed-button.scss";
</style>
