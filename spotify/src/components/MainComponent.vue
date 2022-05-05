<template>
    <main id="site_main">
        <div class="row">
            <div class="col" :key='index' v-for='(disco,index) in dischi'>
                <div class="card">
                    <div class="image">
                        <img :src="disco.poster" alt="">
                    </div>
                    <div class="text">
                        <h2>{{disco.title}}</h2>
                        <div class="autore">
                            <div class="nome">{{disco.author}}</div>
                            <div class="anno">{{disco.year}}</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
import axios from 'axios'

export default {
    name:'MainComponent',

    data() {
        return{
            dischi: ''
        }
    },


    mounted(){
        axios
        .get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(oggetto =>{
            
            this.dischi = oggetto.data.response
            
        })
    }
}
</script>

<style lang='scss'>
    #site_main{

        .row{
            display: flex;
            flex-wrap: wrap;

            .col{
                width:calc(100% / 5);
                

                .card{

                    .image{

                        img{
                            width: 100%;
                            aspect-ratio: 1/1;
                            object-fit: cover;

                        }
                    }

                    .text{

                        h2{

                        }

                        .autore{

                        }
                    }
                }
            }
        }
    }
</style>