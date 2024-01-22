
import { store } from '@/store';

import { Axios } from 'axios';
<template>
    <main class="container-fluid">
        <h1>Project List</h1>
        <div class="row">
            <div class="col-12 col-md-4 col-lg-3" v-for="project in $store.projects" :key="project.id">
                <ul>
                    <li>
                        <router-link :to="{ name: 'project', params: { slug: item.slug } }" class="btn btn-primary" >
                            {{ item.title }}
                        </router-link>
                    </li>
                </ul>
            </div>
        </div>
        <ul>
        </ul>
    </main>
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
            }
        },
        methods: {
            // getAllProjects(){
            //     axios.get(`${this.storeapiUrl}/projects`).then((res)=>{
            //         console.log(res.data);
            //         this.store.projects = res.data.results.data;
            //     });
            // },
            getAllProjects(){
                axios.get(store.apiUrl + '/projects', { params: {'page' : this.currentPage} }).then((res) => {
                    console.log(res.data);
                    this.projects = res.data.results.data;
                    console.log(this.projects)
                    this.currentPage = res.data.results.current_page;
                    this.lastPage = res.data.results.last_page;
                })
            },
            created(){
                this.getAllProjects();
            }
        }
        
    }
</script>

<style lang="scss" scoped>

</style>