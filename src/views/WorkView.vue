<template>
    <section>
        <header class="work-header">
            <picture>
                <source media="(max-width: 768px)" :srcset="require('@/assets/images/sm/' + project.source)"/>
                <source media="(min-width: 769px)" :srcset="require('@/assets/images/' + project.source)"/>
                <img :src="require('@/assets/images/sm/' + project.source)" :alt="project.name + 'project image'" />
            </picture>
        </header>

        <!-- logotype rationale / grayscale -->
        <article>
            <p class="synopsis">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum, iste. Aliquid architecto iste fugiat veritatis officia animi reiciendis, earum, temporibus adipisci ratione similique ad quis eligendi quas quisquam voluptates laudantium.
            </p>

            <hr>
            
            <div class="logotypes">
                <h2 class="subhead">Logotype</h2>
                <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum animi similique aliquid dolorum explicabo, sunt dicta impedit architecto pariatur quibusdam praesentium. Maxime iure atque sequi suscipit. Vero, debitis. Perspiciatis, cum.
                </p>
            </div>

            <div class="logotypes">

            </div>

            <hr>

            <div class="challenge">
                <h2>Challenge</h2>
                <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse aspernatur maxime obcaecati sed. Doloribus ullam magni error vitae assumenda dignissimos temporibus, dolores minus animi quod neque amet quidem, repellendus ea?
                </p>
            </div>
        </article>

        <!-- logotype diagram -->
        <section>
            <header>
                <!-- logotype image here -->
                <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Eum, eaque ut? Voluptatum modi nam ad a obcaecati, vitae numquam reprehenderit optio. Cum sapiente alias minus facere eius cupiditate enim incidunt.
                </p>
                <!-- secondary image here, if there is one -->
                <img v-if="project.logo-secondary" alt="secondary-image" :src="require('@/assets/images/' + project.logo-secondary)">
            </header>
        </section>

        <!-- result section -->
        <section>
            <h2 class="subhead">result</h2>
            <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Numquam, doloremque incidunt non maxime cum sapiente. Beatae quod, reprehenderit a architecto, dicta at illum, molestiae temporibus praesentium impedit minima! Cupiditate, ab!
            </p>
        </section>

        <!-- product / branding images -->
        <section>
            product images go here
            <!-- dynamically add images in a grid here -->
            <!-- <div class="images-grid">
                <img src="" alt="">
            </div> -->
        </section>
    </section>
</template>

<script>
    import { useRoute } from 'vue-router';

    export default {
        name: "TheWorkView",
        
       data() {
        return {
            project: {}
        }
       },

        created() {
            const route = useRoute();
            console.log(route.params);

            this.project = route.params;
        },

        methods: {
            // stub
        }
    }
</script>

<style lang="scss">

    .work-header { width: 100%; }
    picture img { max-width: 100vw; }

    hr { 
        border: 1px solid $union-midgrey;
        margin: 1.8em 0;
    }

</style>