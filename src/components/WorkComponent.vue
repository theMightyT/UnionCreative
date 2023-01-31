<template>
    <section
        class="work"
        :id="data.name"
    > <!-- end open section tag -->
        <!-- <pre>{{ data }}</pre> -->
        <!-- responsive images - can't use dynamic background images here -->
        <picture>
            <source media="(max-width: 768px)" :srcset="require('@/assets/images/sm/' + data.source)"/>
            <source media="(min-width: 769px)" :srcset="require('@/assets/images/' + data.source)"/>
            <img :src="require('@/assets/images/sm/' + data.source)" :alt="data.name + 'project image'" />
        </picture>

        <!-- flex container to force text to bottom -->
        <div class="text-wrapper">
            <h2 class="work-description" v-html="data.desc"></h2>
        </div>
        
        <!-- <router-link to="/project"></router-link> -->
        <button @click="showMoreWork">View Project</button>
    </section>
</template>

<script>


export default {
    name: "WorkComponent",

    props: ['data'],


    methods: {
        showMoreWork() {
            this.$router.push({name: "project", params: this.data}); 
        },
    }
}
</script>

<style lang="scss">
    .work {
        color: white;
        position: relative;

        picture {
            display: flex;
            justify-content: center;

            overflow: hidden;
        }

        .text-wrapper {
            display: flex;
            align-items: flex-end;
            position: absolute;
            min-height: 85px;
            top: 73%;

            h2 {            
                font-family: $union-headline; 
                font-size: 2em;
                font-weight: 700;
                padding: 0 0.6em;    
            }
        }        

        button {
            display: block;
            width: 226px;
            height: 52px;
            background-color: $union-darkgrey;
            color: inherit;
            font-weight: bold;
            font-size: 1.56em;
            border-radius: 16px;
            margin: 0 auto;

            position: absolute;
            bottom: 7%;
            left: 0;
            right: 0;            
        }
    }

    .view-work {         
        position: relative;
        top: 73%;
        color: white;

        h2 { 
            font-family: $union-headline; 
            font-size: 2em;
            font-weight: 700;
            padding: 0 0.5em;
            // margin-bottom: 0.5em;
            vertical-align: bottom;
        }
    }

    @media only screen and (min-width: 768px) {
        .view-work br { display: none; }
    }
</style>