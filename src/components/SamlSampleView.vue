<template>
  <button v-on:click="samlSample">PopUp</button>
</template>

<script>
import { SAMLAuthProvider } from "firebase/auth";
import { initializeApp } from "firebase/app";
import { getAuth, signInWithPopup } from "firebase/auth";
export default {
  name: 'SamlSample',
  props: {
    msg: String
  },
  methods: {
    samlSample: async function() {
      const firebaseConfig = {
        apiKey: "....",
        authDomain: "....",
        projectId: "....",
        storageBucket: "....",
        messagingSenderId: "....",
        appId: "...."
      };

      const app = initializeApp(firebaseConfig);
      // await initializeApp(config);
      const auth = getAuth(app);
      const provider = new SAMLAuthProvider("saml.docopuru-sample");
      console.log(provider);
      try {
        const loginResponse = await signInWithPopup(auth, provider);
        console.log(loginResponse);
      } catch (e) {
        console.error(e);
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
