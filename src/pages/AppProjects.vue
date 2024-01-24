<template>
    <div class="bg-dark">
        <main class="container">
        <div class="row align-items-center justify-content-center bg-dark">
            <h1 class="text-danger text-center mb-4">Projects List:</h1>
            <!-- <div class="col-12 col-md-4 col-lg-3 " v-for="project in projects" :key="project.id">
                <ul class="list-unstyled">
                    <li>
                        <router-link :to="{ name: 'single-project', params: { slug: project.slug } }" class="btn btn-primary" >
                            {{ project.title }}
                        </router-link>
                    </li>
                </ul>
            </div> -->
            <div class="card w-100 d-flex align-items-center border-0 bg-dark" style="width: 18rem;"  v-for="project in store.projects" :key="project.id">
                <img :src="`${store.imgPath}${project.image}`" alt="" class="w-50">
                <div class="card-body">
                    <p class="card-text my-4 fs-2">
                        <router-link :to="{ name: 'single-project', params: { slug: project.slug } }" class="btn btn-primary fs-3 mb-3" >
                            {{ project.title }}
                        </router-link>
                    </p>
                </div>
            </div>
            <nav class="d-flex justify-content-center align-items-center my-4">
                <ul class="pagination">
                    <li class="page-item" :class="{'disabled': currentPage === 1}">
                        <button class="page-link" :disabled="currentPage === 1" @click="getAllProjects(currentPage - 1)">Previous
                        </button>
                    </li>
                    <li class="page-item" v-for="n in lastPage">
                        <button class="page-link" @click="getAllProjects(n)">{{n}}</button>
                    </li> 
                    <li class="page-item" :class="{'disabled': currentPage === lastPage}">
                        <button class="page-link" :disabled="currentPage === lastPage" @click="getAllProjects(currentPage + 1)">Next
                        </button>
                    </li>   
                </ul>
            </nav>
        </div>
        </main>
    </div>
</template>

<script>
import {store} from '../store';
import axios from 'axios';
import AppCard from '../components/AppCard.vue';
    export default {
        name: 'AppProjects',
        components: {
            AppCard
        },
        data(){
            return {
                store,
                projects: [],
                currentPage: 1,
                lastPage: null,
                total: 0
            }
        },
        methods: {
            // getAllProjects(){
            //     axios.get(`${this.store.apiUrl}/projects${this.store.pages}${this.currentPage}`).then((res)=>{
            //         console.log(res.data);
            //         this.projects = res.data.results.data;
            //         console.log(this.projects);
            //     });
            // },
            // getAllProjects(){
            //     axios.get(store.apiUrl + '/projects', { params: {'page' : this.currentPage} }).then((res) => {
            //         console.log(res.data);
            //         this.projects = res.data.results.data;
            //         console.log(this.projects)
            //         this.currentPage = res.data.results.current_page;
            //         this.lastPage = res.data.results.last_page;
            //     })
            // },
            getAllProjects(pageNum){
                axios.get(`${this.store.apiUrl}/projects`,{params: {page: pageNum}}).then((res)=>{
                    console.log(res.data);
                    this.store.projects = res.data.results.data;
                    this.currentPage = res.data.results.current_page;
                    this.lastPage = res.data.results.last_page;
                    this.total = res.data.results.total;
                }).catch((err)=>{
                    console.log('error', err);
                })
            }
        },
        created(){
                this.getAllProjects(this.currentPage);
        },
        // mounted(){
        //      this.$watch(() => this.$route.params, (toParams, previousParams) => {
        //     if(toParams !== previousParams){
        //      this.getProduct();
        //     }
        //    }
        // )
        watch: {
        '$route.params.slug': function (newSlug, oldSlug) {
                if (newSlug !== oldSlug) {
                this.getOneProject();
            }
        }
        },
    }
</script>

<style lang="scss" scoped>
    img{
        width: 1600px;
        height: 1000px;
        object-fit: cover;
        object-position: top;
    }

</style>