<template>
  <div>
    <QuestionForm />
  </div>
</template>

<script>
import QuestionForm from '@/components/QuestionForm.vue'
import Swal from 'sweetalert2'

export default {
  name: 'askQuestion',
  components: {
    QuestionForm
  },
  beforeRouteEnter(to, from, next) {
    if (localStorage.getItem('token')) {
      next()
    } else {
      Swal.fire({
        icon: 'info',
        title: 'Oops...',
        text: 'Sorry, you are not legged in'
      })
      next('/')
    }
  }
}
</script>
