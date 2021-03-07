<template>
<div class="bg-my h-screen ">
    <div class=" bg-my w-full sticky flex flex-row items-center p-2 justify-between shadow-xs">
    <div class="ml-8 text-lg text-white ">
     <span class="mt-8 -ml-3"> <i class="material-icons">dehaze</i></span>
     <div class="-mt-8">
      <img src="./assets/kk.jpg" class="h-8 pl-8">
      </div>
    </div>
    <div class="flex m-2 justify-center w-full">
    <input class="w-full md:w-1/3 h-9 flex cursor-pointer bg-black border border-gray-700 text-base  text-gray-500 font-bold p-4" placeholder="Search">  
             <button class="bg-urs w-14  border border-gray-700 flex items-center">
                <i class="material-icons text-white px-4 ">search</i>
            </button>
                
        <i class="material-icons text-white ml-4 mt-2">mic</i>
        </div>
        <div class="flex items-center gap-6 mr-8 md:flex">
            <a href="https://github.com/Charlie85270/tail-kit" class="p-1 rounded-full text-white focus:outline-none hover:text-gray-200 focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white">
               <span class="mt-8"> <i class="material-icons text-white h-8">video_call</i></span>
                
            </a>
            <a href="#" class="">
               <i class="material-icons text-white h-8">apps</i>
            </a>
             <a href="#" class="">
               <i class="material-icons text-white">notification_add</i>
            </a>
             <a href="#" class="">
              <i class="material-icons text-white h-8">account_circle</i>
            </a>
        </div>
    </div>
    

    
    <div class="flex h-full">
    
      <div class="w-72 bg-urs h-full">
        <div class="mx-2 mb-5 pt-4">
          <button v-for="page in pages" :key="page.id" @click="setID = page" :class="`w-full text-base font-normal text-white rounded px-4 py-2 flex items-center justify-start hover:bg-gray-600 ${setID === page.id ? 'bg-light text-white' : 'text-lightest'}`">
          <i class="material-icons"> {{page.icon}}</i>
           <p class="pl-8">{{page.name}}</p>
          </button>
          </div>
     
        <div class="mx-2 mb-5 pt-4  border-gray-600  border-t border-light shadow-sm ">
          <button v-for="section in sections" :key="section.id" @click="setID = section" :class="`w-full text-base font-normal text-white rounded px-3 py-2 flex items-center justify-start hover:bg-gray-600 ${setID === section.id ? 'bg-light text-white' : 'text-lightest'}`">
          <i class="material-icons"> {{section.icon}}</i>
           <p class="pl-8">{{section.name}}</p>
          </button>
          <span class=" flex items-center justify-start ml-2 mt-4">
            <i class="material-icons text-white mt-2">keyboard_arrow_down</i>
          <button class=" -ml-8 w-full text-base font-normal text-white rounded">Show more

            
          </button>
          </span>
      </div>
</div>

<!------- Recnt category viewed--->
    <div class="w-full h-full relative bg-my text-white overflow-y-scroll">
      <div class='justify-items-start  border-light border-t  border-b py-1'>
        <ul class="flex flex-row gap-4 p-2">
          <li class="rounded-full px-3 py-1.5 text-sm bg-white ml-8 text-my">
            All
          </li>
           <li class="rounded-full px-4 py-1.5 text-sm font-semibold bg-urs">
          Nollywood 
          </li>
           <li class="rounded-full px-4 py-1.5 text-sm font-semibold bg-urs">
          Cryptocurrency
          </li>
           <li class="rounded-full px-4 py-1.5 text-sm font-semibold bg-urs">
          Contemporary Worship Music
          </li>
          </ul>
      </div>
      <div class="px-6 py-3">
          <h1 class="text-white bg-red-500">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Neque, vel culpa! Earum quidem a enim distinctio id reiciendis temporibus eligendi aliquam obcaecati perspiciatis quia, tempore, cupiditate delectus doloribus dolor. Dolorum.</h1>
      </div>
    </div>
  </div>
    
  </div>
  
</template>

<script>

export default {
  name: 'App',
  components: {
    name: 'MaterialIcons'
    },
  data: function() {
    return {
      pages: [ 
      {id: 'home', name: 'Home', icon: 'home'},
      {id: 'trending', name: 'Trending', icon: 'whatshot'},
      {id: 'subscription', name: 'Subscription', icon: 'subscriptions'}
    ],
      sections: [
        {id: 'library', name: 'Library', icon: 'video_library'},
        {id: 'history', name: 'History', icon: 'history'},
        {id: 'your_videos', name: 'Your videos', icon: 'watch_later'},
        {id: 'watch_later', name: 'Watch later', icon: 'smart_display'},
        
      ],
    setID: 'home'
    }
  }
}

</script>

<style src="./assets/index.css"/> 
 

