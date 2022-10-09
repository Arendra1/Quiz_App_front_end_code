<template>
  <div class="outermost">
    <!-- Navigation start -->
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
            <!-- <div class="
                li_items hover:text-yellow-500 hover:font-bold hover:underline hover:underline-offset-8 cursor-pointe">
              Prepare
            </div> -->
            <div class="
                li_items hover:text-yellow-500 hover:font-bold hover:underline hover:underline-offset-8 cursor-pointe">
              Leaderboard
            </div>
            <div class="buttons space-x-5">
              <button class="
                  btn bg-purple-800 w-20 h-8 text-white font-bold text-sm rounded-md hover:bg-purple-900">
                Account
              </button>
              <button class="
                  btn bg-purple-800 w-24 h-8 text-white font-bold text-sm rounded-md hover:bg-purple-900">
                Contact Us
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- Navigation end -->

    <!-- Middle part start -->
    <div class="middle bg-[#131417] h-screen flex flex-col  justify-center items-center">

        <div class="recentQuiz  w-[80%] h-4/5 flex flex-col justify-center items-center border-2 border-green-400 -mt-30 text-white">
        <div class="heading  font-bold text-2xl my-4 font-mono"><h1>RECENTLY QUIZZES ADDED BY YOU</h1></div>
        <div class="topics border-2 border-white hover:border-green-500 w-[50%] p-10 text-green-700 font-sans font-bold">
          <h2 class="hover:text-white hover:underline cursor-pointer">Array and Array Operations</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Stack Operations – 1</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Stack Operations – 2</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Singly Linked Lists Operations</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Doubly Linked List</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Circular Linked Lists</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Queue using Linked List</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Double Ended Queue (Dequeue)</h2>
        </div>
        <div class="btn h-10 w-40 mt-4 font-bold  border-2 border-white flex justify-center items-center text-white rounded-sm hover:border-green-500 hover:text-green-500 "> <router-link to="/addQuiz" exact>Add a new Quiz</router-link>  </div>
      </div>
        
    </div>

    <!-- Middle part end -->

  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>