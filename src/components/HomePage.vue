<template>
  <div class="outermost">
    <div class="navigation bg-black">
      <div class="container text-white h-16">
        <div class="navbar flex justify-between">
          <div class="logo mx-8 font-bold text-2xl my-4">
            Quiz<span class="text-yellow-500">Mania</span>
          </div>
          <div class="nav_items flex space-x-8 my-4 font-medium -mx-11">
            <div class="
                li_items hover:text-yellow-500 hover:font-bold hover:underline hover:underline-offset-8 cursor-pointer">
              Home
            </div>
            <div class="
                li_items hover:text-yellow-500 hover:font-bold hover:underline hover:underline-offset-8 cursor-pointe">
              About
            </div>
            <div class="
                li_items hover:text-yellow-500 hover:font-bold hover:underline hover:underline-offset-8 cursor-pointe">
              Prepare
            </div>
            <div class="
                li_items hover:text-yellow-500 hover:font-bold hover:underline hover:underline-offset-8 cursor-pointe">
              Leaderboard
            </div>
            <div class="buttons space-x-5">
              <button class="
                  btn bg-purple-800 w-24 h-8 text-white font-bold text-sm rounded-md hover:bg-purple-900">
                Account
              </button>
              <!-- <button class="
                  btn bg-purple-800 w-16 h-8 text-white font-bold text-sm rounded-md hover:bg-purple-900">
                Sign Up
              </button> -->
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Quiz part middle start -->
    <div class="middle  bg-[#131417] flex flex-col  justify-center items-center ">
      <div class="recentQuiz h-fit w-[80%] flex flex-col justify-center border-2 border-green-400 items-center px-12 mt-10 text-white">
        <div class="heading  font-bold text-2xl mt-8 mb-4 font-mono"><h1>Recently Added Quizzes</h1></div>
        <div class="topics border-2 border-white hover:border-green-500 w-[50%] p-10  text-green-700 font-sans font-bold">
          <h2 class="hover:text-white hover:underline cursor-pointer">Array and Array Operations</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Stack Operations – 1</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Stack Operations – 2</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Singly Linked Lists Operations</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Doubly Linked List</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Circular Linked Lists</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Queue using Linked List</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Double Ended Queue (Dequeue)</h2>
        </div>
        <div class="btn h-10 mb-10 w-52 mt-6 font-bold  border-2 border-white flex justify-center items-center text-white rounded-sm hover:border-green-500 hover:text-green-500 "><router-link to="/quiz" exact>Attempt Quiz Now</router-link></div>
      </div>
      <div class="trendingQuiz h-fit w-[80%] flex flex-col justify-center border-2 border-green-400 items-center px-12 mt-10 text-white">
        <div class="heading font-bold text-2xl my-4 font-mono"><h1>Trending  Quizzes</h1></div>
        <div class="topics border-2 border-white hover:border-green-500 w-[50%] p-10  text-green-700 font-sans font-bold">
          <h2 class="hover:text-white hover:underline cursor-pointer">C Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">C++ Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Java Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Python Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Data Structures Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Algorithms Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Algorithms Mock Tests</h2>
        </div>
        <div class="btn h-10 mb-10 w-52 mt-6 font-bold  border-2 border-white flex justify-center items-center text-white rounded-sm hover:border-green-500 hover:text-green-500 "><router-link to="/quiz" exact>Attempt Quiz Now</router-link></div>
      </div>
      <div class="recommendedQuiz h-fit w-[80%] flex flex-col justify-center border-2 border-green-400 items-center px-12 mt-10 text-white">
        <div class="heading font-bold text-2xl my-4 font-mono"><h1>Recommended Quizzes For You</h1></div>
        <div class="topics border-2 border-white hover:border-green-500 w-[50%] p-10  text-green-700 font-sans font-bold">
          <h2 class="hover:text-white hover:underline cursor-pointer">C Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">C++ Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Java Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Python Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Data Structures Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Algorithms Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Algorithms Mock Tests</h2>
        </div>
        <div class="btn h-10 mb-10 w-52 mt-6 font-bold  border-2 border-white flex justify-center items-center text-white rounded-sm hover:border-green-500 hover:text-green-500 "> <router-link to="/quiz" exact>Attempt Quiz Now</router-link></div>
      </div>
    </div>
    <!-- Quiz part middle end -->

  </div>
  </template>
  
  <script>
  export default {
  
  }
  </script>
  
  <style scoped>
    

  </style>