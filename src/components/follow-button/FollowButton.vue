<template>
  <div role="button" class="button" :class="buttonClass" @click="followClick">
    <account-plus-icon v-if="!isFollowing" fillColor="white" :size="18" />
    <check-icon v-if="isFollowing" fillColor="#737373" :size="18" />
    {{ text }}
  </div>
</template>

<script>
import AccountPlusIcon from 'vue-material-design-icons/AccountPlus.vue';
import CheckIcon from 'vue-material-design-icons/Check.vue';

export default {
  name: 'FollowButton',
  props: {
    following: Boolean
  },
  components: {
    AccountPlusIcon,
    CheckIcon
  },
  data () {
    return {
      isFollowing: this.following
    }
  },
  computed: {
    buttonClass () {
      return {
        "following": this.isFollowing
      }
    },
    text () {
      return this.isFollowing ? "Following" : "Follow"
    }
  },
  methods: {
    followClick () {
      this.isFollowing = this.isFollowing ? false : true
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/assets/global.scss";
@import "follow-button.scss";
</style>
