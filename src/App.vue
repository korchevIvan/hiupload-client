<template>
  <div class="w-full md:w-8/12 lg:w-6/12 mx-auto px-6 mt-6 md:mt-20">
    <header class="flex flex-wrap md:flex-no-wrap items-center justify-between mb-6 -mx-3 -mt-3">
      <ul class="flex items-center">
        <li>
          <router-link :to="{name: 'home'}" class="text-sm inline-block p-3 text-gray-800">Home</router-link>
        </li>
        <li>
          <a href="" class="text-sm inline-block p-3 text-gray-800">Your files</a>
        </li>
      </ul>

      <ul class="flex items-center">
        <li>
          <router-link :to="{name: 'login'}" class="text-sm inline-block p-3 text-gray-800">Sign In</router-link>
        </li>
        <li>
          <a href="" class="text-sm inline-block p-3 text-gray-800">Create account</a>
        </li>
      </ul>
    </header>
    <router-view/>
  </div>
</template>

<style src="./assets/styles/app.css" />