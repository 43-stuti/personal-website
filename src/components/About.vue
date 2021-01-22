<template>
    <v-container fluid fill-width class="aboutMain">
        <v-container fluid fill-width>
            <v-container>
                <v-container fluid fill-width class="aboutHeading">
                    About Me
                </v-container>
                <v-container>
                    <v-row class="d-block text-subtitle-2 font-weight-regular text-left grey--text">
                        <v-col
                            :cols = 12
                            :lg = 6
                            :sm = 12
                            :md = 10
                        >
                            I love fish, squirrels and I love coding and designing for the web. <br>
                            I studied <b>Computer Science</b> for my undergrad and am currently pursuing my master in <b>Interactive Telecommunications</b> from NYU.<br>
                            Prior to that, I professionally worked as a backend developer but honed up my front end skills with freelance or self initiated projects. 
                            For my self-initiated projects, I try to pick up work where I can explore playful gamified experiences for the web or interfacing hardware(primarily controlled by arduino)
                            with software. 
                        </v-col>
                    </v-row>
                    <v-row class="d-block text-subtitle-2 font-weight-regular text-left mt-3 grey--text">
                        <v-col
                            :cols = 12
                            :lg = 6
                            :sm = 12
                            :md = 10
                        >
                            Currently I spend my days looking at beautiful data visualisation work and am working on a creating a visualisation project with my friend centering around the potrayal of women in Indian cinema.<br>
                            I am also experimenting with interactive storytelling in the 3D space using unity and threejs.
                            I spend a lot of my time people and squirrel watching and my recent move to NYC has made this even more pleasurable.
                        </v-col>
                    </v-row>
                    <div class="mt-7">
                        <v-container v-for = "(item,index) in lists" class="mb-3"
                            :key="index"
                            :item="item" 
                            >
                            <v-row class="text-subtitle-2 font-weight-black mb-3">
                                {{item.text}}
                            </v-row>
                            <v-row>
                                <div v-for = "(val,innerindex) in item.values"
                                class="text-caption font-weight-medium d-flex align-start mr-3"
                                :key="innerindex"
                                :val="val"
                                >
                                    {{val}}
                                </div>
                            </v-row>
                        </v-container>
                    </div>
                </v-container>
            </v-container>
        </v-container>
    </v-container>
</template>
<script>
export default {
    name:'About',
    data() {
        return {
            Classes : {
                CoverText : 'text-h5 text-sm-h5 text-md-h5 text-lg-h3 text-xl-h5 font-weight-black text-left',
                CoverTextLight : 'text-h4 text-sm-h4 text-md-h4 text-lg-h4 text-xl-h1 font-weight-regular text-left pink--text text--darken-1 mt-4',
                SubText : 'mt-12 text-body-1 font-weight-bold cyan--text text--darken-1 text-left'
            },
            lists: [
                {
                    text:'Tools I often work with',
                    values:['Javascript','HTML/CSS','Vue','NodeJS','Loopback','mysql','mongodb','Figma','Arduino','Photoshop']
                },
                {
                    text:'Tools I am currently learning',
                    values:['d3','threejs','unity']
                }
            ]
        }
    }
}
</script>
<style scoped>
.aboutHeading {
    color:#c53968;
    font-weight: 600;
}
.aboutMain {
    background-color:  rgba(249, 253, 255, 0.7);
}
</style>
