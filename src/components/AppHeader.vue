<template>
    <div class="">
      <nav class="navbar navbar-expand-lg pt-3 bg-primary">
          <!-- <a class="navbar-brand" href="#">Navbar</a>
          <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button> -->
          <div class="collapse navbar-collapse justify-content-center" id="navbarSupportedContent">
            <ul class="navbar-nav mr-auto">
              <!-- <li class="nav-item active">
                <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
              </li> -->
              <li class="nav-item text-center fs-1" v-for="item in menu" :key="index">
                <router-link :to="{name: item.name}" class=" nav-link active fs-1 text-white text-uppercase ">{{ item.label }}</router-link>
              </li>
            </ul>
            <!-- <form class="form-inline my-2 my-lg-0 d-flex">
              <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
              <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
            </form> -->
          </div>
      </nav>
    </div>
</template>

<script>
    export default {
        name: 'AppHeader',
        data(){
            return {
                menu: [
                    {
                        label: 'Home',
                        name: 'home',
                    },
                    {
                        label: 'Projects',
                        name: 'projects',
                    },
                    {
                        label: 'Contacts',
                        name: 'contacts',
                    }
                ]
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>