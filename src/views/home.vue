<template>
  <div>
    <v-container fluid class="HomeHero" fill-width fill-height
      v-bind:style ="heroHeight"
    >
        
    </v-container>
    <v-container fluid fill-width class="tabs">
      <v-container>
        <v-row>
          <v-col v-for = "(item,index) in tabs" 
                          :key="index"
                          :item="item" 
                          :cols = 4
                          :lg = 2
                          :xl = 2
                          :sm = 4
                          :md = 3
                          :xs = 4
                          >
                <div @click="changeTab(index)" :class="{active: state === index+1}">
                  {{item}}
                </div>
              
          </v-col>
        </v-row>
      </v-container>
    </v-container>
    <RecentProjects :state="state"></RecentProjects>
  </div>
</template>

<script>
// @ is an alias to /src
import RecentProjects from '@/components/RecentProjects.vue'
export default {
  name: 'Home',
  components: {
    RecentProjects
  },
  data() {
    return {
      Classes : {
        CoverText : 'text-h4 text-sm-h4 text-md-h2 text-lg-h2 text-xl-h1 font-weight-black text-left',
        CoverTextLight : 'text-h4 text-sm-h4 text-md-h4 text-lg-h4 text-xl-h1 font-weight-regular text-left pink--text text--darken-1 mt-4',
        SubText : 'mt-12 text-body-1 font-weight-bold pink--text text--darken-1 text-left'
      },
      state: 1,
      tabs:['Development','Design']
    }
  },
  computed: {
      heroHeight() {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs':
          case 'sm':
            return {height: '550px'};
          default:
            return {height: '650px'};
        }
      }
  },
  methods: {
    changeTab(index) {
      this.state = index+1;
    }
  }
}
</script>

<style>
    .HomeHero {
    height: 100%;
    width: 100%;
    z-index: -1;
    background-color:  rgba(255, 249, 253, 0.7);
  }
   .Flowers {
       z-index: 0;
       position: absolute;
       margin-top: -100px;
    }
  .Welcome {
       z-index: 1;
  }
  .active {
    color: #84FFFF;
    font-weight: 600;
  }
.tabs {
  background-color: rgb(0, 0, 0);
  color: rgb(255, 255, 255);
}
</style>