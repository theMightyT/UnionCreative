<template>
    <section class="contact-section" ref="contact">
        <header>
            <h1 class="hidden">contact form</h1>
            <h2>How can we help?</h2>
            <p>Please use the form below. We appreciate your interest and will respond as soon as possible.</p>
            <nav>
                <span @click="closeContact" class="close">X</span>
            </nav>
        </header>

        <form action="" class="contact-form" ref="contactform">
            <label for="username">Name:</label>
            <input type="text" name="username" placeholder="name" required>

            <label for="usermail">Email:</label>
            <input type="email" name="usermail" placeholder="email" required>

            <label for="phone">Phone (optional):</label>
            <input type="tel" name="phone" placeholder="phone" required>

            <label for="message">How can we help?</label>
            <textarea name="message" id="message" placeholder="enter message" required></textarea>

            <input type="submit" value="Go!">
        </form>
    </section>
</template>

<script>
export default {
    name: 'TheContactForm',

    emits: ['closeform'],

    created() {
        console.log('contact form up');
    },

    methods: {
        closeContact() {
            // emit the close contact form event
            this.$emit('closeform');
            this.$refs['contactform'].reset();
        }
    }
}
</script>

<style lang="scss">
    .contact-section {
        position: absolute;
        height: auto;
        width: 100vw;
        background: rgba(0, 0, 0, 0.88);
        color: white;
        padding-top: 4em;
        padding-left: 2.5em;
        left: -100vw;

        z-index: 5000;

        transition: all 0.8s ease;

        header {
            h2{ font-family: $union-headline; font-size: 2.5em; }

            p { font-size: 1.2em; width: 60%; margin: 1em 0 1.5em 0; line-height: 1.5; }

            nav {
                position: absolute; 
                top: 1em; 
                right: 1em;

                span { cursor: pointer; }
            }
        }

        form { 
            margin-top: 2em;

            label { 
                display: none;
                margin-bottom: 0.75em;
            }

            textarea { height: 150px; }

            input[type="submit"] { 
                font-size: 1.2em; 
                width: 100px; 
                margin-bottom: 4em;
                padding: 1em 0.5em;
                cursor: pointer;
                border: 2px solid rgba(74, 217, 13, 0.452);
                background-color: rgba(74, 217, 13, 0.1);
                color: white;
            }

            input[type="submit"]:hover { background-color: rgba(74, 217, 13, 0.452); }

            input:not([type="submit"]), textarea { 
                margin-bottom: 2em;
                font-size: 1.2em;
                padding: 0.5em 1em;
                // border-radius: 0.25em;

                background-color: rgba(0,0,0,0);
                color: white;

                border-left: 1px solid white;
            }

            input:not([type="input"]):focus, textarea:focus { background-color: rgba(0, 0, 0, 0.1); outline: none; }
        }
    }

    @media screen and (min-width: 768px) {
        .contact-section { 
            width: 75%;

            input { width: 75%; }
            textarea { width: 90%; }
        }
    }

    @media screen and (min-width: 1080px) {
        .contact-section {width: 55%; }
    }

    .show-form { left: 0; }
</style>