<script>
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "firebase/app";
  import { onMount } from "svelte";
  import {
    getAuth,
    signInWithEmailAndPassword,
    GoogleAuthProvider,
    signInWithPopup,
  } from "firebase/auth";

  async function loginWithGoogle() {
    try {
      const auth = getAuth();
      const provider = new GoogleAuthProvider();
      await signInWithPopup(auth, provider)
        .then((result) => {
          // This gives you a Google Access Token. You can use it to access the Google API.
          const credential = GoogleAuthProvider.credentialFromResult(result);
          const token = credential.accessToken;
          // The signed-in user info.
          const user = result.user;
          // ...
        })
        .catch((error) => {
          // Handle Errors here.
          const errorCode = error.code;
          const errorMessage = error.message;
          // The email of the user's account used.
          const email = error.customData.email;
          // The AuthCredential type that was used.
          const credential = GoogleAuthProvider.credentialFromError(error);
          // ...
        });
    } catch (e) {
      console.error(e);
    }
  }

  const firebaseConfig = {
    apiKey: "AIzaSyAKoxDGbZS-ahmNr1UjSryNdi0FFBSz7mk",
    authDomain: "heyu-prod.firebaseapp.com",
    projectId: "heyu-prod",
    storageBucket: "heyu-prod.appspot.com",
    messagingSenderId: "735753354014",
    appId: "1:735753354014:web:e642503f3ea3698a8d270f",
    measurementId: "G-C6W3W60T74",
  };

  onMount(async () => {
    // Initialize Firebase
    const app = await initializeApp(firebaseConfig); //notice await .... this is golden


    const auth = getAuth();
      const provider = new GoogleAuthProvider();
      console.log(provider)
      await signInWithPopup(auth, provider)
        .then((result) => {
            console.log('----here before----')
          // This gives you a Google Access Token. You can use it to access the Google API.
          const credential = GoogleAuthProvider.credentialFromResult(result);
          const token = credential.accessToken;
          // The signed-in user info.
          const user = result.user;
          // ...
        })
        .catch((error) => {
            console.log('----here after---- ' + error)
          // Handle Errors here.
          const errorCode = error.code;
          const errorMessage = error.message;
          // The email of the user's account used.
          const email = error.customData.email;
          // The AuthCredential type that was used.
          const credential = GoogleAuthProvider.credentialFromError(error);
          // ...
        });


    //== old below here

    //const auth = getAuth(); // This should work...

    //==working
    // signInWithEmailAndPassword(auth, 'ebw@startmail.com', 'Kayismine')

    // .then((userCredential) => {
    // // Signed in
    // const user = userCredential.user;
    // console.log('---logged in---')
    // })
    // .catch((error) => {
    // console.log('---no entry---')
    // const errorCode = error.code;
    // const errorMessage = error.message;
    // });
    // });
    //==end-working
  });
</script>

<button on:click={loginWithGoogle}> Login Firebase </button>

<slot />

