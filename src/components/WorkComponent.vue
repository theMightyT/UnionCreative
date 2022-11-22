<template>
    <section
        class="work"
        :style="{backgroundImage:`url(${require('@/assets/images/smallWorkImages/' + data.source)})`}"
        @click="showMoreWork">

        <article class="view-work">
            <h2 class="work-description">{{ data.desc }}</h2>
            <button>View Project</button>
        </article>


    </section>
</template>

<script>


export default {
    name: "WorkComponent",

    props: ['data'],

    methods: {
        showMoreWork() { debugger; }
    }
}
</script>

<style lang="scss">
    .work {
        background-repeat: no-repeat;
        background-size: cover;
        background-position: top center;
    }

    .view-work {         
        position: relative;
        top: 70%;
        color: white;

        h2 { 
            font-family: $union-headline; 
            font-size: 2.18em;
            font-weight: 700;
            padding: 0 1em 0.5em 1em;;
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
        }
    }

    // .work-description { color: white; }
</style>