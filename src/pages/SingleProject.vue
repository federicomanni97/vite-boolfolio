<template>
    <div>
        <h1>Single Project</h1>
        {{ project.title }}
    </div>
</template>

<script>
    import axios from 'axios';
    import { store } from '../store';

    export default {
        name: 'SingleProject',
        data(){
            return {
                project: null
            }
        },
        methods:{
            getProjectData(){
                console.log(this.$route);
                axios.get(`${this.store.apiUrl}/projects/${this.$route.params.slug}`).then((res)=>{
                    console.log(res.data);
                })
            }
        },
        created(){
            this.getProjectData();
        }
    }
</script>

<style lang="scss" scoped>

</style>