<template>
    <div>
        <h1 class="text-danger text-center py-4">Contact Me!</h1>
        <ContactForm/>
    </div>
</template>

<script>
import ContactForm from '../components/ContactForm.vue'
    export default {
        name: 'AppContact',
        components: {
            ContactForm
        }
        
    }
</script>

<style lang="scss" scoped>

</style>