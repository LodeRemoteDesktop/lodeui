<template>
    <div>
        <img src="~assets/profile.webp" class="rounded navbar_icon_height" @click="isLoginOpened = true" height="28"
            alt="Login" />
        <b-modal v-model="isLoginOpened" has-modal-card trap-focus :destroy-on-hide="false" aria-role="dialog"
            aria-label="Login Dialog" close-button-aria-label="Close" aria-modal>
            <form action="">
                <div class="modal-card" style="width: auto">
                    <header class="modal-card-head">
                        <p class="modal-card-title">Login</p>
                    </header>
                    <section class="modal-card-body">
                        <b-field label="Email">
                            <b-input type="email" v-model="email" placeholder="Email" required>
                            </b-input>
                        </b-field>

                        <b-field label="Password">
                            <b-input type="password" v-model="password" password-reveal placeholder="Password" required>
                            </b-input>
                        </b-field>
                    </section>
                    <footer class="modal-card-foot">
                        <b-button label="Close" @click="isLoginOpened = false" />
                        <b-button label="Login" type="is-primary" @click="handleSubmit()" />
                    </footer>
                </div>
            </form>
        </b-modal>
    </div>
</template>

<script setup>
import 'buefy/dist/buefy.css'
import { ref } from "vue";

const isLoginOpened = ref(false);

const email = ref("");
const password = ref("");

function handleSubmit() {
    console.log("Email: ", email.value, "\nPassword: ", password.value);
}
</script>

<style>
.navbar_icon_height {
    height: 7.5vh;
    /* width: 7.5vw; */
}

.rounded {
    border-radius: 50%;
}
</style>