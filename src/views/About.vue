<template>
  <div class="Home">
  <br />
  <h1>Proper Form Handling in Vue.js</h1>
  <formhgood /><br />
  <formhbad />
  <notify />
  </div>
</template>

<script>
import formhgood from '@/components/formhgood.vue'
import formhbad from '@/components/formhbad.vue'
import notify from '@/components/notify.vue'
export default {
  name: 'Home',
  components: {
    notify,
    formhgood,
    formhbad
  }
}
</script>
