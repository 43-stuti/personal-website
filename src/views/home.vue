<template>
  <div>
    <v-row>
       <v-col class="navi" :cols = 12
              :lg = 2
              :xl = 4
              :sm = 12
              :md = 12
              :xs = 12>
                <v-app-bar-nav-icon fixed class="hidden-lg-and-up ml-12 mt-3 fixnav" @click="drawer = !drawer">

              </v-app-bar-nav-icon>
    <v-navigation-drawer v-if="drawer"
               
              v-model="drawer"
              fixed
            >
            <v-list class="mt-12 pt-12"
            dense
            nav
          >
            <v-list-item class="ml-4 mb-2"
              v-for="(routes,index) in mainNav"
              :key="index"
            >
            <a href="#" @click.prevent="goToDiv(routes,index)" :class="{activeLink: activeNav === index}">
              <v-list-item-content>
                <v-list-item-title> 
                  <v-row>
                    <v-col :cols = 2 class="mr-1"> 
                      <img src="/favicon.png" v-if="activeNav === index" height="22px" width="22px">
                       
                    </v-col>
                    <v-col :cols = 8 class="body-1 font-weight-black text-left">
                      <div>
                        {{routes.name}}
                      </div>
                      <div class="underline" :class="{activeUnderline: activeNav === index}">
                      </div>
                    </v-col>
                    
                  </v-row>
                  </v-list-item-title>
              </v-list-item-content>
            </a>
            </v-list-item>
            <v-list-item>
              <v-row class="mt-8 ml-12">
                <div class = "d-block mr-4" v-bind:class="[Classes.Description]"> 
                       <a href="https://www.linkedin.com/in/stuti-moh" class = "spacing" target="_blank"> 
                          <img src="/linkedin.png" aspect-ratio="2.1" contain>
                        </a>
                    </div>
                    <div class = "d-block mr-4" v-bind:class="[Classes.Description]"> 
                       <a href="https://github.com/43-stuti/" class = "spacing" target="_blank"> 
                          <img src="/github.png" aspect-ratio="2.1" contain>
                        </a>
                    </div>
                    <div class = "d-block mr-4" v-bind:class="[Classes.Description]"> 
                       <a href="https://gitlab.com/stuti_43" class = "spacing" target="_blank"> 
                          <img src="/gitlab.png" aspect-ratio="2.1" contain>
                        </a>
                    </div>
              </v-row>
            </v-list-item>
             <v-list-item>
                <v-row class="ml-12 text-caption font-weight-regular text-left mt-2 grey--text">
                    <a href="/resume.pdf" target="_blank" >My Resume</a>
                </v-row>
              </v-list-item>
        </v-list>
      </v-navigation-drawer>
      </v-col>
      <v-col class="main" :cols = 12
              :lg = 10
              :xl = 8
              :sm = 12
              :md = 12
              :xs = 12
      >
        <v-container ref="home" fluid class="HomeHero" fill-width
          v-bind:style ="heroHeight"
        >
            <v-container align="center">
              <v-container class="ml-8">
                <v-row align="center"> 
                  <v-col class = "mt-lg-5" align = "center"
                        :cols = 12
                        :lg = 8
                        :sm = 12
                        :md = 12>
                    <div>
                      <v-row v-bind:class="[Classes.SubText] " align='center'> 
                        <v-col>
                        
                        </v-col>
                      </v-row>
                      <v-row  class="mt-lg-4" v-bind:class="[Classes.CoverText]" align='center'>
                        <v-col>
                          Hi, I am Stuti.  <br> I am a software developer.
                        </v-col>
                      </v-row>
                      <v-row> 
                        <v-col class="align-start"
                                        :cols = 12
                                        :lg = 6
                                        :sm = 12
                                        :md = 10 >
                          <div class="d-block text-subtitle-2 font-weight-regular text-left mt-5 grey--text" :cols=5>
                            On my off days, I love building playful hardware-software interactions. Currently pursuing my Masters in Interactive Telecommunications from NYU.
                            
                            
                          </div>
                        </v-col>
                      </v-row>
                      
                        <div class="ml-2 mr-7">
                          <v-row class="mt-6 text-left text-subtitle-2 font-weight-regular text-left mt-5 grey--text">
                              Selected personal and academic work below.<br>
                          </v-row>
                          <v-row class="mb-12 text-subtitle-2 font-weight-regular text-left mt-3 grey--text">
                              For professional experience check out my <a href="https://www.linkedin.com/in/stuti-moh" target="_blank" class="inlineLink">linkedin </a> or <a href="/resume.pdf" target="_blank" class="inlineLink">resume.</a>
                          </v-row>
                        </div>
                    </div>
                  </v-col>
                </v-row>
              </v-container>
            </v-container>
        </v-container>
        <v-container ref="project" fluid fill-width class="tabs">
          <v-container>
            <v-row class="ml-8">
              <v-col v-for = "(item,index) in tabs" 
                              :key="index"
                              :item="item" 
                              :cols = 6
                              :lg = 2
                              :xl = 2
                              :sm = 6
                              :md = 3
                              :xs = 6
                              >
                    <div @click="changeTab(index)" :class="{active: state === index+1}">
                      {{item}}
                    </div>
                  
              </v-col>
            </v-row>
          </v-container>
        </v-container>
        <RecentProjects :state="state"></RecentProjects>
        <div ref="about">
          <About></About>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
// @ is an alias to /src
import RecentProjects from '@/components/RecentProjects.vue'
import About from '@/components/About.vue'
export default {
  name: 'Home',
  components: {
    RecentProjects,
    About
  },
  data() {
    return {
      Classes : {
        CoverText : 'text-h5 text-sm-h5 text-md-h5 text-lg-h3 text-xl-h5 font-weight-black text-left',
        CoverTextLight : 'text-h4 text-sm-h4 text-md-h4 text-lg-h4 text-xl-h1 font-weight-regular text-left pink--text text--darken-1 mt-4',
        SubText : 'mt-12 text-body-1 font-weight-bold cyan--text text--darken-1 text-left'
      },
      state: 1,
      tabs:['Development','Design'],
      mainNav:[{
        name:'Home',
        route:'/home',
        ref:'home'
      }, {
        name:'Projects',
        route:'/projects',
        ref:'project'
      }, {
        name:'About',
        route:'/about',
        ref:'about'
      }],
      drawer:true,
      activeNav:0
    }
  },
  computed: {
      heroHeight() {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs':
          case 'sm':
            return {height: '70vh'};
          case 'md':
            return {height: '40vh'};
          default:
            return {height: '80vh'};
        }
      }, 
      mini() {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs':
          case 'sm':
            return false;
          default:
            return true;
        }
      }
        
  },
  methods: {
    changeTab(index) {
      this.state = index+1;
    },
    goToDiv(node,index) {
      var elmnt = this.$refs[node.ref]
      this.activeNav = index;
      if(['xs','sm'].indexOf(this.$vuetify.breakpoint.name) > -1) {
        this.drawer = !this.drawer
      }
      elmnt.scrollIntoView();
    }
  },
  mounted() {
    switch (this.$vuetify.breakpoint.name) {
          case 'xs':
          case 'sm':
            this.drawer = false
          break;
          default:
            this.drawer = true
        }
  }
}
</script>

<style>
.fixnav {
  position: fixed;
  background-color: rgb(247, 247, 247)
}
.inlineLink {
  margin-right: 2px;
  margin-left: 3px;
  font-weight: 800;
}
 .v-application a .activeLink {
    color: rgb(248, 247, 247) !important;
  }
  .v-application a {
    color: #181818 !important;
  }
  a {
    color: none;
    text-decoration: none;
  }
  .underline {
    height: 4px;
    color: rgb(255, 255, 255);
  }
  .activeUnderline {
    background-color:#f04a81
  }
  .navi {
    z-index: 100;
  }
  .main {
    z-index: 50;
  }
  .HomeHero {
    height: 10vh;
    width: 100%;
    z-index: -1;
    background-color:  rgba(249, 253, 255, 0.7);
  }
  .Flowers {
      z-index: 0;
      position: absolute;
      margin-top: -100px;
  }
  .active {
    color:#c53968;
    font-weight: 600;
  }
  .tabs {
    background-color: rgb(0, 0, 0);
    color: rgb(255, 255, 255);
  }
</style>