<template>
  <div class="card">
    <div class="card__header">
      <img :src="headerUrl" alt="">
      <dots-vertical-icon fillColor="white" @click="moreButtonClick" />
    </div>
    <div class="card__avatar-follow">
      <img :src="avatarUrl" alt="">
      <FollowButton />
    </div>
    <div class="card__name">
      <div class="card__name-full">{{ name }}</div>
      <div class="card__name-id">@{{ username }}</div>
    </div>
    <p class="card__desc">
      {{ desc }}
    </p>
    <div class="card__info">
      <div class="card__info-followers"><span>{{ numberOfFollowers }}</span> Followers</div>
      <div class="card__info-divider"></div>
      <div class="card__info-category">{{ category }}</div>
    </div>
    <slot />
  </div>
</template>

<script>
import DotsVerticalIcon from 'vue-material-design-icons/DotsVertical.vue';
import FollowButton from '@/components/follow-button/FollowButton.vue';

export default {
  name: 'Card',
  props: {
    name: String,
    username: String,
    headerUrl: String,
    avatarUrl: String,
    totalFollowers: Number,
    category: String,
    desc: String
  },
  components: {
    DotsVerticalIcon,
    FollowButton
  },
  computed: {
    numberOfFollowers () {
      const number = this.totalFollowers
      if (number > 999999) {
        const result = (number/1000000).toFixed(2)
        return `${result}m`
      }
      if (number > 999) {
        const result = (number/1000).toFixed(2)
        return `${result}k`
      }
      return number
    }
  },
  methods: {
    moreButtonClick () {
      alert("Custom function.\nExample: Open menu dropdown.")
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/assets/global.scss";
@import "card.scss";
</style>
