<template>
  <div class="content"> 
    <UserProfile />
    <BeerProfile />
  </div>
</template>

<script>
import UserProfile from './components/UserProfile.vue'
import BeerProfile from './components/BeerProfile.vue'


export default {
  name: 'App',
  components: {
    UserProfile,
    BeerProfile
  }
}
</script>

<style>
  .content {
display:flex;
  }

@media  screen and (max-width: 768px) {

.content {
flex-direction: column; 
 }
}
</style>
