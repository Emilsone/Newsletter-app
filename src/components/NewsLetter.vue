<template>
  <section class="text-gray-600 body-font">
    <div class="container px-5 py-24 mx-auto flex flex-wrap items-center">
      <div class="lg:w-3/5 md:w-1/2 md:pr-16 lg:pr-0 pr-0">
        <h1 class="title-font font-medium text-3xl text-gray-900">Welcome to Trackee Newsletter</h1>
        <p class="leading-relaxed mt-4">Join our weekly newsletter. You'll also get some of our finest posts every week.
</p>
      </div>
      <form ref="form" autocomplete="off" class="lg:w-2/6 md:w-1/2 bg-gray-100 rounded-lg p-8 flex flex-col md:ml-auto w-full mt-10 md:mt-0 add"
        id="app">
        <h2 class="text-gray-900 text-lg font-medium title-font mb-5">Sign Up</h2>
        <div class="relative mb-4">
          <label for="full-name" class="leading-7 text-sm text-gray-600" >Full Name</label>
          <input ref="name" type="text"  name="name"
            class="w-full bg-white rounded border border-gray-300 focus:border-indigo-500 focus:ring-2 focus:ring-indigo-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out" >
        </div>
        <div class="relative mb-4">
          <label for="email" class="leading-7 text-sm text-gray-600" >Email</label>
          <input ref="email"  type="email" name="email"
            class="w-full bg-white rounded border border-gray-300 focus:border-indigo-500 focus:ring-2 focus:ring-indigo-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out">
        </div>
        <button @click.prevent="createNewSuscriber"
          class="text-white btn-bg border-0 py-2 px-8 focus:outline-none rounded text-lg">Send</button>
      </form>
    </div>
  </section>
</template>
<script>
import {
  getFirestore,
  collection,
  addDoc
} from 'firebase/firestore';
import { initializeApp } from 'firebase/app';

import { ref } from 'vue';


// Paste your Your web app's Firebase configuration
const firebaseConfig = {
  apiKey: 'AIzaSyBHgT-oUhDc3Ek6KxaiGx_MmsoFlN9CyM4',
  authDomain: 'newsletter-page-93305.firebaseapp.com',
  projectId: 'newsletter-page-93305',
  storageBucket: 'newsletter-page-93305.appspot.com',
  messagingSenderId: '769518697047',
  appId: '1:769518697047:web:a02dd0a10fcc37a3340112',
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);

// cloud firestore 
const db = getFirestore(app);
export default {
  name: 'App',
  components: {},
  methods: {
    createNewSuscriber: function () {
      addDoc(collection(db, 'EmailCollection'), {
        name: this.$refs.name.value,
        email: this.$refs.email.value,
       
      });
      this.$refs.form.reset();
    },
  },
  data: () => {
    return {
      suscribers: ref([]),
    };
  },
};
</script>

<style>

.btn-bg{
  background-color: #1D1D1D;
}
</style>

