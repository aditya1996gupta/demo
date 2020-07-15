<template>
  <div class="Home">
  <dataget />
  <postdata />
  </div>
</template>

<script>
import dataget from '@/components/dataget'
import postdata from '@/components/postdata'
export default {
  name: 'Home',
  components: {
    dataget,
    postdata
  }
}
</script>
