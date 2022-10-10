<template>
  <div class="outermost">
    <div class="navigation bg-black">
      <div class="container text-white h-16">
        <div class="navbar flex justify-between">
          <div class="logo mx-8 font-bold text-2xl my-4">
            Quiz<span class="text-yellow-500">Mania</span>
          </div>
          <div class="nav_items flex space-x-8 my-4 mr-10 font-medium -mx-11">
            <div
              class="
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
            <div @click="leaderBoard()" class="
                li_items hover:text-yellow-500 hover:font-bold hover:underline hover:underline-offset-8 cursor-pointe">
              Leaderboard
            </div>
            <div class="buttons space-x-5">
              <div class="user absolute">
                <button @click="profile()" class="
                  btn bg-purple-800 w-20 h-8  right-10  text-white font-bold text-sm rounded-md hover:bg-purple-900">
                  Profile
                </button>
                <div v-show="success"
                  class="z-10 h-76 w-96  p-10 relative border-2 border-[#f3f7f7] top-4 text-white right-52 bg-[#131417]"
                  id="profile">
                  <h1 class="font-bold font-mono text-2xl ml-16 -mt-4 mb-8">UPDATE PROFILE</h1>
                  <div class="form flex flex-col justify-center items-center space-y-8">
                    <div class="name">
                      <label class="font-bold font-mono text-md" for="">Name: </label>
                      <input
                        class="h-12 w-56 px-2 rounded-sm  bg-green-500 border-2 border-[#f3f7f7] hover:focus cursor-pointer"
                        type="text" v-model="name">
                    </div>
                    <div class="email"><label class="font-bold font-mono text-md" for="">Email: </label>
                      <input
                        class="h-12 w-56 px-2 rounded-sm  bg-green-500 border-2 border-[#f3f7f7] hover:focus cursor-pointer"
                        type="email" v-model="email">
                    </div>
                    <div class="accesslevel"><label class="font-bold font-mono text-md" for="">User: </label>
                      <input
                        class="h-12 w-56 px-2 rounded-sm  bg-green-500 border-2 border-[#f3f7f7] hover:focus cursor-pointer"
                        type="email" v-model="accessLevel">
                    </div>
                    <div class="accesslevel"><label class="font-bold font-mono text-md" for="">Score: </label>
                      <input
                        class="h-12 w-56 px-2 rounded-sm  bg-green-500 border-2 border-[#f3f7f7] hover:focus cursor-pointer"
                        type="email" v-model="score">
                    </div>


                  </div>
                </div>
              </div>
              <button @click="logout()"
                class="
                  btn bg-purple-800 w-20 h-8 relative -right-20 text-white font-bold text-sm rounded-md hover:bg-purple-900">
                Log out
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Quiz part middle start -->
    <!-- <div class="middle  bg-[#131417] flex flex-col  justify-center items-center ">
      <div
        class="recentQuiz h-fit w-[80%] flex flex-col justify-center border-2 border-green-400 items-center px-12 mt-10 text-white">
        <div class="heading  font-bold text-2xl mt-8 mb-4 font-mono">
          <h1>Recently Added Quizzes</h1>
        </div>
        <div
          class="topics border-2 border-white hover:border-green-500 w-[50%] p-10  text-green-700 font-sans font-bold">
          <h2 class="hover:text-white hover:underline cursor-pointer">Array and Array Operations</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Stack Operations – 1</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Stack Operations – 2</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Singly Linked Lists Operations</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Doubly Linked List</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Circular Linked Lists</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Queue using Linked List</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Double Ended Queue (Dequeue)</h2>
        </div>
        <div
          class="btn h-10 mb-10 w-52 mt-6 font-bold  border-2 border-white flex justify-center items-center text-white rounded-sm hover:border-green-500 hover:text-green-500 ">
          <router-link to="/quiz" exact>Attempt Quiz Now</router-link>
        </div>
      </div>
      <div
        class="trendingQuiz h-fit w-[80%] flex flex-col justify-center border-2 border-green-400 items-center px-12 mt-10 text-white">
        <div class="heading font-bold text-2xl my-4 font-mono">
          <h1>Trending Quizzes</h1>
        </div>
        <div
          class="topics border-2 border-white hover:border-green-500 w-[50%] p-10  text-green-700 font-sans font-bold">
          <h2 class="hover:text-white hover:underline cursor-pointer">C Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">C++ Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Java Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Python Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Data Structures Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Algorithms Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Algorithms Mock Tests</h2>
        </div>
        <div
          class="btn h-10 mb-10 w-52 mt-6 font-bold  border-2 border-white flex justify-center items-center text-white rounded-sm hover:border-green-500 hover:text-green-500 ">
          <router-link to="/quiz" exact>Attempt Quiz Now</router-link>
        </div>
      </div>
      <div
        class="recommendedQuiz h-fit w-[80%] flex flex-col justify-center border-2 border-green-400 items-center px-12 mt-10 text-white">
        <div class="heading font-bold text-2xl my-4 font-mono">
          <h1>Recommended Quizzes For You</h1>
        </div>
        <div
          class="topics border-2 border-white hover:border-green-500 w-[50%] p-10  text-green-700 font-sans font-bold">
          <h2 class="hover:text-white hover:underline cursor-pointer">C Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">C++ Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Java Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Python Programming Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Data Structures Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Algorithms Mock Tests</h2>
          <h2 class="hover:text-white hover:underline cursor-pointer">Algorithms Mock Tests</h2>
        </div>
        <div
          class="btn h-10 mb-10 w-52 mt-6 font-bold  border-2 border-white flex justify-center items-center text-white rounded-sm hover:border-green-500 hover:text-green-500 ">
          <router-link to="/quiz" exact>Attempt Quiz Now</router-link>
        </div>
      </div>
    </div> -->
    <!-- Quiz part middle end -->

    <!-- Table Part Started  -->

    <div class="tables">

      <div class="table1">
        <div class="table h-screen  w-full bg-[#131417] p-16">

          <div class="heading text-white flex justify-center items-center font-bold text-2xl my-4 font-mono -mt-10">
            <h1>RECENTLY ADDED QUIZZES </h1>
          </div>
          <div class="overflow-x-auto relative shadow-md sm:rounded-lg border-2 border-white">
            <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
              <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
                <tr>
                  <th scope="col" class="py-3 px-6">
                    Quiz ID
                  </th>
                  <th scope="col" class="py-3 px-6">
                    Quiz name
                  </th>
                  <th scope="col" class="py-3 px-6">
                    Category
                  </th>
                  <th scope="col" class="py-3 px-6">
                    No. of Questions
                  </th>
                  <th scope="col" class="py-3 px-6">
                    Difficulty Level
                  </th>
                  <th scope="col" class="py-3 px-6">
                    Attempted By
                  </th>
                  <th scope="col" class="py-3 px-6">
                    Action
                  </th>
                </tr>
              </thead>
              <tbody>
                <tr class="bg-[#131417] border-b   dark:border-gray-700">
                  <td class="py-4 px-6">
                    01
                  </td>
                  <td class="py-4 px-6">
                    Array and Array Operations
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <router-link to="/quiz">
                      <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                    </router-link>
                  </td>
                </tr>
                <tr class="bg-[#131417] first-line: border-b  dark:border-gray-700">
                  <td class="py-4 px-6">
                    02
                  </td>
                  <td class="py-4 px-6">
                    Stack Operations – 1
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    Easy
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    <router-link to="/quiz">
                      <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                    </router-link>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b   dark:border-gray-700">
                  <td class="py-4 px-6">
                    03
                  </td>
                  <td class="py-4 px-6">
                    Stack Operations – 2
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    100
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <router-link to="/quiz">
                      <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                    </router-link>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b  dark:border-gray-700">
                  <td class="py-4 px-6">
                    04
                  </td>
                  <td class="py-4 px-6">
                    Singly Linked Lists Operations
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <router-link to="/quiz">
                      <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                    </router-link>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b  dark:border-gray-700">
                  <td class="py-4 px-6">
                    05
                  </td>
                  <td class="py-4 px-6">
                    Doubly Linked List
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    Easy
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    <router-link to="/quiz">
                      <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                    </router-link>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b   dark:border-gray-700">
                  <td class="py-4 px-6">
                    06
                  </td>
                  <td class="py-4 px-6">
                    Circular Linked List
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    100
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <router-link to="/quiz">
                      <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                    </router-link>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b   dark:border-gray-700">
                  <td class="py-4 px-6">
                    07
                  </td>
                  <td class="py-4 px-6">
                    Queue using Linked List
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    100
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <router-link to="/quiz">
                      <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                    </router-link>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b   dark:border-gray-700">
                  <td class="py-4 px-6">
                    08
                  </td>
                  <td class="py-4 px-6">
                    Double Ended Queue (Dequeue)
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    100
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <router-link to="/quiz">
                      <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                    </router-link>
                  </td>
                </tr>
              </tbody>
            </table>


          </div>

          <!-- <div class="button flex justify-center space-x-8">
            <div
              class="btn h-10 w-40 mt-4 font-bold  border-2 border-white flex justify-center items-center text-white rounded-sm hover:border-green-500 hover:text-green-500 ">
              <router-link to="/addQuiz" exact>Add a new Quiz</router-link>
            </div>
            <div
              class="btn h-10 w-40 mt-4 font-bold  border-2 border-white flex justify-center items-center text-white rounded-sm hover:border-green-500 hover:text-green-500 ">
              <router-link to="/addQuiz" exact>Update Quiz</router-link>
            </div>

          </div> -->



        </div>
      </div>
      <div class="table2">
        <div class="table h-screen  w-full bg-[#131417] p-16">

          <div class="heading text-white flex justify-center items-center font-bold text-2xl my-4 font-mono -mt-10">
            <h1>TRENDING QUIZZES</h1>
          </div>
          <div class="overflow-x-auto relative shadow-md sm:rounded-lg border-2 border-white">
            <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
              <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
                <tr>
                  <th scope="col" class="py-3 px-6">
                    Quiz ID
                  </th>
                  <th scope="col" class="py-3 px-6">
                    Quiz name
                  </th>
                  <th scope="col" class="py-3 px-6">
                    Category
                  </th>
                  <th scope="col" class="py-3 px-6">
                    No. of Questions
                  </th>
                  <th scope="col" class="py-3 px-6">
                    Difficulty Level
                  </th>
                  <th scope="col" class="py-3 px-6">
                    Attempted By
                  </th>
                  <th scope="col" class="py-3 px-6">
                    Action
                  </th>
                </tr>
              </thead>
              <tbody>
                <tr class="bg-[#131417] border-b   dark:border-gray-700">
                  <td class="py-4 px-6">
                    01
                  </td>
                  <td class="py-4 px-6">
                    Array and Array Operations
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
                <tr class="bg-[#131417] first-line: border-b  dark:border-gray-700">
                  <td class="py-4 px-6">
                    02
                  </td>
                  <td class="py-4 px-6">
                    Stack Operations – 1
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    Easy
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b   dark:border-gray-700">
                  <td class="py-4 px-6">
                    03
                  </td>
                  <td class="py-4 px-6">
                    Stack Operations – 2
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    100
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b  dark:border-gray-700">
                  <td class="py-4 px-6">
                    04
                  </td>
                  <td class="py-4 px-6">
                    Singly Linked Lists Operations
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b  dark:border-gray-700">
                  <td class="py-4 px-6">
                    05
                  </td>
                  <td class="py-4 px-6">
                    Doubly Linked List
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    Easy
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b   dark:border-gray-700">
                  <td class="py-4 px-6">
                    06
                  </td>
                  <td class="py-4 px-6">
                    Circular Linked List
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    100
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b   dark:border-gray-700">
                  <td class="py-4 px-6">
                    07
                  </td>
                  <td class="py-4 px-6">
                    Queue using Linked List
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    100
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b   dark:border-gray-700">
                  <td class="py-4 px-6">
                    08
                  </td>
                  <td class="py-4 px-6">
                    Double Ended Queue (Dequeue)
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    100
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
              </tbody>
            </table>


          </div>

          <!-- <div class="button flex justify-center space-x-8">
            <div
              class="btn h-10 w-40 mt-4 font-bold  border-2 border-white flex justify-center items-center text-white rounded-sm hover:border-green-500 hover:text-green-500 ">
              <router-link to="/addQuiz" exact>Add a new Quiz</router-link>
            </div>
            <div
              class="btn h-10 w-40 mt-4 font-bold  border-2 border-white flex justify-center items-center text-white rounded-sm hover:border-green-500 hover:text-green-500 ">
              <router-link to="/addQuiz" exact>Update Quiz</router-link>
            </div>

          </div> -->



        </div>
      </div>
      <div class="table3">
        <div class="table h-screen  w-full bg-[#131417] p-16">

          <div class="heading text-white flex justify-center items-center font-bold text-2xl my-4 font-mono -mt-10">
            <h1>RECOMMENDED QUIZZES </h1>
          </div>
          <div class="overflow-x-auto relative shadow-md sm:rounded-lg border-2 border-white">
            <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
              <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
                <tr>
                  <th scope="col" class="py-3 px-6">
                    Quiz ID
                  </th>
                  <th scope="col" class="py-3 px-6">
                    Quiz name
                  </th>
                  <th scope="col" class="py-3 px-6">
                    Category
                  </th>
                  <th scope="col" class="py-3 px-6">
                    No. of Questions
                  </th>
                  <th scope="col" class="py-3 px-6">
                    Difficulty Level
                  </th>
                  <th scope="col" class="py-3 px-6">
                    Attempted By
                  </th>
                  <th scope="col" class="py-3 px-6">
                    Action
                  </th>
                </tr>
              </thead>
              <tbody>
                <tr class="bg-[#131417] border-b   dark:border-gray-700">
                  <td class="py-4 px-6">
                    01
                  </td>
                  <td class="py-4 px-6">
                    Array and Array Operations
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
                <tr class="bg-[#131417] first-line: border-b  dark:border-gray-700">
                  <td class="py-4 px-6">
                    02
                  </td>
                  <td class="py-4 px-6">
                    Stack Operations – 1
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    Easy
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b   dark:border-gray-700">
                  <td class="py-4 px-6">
                    03
                  </td>
                  <td class="py-4 px-6">
                    Stack Operations – 2
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    100
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b  dark:border-gray-700">
                  <td class="py-4 px-6">
                    04
                  </td>
                  <td class="py-4 px-6">
                    Singly Linked Lists Operations
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b  dark:border-gray-700">
                  <td class="py-4 px-6">
                    05
                  </td>
                  <td class="py-4 px-6">
                    Doubly Linked List
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    Easy
                  </td>
                  <td class="py-4 px-6">
                    10
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b   dark:border-gray-700">
                  <td class="py-4 px-6">
                    06
                  </td>
                  <td class="py-4 px-6">
                    Circular Linked List
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    100
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b   dark:border-gray-700">
                  <td class="py-4 px-6">
                    07
                  </td>
                  <td class="py-4 px-6">
                    Queue using Linked List
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    100
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
                <tr class="bg-[#131417] border-b   dark:border-gray-700">
                  <td class="py-4 px-6">
                    08
                  </td>
                  <td class="py-4 px-6">
                    Double Ended Queue (Dequeue)
                  </td>
                  <td class="py-4 px-6">
                    DSA
                  </td>
                  <td class="py-4 px-6">
                    100
                  </td>
                  <td class="py-4 px-6">
                    Medium
                  </td>
                  <td class="py-4 px-6">
                    20
                  </td>
                  <td class="py-4 px-6">
                    <a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Attemp Now</a>
                  </td>
                </tr>
              </tbody>
            </table>


          </div>

          <!-- <div class="button flex justify-center space-x-8">
            <div
              class="btn h-10 w-40 mt-4 font-bold  border-2 border-white flex justify-center items-center text-white rounded-sm hover:border-green-500 hover:text-green-500 ">
              <router-link to="/addQuiz" exact>Add a new Quiz</router-link>
            </div>
            <div
              class="btn h-10 w-40 mt-4 font-bold  border-2 border-white flex justify-center items-center text-white rounded-sm hover:border-green-500 hover:text-green-500 ">
              <router-link to="/addQuiz" exact>Update Quiz</router-link>
            </div>

          </div> -->



        </div>
      </div>



    </div>



    <!-- Table Part end  -->



  </div>
</template>
  
<script>
import Vue from 'vue';
import axios from 'axios';

import VueToast from 'vue-toast-notification';
import 'vue-toast-notification/dist/theme-sugar.css';
import setAuthHeader from '@/utils/setAuthHeader';

// import setAuthHeader from '../utils/setAuthHeader.js';
// import loginPage from './LogInPage.vue';

Vue.use(VueToast);
export default {

  name: 'HomePage.vue',
  data() {
    return {
      success: false,
      name: '',
      email: '',
      accessLevel: '',
      score: 0

    }
  },

  components: {
    // "loginPage" : loginPage

  },


  methods: {

    logout() {
      this.$router.push({ path: '/login', replace: true })
      Vue.$toast.open('You are successfully logged out');
      setAuthHeader(false);

    },

    leaderBoard() {
      this.$router.push({ path: '/leadboard', replace: true })
    },

    async profile() {

      try {
        const userInfo = await axios.get('http://localhost:8000/api/user/loggeduser');
        console.log(userInfo);
        // console.log(userInfo.data);
        // console.log(userInfo.data.name);
        // console.log(userInfo.data.email);
        this.name = userInfo.data.user.name;
        this.email = userInfo.data.user.email;
        this.accessLevel = userInfo.data.user.accessLevel;
        this.score = userInfo.data.user.score;
        console.log(this.name);
        console.log(this.email);
        console.log(this.accessLevel);

      } catch (error) {
        console.log(error);
      }

      this.success = !this.success;

    },




  }
}
</script>
  
<style scoped>

</style>