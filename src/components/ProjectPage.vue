<template>
    <v-container fluid fill-width class="Testimonial">
        <v-container fluid fill-width>
            <v-container justify="start">
                <v-row v-for = "(item,index) in currentProject" class="mb-1" justify="start" 
                     :key="index"
                     :item="item" 
                    >
                   <v-col class="d-flex" :cols = 12
                            :lg = 12
                            :sm = 12
                            :md = 12
                            :xs = 12
                            >
                            <v-img :src="item" aspect-ratio="1.5"></v-img>
                        </v-col>
                </v-row>
             </v-container>
        </v-container>
    </v-container>
   
</template>
<script>
export default {
    name:'ProjectPage',
    data()  {
        return {
            slug: null,
            TextStyles : [{
                color : "#000000"
            }],
            Overlay:false,
            Classes : {
                CoverText : 'text-h4 text-sm-h4 text-md-h2 text-lg-h2 text-xl-h1 font-weight-black text-left',
                CoverTextLight : 'text-h4 text-sm-h4 text-md-h2 text-lg-h2 text-xl-h1 font-weight-medium text-left pink--text text--darken-12',
                SubText : 'mt-4 text-h6 text-lg-h5 font-weight-medium text-left deep-purple--text text--darken-4',
                SectionHeading : 'grey--text text--darken-4',
                SectionSubHeading : 'text-h5 font-weight-bold mt-2',
                OverridingClass : 'text--white'
            },
            currentProject : [],
            projects: {
                'whatsapp-redesign':[1,2,3,4,5,6,7],
                'my-community':[1,2,3,4,5,6],
                'bubble-therapy':[1,2,3,4,5]
            }
        }
    },
    methods: {
    },
    computed: {
    },
    created() {
    }, 
    mounted() {
      this.slug = this.$route.params.slug;
      for(let i=0;i<this.projects[this.slug].length;i++) {
          let path = "/"+this.slug+'/'+this.projects[this.slug][i].toString()+'.jpg';
          this.currentProject.push(path)
      }
    }
}

</script>
<style scoped>
    .Cover {
        height: 5%;
    }
</style>