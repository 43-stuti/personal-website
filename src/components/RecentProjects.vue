<template>
    <v-container fluid fill-width class="Testimonial">
        <v-container fluid fill-width>
            <v-container>
               
            </v-container>
            <v-container v-if="state==2" justify="start">
                <v-row class="mt-0" justify="start">
                    <v-col v-for = "item in slides" 
                                :item="item" 
                                :key="item.id"
                                :cols = 12
                                :lg = 6
                                :sm = 12
                                :md = 6
                                :xs = 12
                                >
                        <router-link
                            :to= "{
                                name:'PROJECTPAGE',
                                params: {slug: item.slug}
                            }">
                            <v-row class="mt-6" align = "start">
                                <v-col  class="d-flex align-start" :cols = 12
                                    :lg = 6
                                    :sm = 12
                                    :md = 6
                                    :xs = 12
                                    >
                                    <v-img :src="item.image" aspect-ratio="2.1" contain></v-img>
                                </v-col>
                                <v-col class="d-flex ml-3 align-start"
                                    :cols = 12
                                    :lg = 5
                                    :sm = 12
                                    :md = 2 >
                                        <v-row class="d-block overlap">
                                            <div class="d-block text-h6 text-sm-h6 text-md-h4 text-lg-h5 text-xl-h4 text-left font-weight-bold white--text">
                                                {{item.Title}}
                                            </div>
                                            <div class="d-block text-subtitle-2 font-weight-regular text-left mt-5 grey--text">
                                                {{item.Description}}
                                            </div>
                                             <div class="d-block text-h6 text-sm-h6 text-md-h4 text-lg-h4 text-xl-h4 font-weight-regular text-left ml-1 titleClass">
                                                <v-col class="d-inline pa-0" v-for = "tag in item.Tags" 
                                                        :key="tag"
                                                        :cols = 2
                                                        :lg = 2
                                                        :sm = 2
                                                        :md = 2
                                                        :xs = 2
                                                >
                                                    <div class="tag">
                                                        {{tag}}
                                                    </div>
                                                </v-col>
                                            </div>
                                        </v-row>
                                    
                                </v-col>
                            </v-row>
                        </router-link>
                    </v-col>
                </v-row>
                <v-row>
                    <v-col class="mt-8" 
                        :cols = 6
                        :lg = 2
                        :sm = 6
                        :md = 3> 
                    </v-col>
                </v-row>
            </v-container>
            <v-container v-if="state==1" justify="start">
                <v-row class="mt-0" justify="start">
                    <v-col v-for = "item in slides" 
                                :item="item" 
                                :key="item.id"
                                :cols = 12
                                :lg = 6
                                :sm = 12
                                :md = 6
                                :xs = 12
                                >
                        <a :href="item.link" target="_blank">
                            <v-row class="mt-6" align = "start">
                                <v-col  class="d-flex align-start" :cols = 12
                                    :lg = 6
                                    :sm = 12
                                    :md = 6
                                    :xs = 12
                                    >
                                    <v-img :src="item.image" aspect-ratio="2.1" contain></v-img>
                                </v-col>
                                <v-col class="d-flex ml-3 align-start"
                                    :cols = 12
                                    :lg = 5
                                    :sm = 12
                                    :md = 6 >
                                        <v-row class="d-block overlap">
                                            <div class="d-block text-h6 text-sm-h6 text-md-h4 text-lg-h5 text-xl-h4 text-left font-weight-bold white--text">
                                                {{item.Title}}
                                            </div>
                                            <div class="d-block text-subtitle-2 font-weight-regular text-left mt-5 grey--text">
                                                {{item.Description}}
                                            </div>
                                             <div class="d-block text-h6 text-sm-h6 text-md-h4 text-lg-h4 text-xl-h4 font-weight-regular text-left ml-1 titleClass">
                                                <v-col class="d-inline pa-0" v-for = "tag in item.Tags" 
                                                        :key="tag"
                                                        :cols = 2
                                                        :lg = 2
                                                        :sm = 2
                                                        :md = 2
                                                        :xs = 2
                                                >
                                                    <div class="tag">
                                                        {{tag}}
                                                    </div>
                                                </v-col>
                                            </div>
                                        </v-row>
                                    
                                </v-col>
                            </v-row>
                        </a>
                    </v-col>
                </v-row>
                <v-row>
                    <v-col class="mt-8" 
                        :cols = 6
                        :lg = 2
                        :sm = 6
                        :md = 3> 
                    </v-col>
                </v-row>
            </v-container>
        </v-container>
    </v-container>
</template>

<script>

  export default {
    name: 'RecentProjects',
    data() {
        return{
            Classes: {
                SectionHeading : 'cyan--text text--darken-2 font-weight-medium',
                SectionSubHeading : 'text-h5 white--text font-weight-light mt-2'
            },
            spacing : "d-inline-flex",
            development:[{  
                Title:"Mr. Scribbles",
                Date: "20 Nov'19",
                Description:"Mr scribbles is a robot that draws, but it's actions are contolled by your dance steps. Trained using Ml5 and programmed via arduino",
                Tags: ['NodeJS','Arduino','Sockets'],
                image: "/mr-scribbles.png",
                link:"https://github.com/stuti-43m/scribblesV2/blob/master/README.md"
                }, {
                Title:"The one where you are one of them",
                Date: "20 Nov'19",
                Description:"This is a chat application where your words are twisted by characters from friends. A machine-learning model trained on FRIENDS script takes your group conversation in a completely unanticipated direction.",
                Tags: ['NodeJS','VueJS','RunwayML'],
                image: "/friends-chat.png",
                link:"https://github.com/43-stuti/friends-chat-client/blob/master/README.md"
                },{ 
                Title:"Data Visualisation",
                Date: "20 Nov'19",
                Description:"Data viz for an ice-cream manufacturing company to give them a sense of regions where they could increase their presence based on the popluation density of the region",
                Tags: ['NodeJS','Javascript','Google Maps API'],
                image: "/map-viz.png",
                link:"https://github.com/stuti-43m/tntmaps/blob/master/README.md"
                }, { 
                Title:"Vue website",
                Date: "20 Nov'19",
                Description:"A website built using Vue, vue-router and vue-store. Firebase for backend and threejs for subtle graphics",
                Tags: ['VueJS','ThreeJs','Firebase'],
                image: "/nm-creations.png",
                link:"https://www.nmcreation.in/#/"
                },{ 
                Title:"Connect",
                Date: "20 Nov'19",
                Description:"Automated process to send ML generated (intended absurd) messages to your Instagram friends.",
                Tags: ['Puppeteer','NodeJS','RunwayML'],
                image: "/connect.png",
                link:"https://github.com/43-stuti/connect/blob/master/README.md"
                }, { 
                Title:"Prophecy game",
                Date: "20 Nov'19",
                Description:"A game built using p5 and contolled using arduino and a few sensors",
                Tags: ['p5.js','Arduino'],
                image: "/prophecy-game.png",
                link:"https://github.com/43-stuti/prophecy-game/blob/master/README.md"
                }],
            design:[{
                slug: 'whatsapp-redesign',    
                Title:"Whatsapp redesign",
                Date: "20 Nov'19",
                Description:"Redesign whatsapp group chats",
                Tags: ['UI','UX','Side Project'],
                image: "/whatsapp-redesign/cover.jpg"
                }, {
                slug: 'my-community',    
                Title:"My Community",
                Date: "20 Nov'19",
                Description:"An application to connect neighbours",
                Tags: ['UI','UX','Side Project'],
                image: "/my-community/cover.jpg"
                }, {
                slug: 'bubble-therapy',    
                Title:"Bubble Therapy",
                Date: "20 Nov'19",
                Description:"A system to enable acceptance of mental health",
                Tags: ['Side Project'],
                image: "/bubble-therapy/cover.jpg"
                }],
            slides:[{  
                Title:"Mr. Scribbles",
                Date: "20 Nov'19",
                Description:"Mr scribbles is a robot that draws, but it's actions are contolled by your dance steps. Trained using Ml5 and programmed via arduino",
                Tags: ['NodeJS','Arduino','Sockets'],
                image: "/mr-scribbles.png",
                link:"https://github.com/stuti-43m/scribblesV2/blob/master/README.md"
                }, {
                Title:"The one where you are one of them",
                Date: "20 Nov'19",
                Description:"This is a chat application where your words are twisted by characters from friends. A machine-learning model trained on FRIENDS script takes your group conversation in a completely unanticipated direction.",
                Tags: ['NodeJS','VueJS','RunwayML'],
                image: "/friends-chat.png",
                link:"https://github.com/43-stuti/friends-chat-client/blob/master/README.md"
                },{ 
                Title:"Data Visualisation",
                Date: "20 Nov'19",
                Description:"Data viz for an ice-cream manufacturing company to give them a sense of regions where they could increase their presence based on the popluation density of the region",
                Tags: ['NodeJS','Javascript','Google Maps API'],
                image: "/map-viz.png",
                link:"https://github.com/stuti-43m/tntmaps/blob/master/README.md"
                }, { 
                Title:"Vue website",
                Date: "20 Nov'19",
                Description:"A website built using Vue, vue-router and vue-store. Firebase for backend and threejs for subtle graphics",
                Tags: ['VueJS','ThreeJs','Firebase'],
                image: "/nm-creations.png",
                link:"https://www.nmcreation.in/#/"
                }, { 
                Title:"Connect",
                Date: "20 Nov'19",
                Description:"Automated process to send ML generated (intended absurd) messages to your Instagram friends.",
                Tags: ['Puppeteer','NodeJS','RunwayML'],
                image: "/connect.png",
                link:"https://github.com/43-stuti/connect/blob/master/README.md"
                }, { 
                Title:"Prophecy game",
                Date: "20 Nov'19",
                Description:"A game built using p5 and contolled using arduino and a few sensors",
                Tags: ['p5.js','Arduino'],
                image: "/prophecy-game.png",
                link:"https://github.com/43-stuti/prophecy-game/blob/master/README.md"
                }]
        }
    },
    props:['state'],
    methods: {
        route(item) {
            console.log('routing',item)
        }
    },
    watch: {
        state: function() {
            if(this.state == 1) {
                this.slides = this.development
            } else {
                this.slides = this.design
            }
        }
    }
  }
</script>
<style scoped>
 .Testimonial {
    background-color: rgb(0, 0, 0);
    width: 100%
 }
 .link {
     color: #ffffff;
     text-decoration: none;
 }
 .tag {
     display: inline-block;
     color: blanchedalmond;
     font-size: 12px;
     margin-right: 6px;
 }
 .underline {
    background-color: #84FFFF;
    height: 1px;
 }
 .overlap { 
     margin-bottom: 10px;
     z-index: 100;
 }
 a {
    text-decoration: none;
    }
</style>