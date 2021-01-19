 <v-container justify="start">
            <v-row class="mt-8" justify="start">
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
                        <v-row align = "end">
                            <v-col  class="d-flex" :cols = 7
                                :lg = 6
                                :sm = 6
                                :md = 6
                                :xs = 8
                                >
                                <v-img :src="item.image" aspect-ratio="0.7"></v-img>
                            </v-col>
                            <v-col class="d-flex ml-n1" align = "end"
                                :cols = 4
                                :lg = 2
                                :sm = 5
                                :md = 2 >
                                    <v-row class="d-block overlap">
                                        <div class=" d-block text-h6 text-sm-h6 text-md-h4 text-lg-h4 text-xl-h4 text-left white--text">
                                            {{item.Bride}}
                                        </div>
                                        <div class="d-block text-h6 text-sm-h6 text-md-h4 text-lg-h4 text-xl-h4 font-weight-bold text-left ml-1 pink--text">
                                            weds
                                        </div>
                                        <div class="d-block text-h6 text-sm-h6 text-md-h4 text-lg-h4 text-xl-h4 text-left ml-1 white--text">
                                            {{item.Groom}}
                                        </div>
                                        <div class="d-block text-subtitle-1 font-weight-medium text-left mt-8 grey--text">
                                            ~ {{item.Date}}
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
                <div class="mt-4 d-flex">
                    <router-link class="link text-subtitle-2 font-weight-regular"
                    to="/projects" align="start">
                    <div class="underline my-2">
                        </div>
                        <div>
                        VIEW OUR WORK
                        
                        </div>
                        <div class="underline my-2">
                        </div>
                    </router-link>
                </div>
              </v-col>
            </v-row>
        </v-container>