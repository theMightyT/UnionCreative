<template>
    <section 
        class="work" 
        :style="{backgroundImage:`url(${require('@/assets/images/' + data.source)})`}"
        @click="showMoreWork"
    >
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