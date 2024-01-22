
import { store } from '@/store';

import { Axios } from 'axios';
<template>
    <div>
        <h1>Project List</h1>
        <ul>
            <li v-for="project in $store.projects" :key="project.id">
                <router-link :to="{ name: 'project', params: { slug: item.slug } }" class="btn btn-primary" >
                    {{ item.title }}
                </router-link>
            </li>
        </ul>
    </div>
</template>

<script>
import {store} from './../router/store';
import axios from 'axios';
    export default {
        name: 'AppProjects'
        data(){
            return {
                store
            }
        },
        methods: {
            getAllProjects(){
                axios.get(`${this.storeapiUrl}/projects`).then((res)=>{
                    console.log(res.data);
                    this.store.projects = res.data.results.data;
                });
            },
            created(){
                this.getAllProjects();
            }
        }
        
    }
</script>

<style lang="scss" scoped>

</style>