<script lang="ts">
  import { onMount } from "svelte";
  import { initializeApp } from "firebase/app";
  import {
    getAuth,
    connectAuthEmulator,
    signInWithEmailAndPassword,
    GoogleAuthProvider,
    signInWithPopup,
  } from "firebase/auth";

//   async function loginWithGoogle() {
//     try {
//       const auth = getAuth()
//       const provider = new GoogleAuthProvider()
// 			await signInWithPopup(auth, provider)
//     } catch (e) {
//       console.error(e)
//     }
//   }

//   onMount(async () => {
//     const firebaseConfig = {
//       apiKey: "AIzaSyAKoxDGbZS-ahmNr1UjSryNdi0FFBSz7mk",
//       authDomain: "heyu-prod.firebaseapp.com",
//       projectId: "heyu-prod",
//       storageBucket: "heyu-prod.appspot.com",
//       messagingSenderId: "735753354014",
//       appId: "1:735753354014:web:e642503f3ea3698a8d270f",
//       measurementId: "G-C6W3W60T74",
//     };
//     // Initialize Firebase
//     const app = await initializeApp(firebaseConfig); //notice await .... this is golden

//     const auth = getAuth(); // This should work...
//     signInWithEmailAndPassword(auth, "ebw@startmail.com", "Kayismine")
//       .then((userCredential) => {
//         // Signed in
//         const user = userCredential.user;
//         console.log("---logged in---");
//       })
//       .catch((error) => {
//         console.log("---no entry---");
//         const errorCode = error.code;
//         const errorMessage = error.message;
//       });
//   });


</script>


<!-- <button on:click={loginWithGoogle}> push-this </button> -->
