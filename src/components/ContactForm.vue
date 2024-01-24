<template>
    <div class="container">
        <form @submit.prevent="submitForm()" class="text-white fs-3">
            <div class="mb-3">
                <label for="name" class="form-label">Your Name</label>
                <input type="text" class="form-control" id="email" aria-describedby="nameHelp" v-model="name">
                <div id="nameHelp" class="form-text">We'll never share your email with anyone else.</div>
            </div>
            <div class="mb-3">
                <label for="email" class="form-label">Email address</label>
                <input type="email" class="form-control" id="email" aria-describedby="emailHelp" v-model="email">
                <div id="emailHelp" class="form-text">We'll never share your email with anyone else.</div>
            </div>
            <div class="mb-3">
                <label for="address" class="form-label">Your Address</label>
                <input type="text" class="form-control" id="email" aria-describedby="addressHelp" v-model="address">
                <div id="addressHelp" class="form-text">We'll never share your email with anyone else.</div>
            </div>
            <div class="mb-3">
                <label for="message" class="form-label">Your message</label>
                <textarea type="text" class="form-control" id="email" aria-describedby="message" v-model="message"></textarea>
                <div id="messageHelp" class="form-text">We'll never share your email with anyone else.</div>
            </div>
            <button type="submit" class="btn btn-primary">Submit</button>
            <button type="reset" class="btn btn-info me-2">Reset</button>
        </form>
    </div>
</template>

<script>
import { store } from '../store.js';
import axios from 'axios';

    export default {
        name: 'ContactForm',
        data(){
            return{
                store,
                name: '',
                email: '',
                address: '',
                message: ''
            }
        },
        methods: {
            submitForm(){
                const formData = {
                    name: this.name,
                    email: this.email,
                    address: this.address,
                    message: this.message
                }
                axios
                .post(store.apiUrl + 'contacts', this.formData)
                .then((res)=>{
                    console.log(res.data);
                    this.name = '';
                    this.email = '';
                    this.address = '';
                    this.message = '';
                }).catch((err)=>{
                    console.log(err);
                })
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>