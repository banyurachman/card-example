<template>
  <div id="app">
    <Card
      username="EvelynVtuber"
      name="Evelyn"
      headerUrl="https://trakteer.id/storage/images/cover/cvr-I3Bgs5NTRaSqKoAaCJPMH7Puwjk4oOib1632148850.jpg"
      avatarUrl="https://trakteer.id/storage/images/avatar/ava-sTZxTrISsbgCaBZDZ5scOBZjAKf3mVWE1632148865.jpeg"
      :totalFollowers=898779
      category="Virtual Youtuber"
      desc="Evelyn, atau yang biasa dipanggil Epel adalah Virtual Youtuber dari Jakarta.">
      <SocmedButton v-for="item in socialMedia" :key="item" :name="item" :clickFunction="clickSocmedButton" />  
    </Card>

    <Card
      username="punipun7"
      name="Clarissa Punipun"
      headerUrl="https://trakteer.id/storage/images/cover/cvr-BwXgtstoi1jNzm8axvtkOP2ONS0KDxR51579621717.jpg"
      avatarUrl="https://trakteer.id/storage/images/avatar/ava-bM9Ay8G9uehD3muoOtHcUKZkksO40qab1582346273.jpg"
      :totalFollowers=1788779
      category="Cosplayer"
      desc="✦ Klik Follow. International: ko-fi.com/punipun7 ✦ Baca Wajah: Cek 'Post'">
      <SocmedButton v-for="item in socialMedia" :key="item" :name="item" :clickFunction="clickSocmedButton" />  
    </Card>

    <Card
      username="APradipta"
      name="A. Pradipta"
      headerUrl="https://trakteer.id/storage/images/cover/cvr-enQyCEGu3pk7e69ZnUNeJWQCgsTbVuAa1567525829.jpg"
      avatarUrl="https://trakteer.id/storage/images/avatar/ava-5XhKwvwR9avBtGb0SDkI1t20DbK79iBC1566949924.jpg"
      :totalFollowers=298877
      category="Comic Artist"
      desc="Ada suatu masa ketika seorang pencipta merasa tidak akan pernah berhenti berkarya.">
      <SocmedButton v-for="item in socialMedia" :key="item" :name="item" :clickFunction="clickSocmedButton" />  
    </Card>
  </div>
</template>

<script>
import Card from './components/card/Card.vue'
import SocmedButton from '@/components/socmed-button/SocmedButton.vue';

export default {
  name: 'App',
  data () {
    return {
      // Example for Socmed Button component purpose
      socialMedia: ["FacebookIcon", "TwitterIcon", "InstagramIcon", "YoutubeIcon", "LinkIcon"]
    }
  },
  components: {
    Card,
    SocmedButton
  },
  methods: {
    // Example for Socmed Button component purpose
    clickSocmedButton () {
      alert ("Custom function for slot.\nExample: Go to creator's social media page.")
    }
  }
}
</script>

<style lang="scss">
body {
  margin: 0;
  min-height: 100vh;
  display: grid;
  place-items: center;
}
#app {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  gap: 16px;
  padding: 16px;
}
</style>
