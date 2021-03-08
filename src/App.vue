<template>
<div class="bg-my h-screen ">
    <div class=" bg-my w-full sticky flex flex-row items-center p-2 justify-between shadow-xs">
    <div class="ml-8 text-lg text-white">
     <span class="mt-8 -ml-3 "> <i class="material-icons">dehaze</i></span>
     <div class="-mt-8 items-center flex">
       <i class="material-icons ml-9 text-2xl -mt-1 fill text-head">smart_display</i>
     <h3 class="font-bold -mt-1 pl-1">YouTube<sup class="text-gray-400">NG</sup></h3>
      </div>
      
    </div>
    <div class="flex m-2 justify-center w-full">
    <input class="w-full md:w-1/3 h-9 flex cursor-pointer bg-black border border-gray-800 text-base  text-gray-500 font-bold p-4" placeholder="Search">  
             <button class="bg-urs w-14  border border-gray-800 flex items-center">
                <i class="material-icons text-white px-4 ">search</i>
            </button>
                
        <i class="material-icons text-white ml-2 mt-2">mic</i>
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
      <div class="w-72 bg-urs h-full  overflow-y-scroll">
        <div class="mx-2 mb-5 pt-4 focus:outline-none ">
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
          <button class=" -ml-8 w-full text-base font-normal text-white rounded">Show more</button>
           </span>
      </div>

       <div class="mx-2 mb-5 pt-4 border-gray-600  border-t border-light shadow-sm">
         <h1 class="text-gray-400 font-bold mx-4 my-2">SUBSCRIPTIONS</h1>
          <button v-for="sub in subs" :key="sub.id" @click="setID = sub" :class="`w-full text-base font-normal text-white rounded px-4 py-2 flex items-center justify-start hover:bg-gray-600 ${setID === sub.id ? 'bg-light text-white' : 'text-lightest'}`">
          <img :src="`${sub.src}`" class="w-6 h-6 rounded-full">
           <p class="pl-6 text-base font-normal">{{sub.name}}</p>
          </button>
      </div>

      <div class="mx-2 mb-5 pt-4  border-gray-600  border-t border-light shadow-sm ">
         <h1 class="text-gray-400 font-bold mx-4 my-2">MORE FROM YOUTUBE</h1>
          <button v-for="premium in premiums" :key="premium.id" @click="setID = premium" :class="`w-full text-base font-normal text-white rounded px-3 py-2 flex items-center justify-start hover:bg-gray-600 ${setID === premium.id ? 'bg-light text-white' : 'text-lightest'}`">
          <i class="material-icons"> {{premium.icon}}</i>
           <p class="pl-8">{{premium.name}}</p>
          </button>
          <span class=" flex items-center justify-start ml-2 mt-4">
            <i class="material-icons text-white mt-2">keyboard_arrow_down</i>
          <button class=" -ml-8 w-full text-base font-normal text-white rounded">Show more</button>
           </span>
      </div>
</div>

<!------- Recnt category viewed--->
    <div class="w-full h-full relative bg-my text-white overflow-y-scroll">
      <div class='justify-items-start  border-gray-800  border-t border-b border-light'>
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

      <div class="container my-12 mx-auto px-4 md:px-12">
    <div class="flex flex-wrap -mx-1 lg:-mx-4">

        <!-- Column -->
        <div v-for="video in videos" :key="video.artist" class="my-1 px-1 w-full md:w-1/2 lg:my-4 lg:px-4 lg:w-1/4 ">

            <!-- div -->
            <div class="overflow-hidden rounded-lg shadow-lg hover:bg-gray-900">

                <a href="#">
                    <img :src="`${video.src}`" alt="Placeholder" class="block h-auto w-full">
                </a>

            <div>
                <div class="flex flex-col  leading-none p-2 md:p-4">
                    <a class="flex items-start no-underline hover:no-underline text-white" href="#">
                        <img :src="`${video.artist_src}`" class="block rounded-full w-auto h-">
                        <h1 class="ml-4 text-sm hover:no-underline flex justify-items-start ">
                            {{video.title}}
                        </h1>
                    </a>
                    <div class="items-center justify-start pl-12">
                    <h4 class="pt-2 text-sm  text-gray-400">{{video.artist}}</h4>
                    <div>
                    <span class="text-sm text-gray-400">{{video.views}}</span>
                    <span class=" ml-4 text-sm text-gray-400">{{video.time}}</span>
                    </div>
                    </div>
                </div>
            </div>
            </div>
            <!-- END div -->
        </div>
        </div>
        </div>
      <!--- begiining of card --->
      <div class="w-full flex flex-wrap">
         <div class="p-2 w-48">
           <div class="w-full bg-light h-auto p-5 rounded">
             <img src="" class="h-auto w-full mb-2">
             <div>

             </div>

           </div>
         </div>
      </div>
        <!----- end of card--->
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
    videos: [
        {src: 'https://picsum.photos/600/400/?random=1', title: 'AFROBEAT MIX 2021 | DAVIDO, BURNA BOY', artist: 'DAVIDO', artist_src: 'https://picsum.photos/32/32/?random=1', views: '6k views', time: '4 month ago'},
        {src: 'https://picsum.photos/600/400/?random=2', title: 'HIGH LEVEL SKILLS FOR PROGRAMMERS', artist: '2FACE', artist_src: 'https://picsum.photos/32/32/?random=2', views: '14k views', time: '1 day ago'},
        {src: 'https://picsum.photos/600/400/?random=3', title: 'WORKING WITH APIs', artist: 'WIZKID', artist_src: 'https://picsum.photos/32/32/?random=3', views: '120k views', time: '7 hours ago'},
        {src: 'https://picsum.photos/600/400/?random=4', title: 'JAVASCRIPT PROs AND CONs', artist: 'TIWA', artist_src: 'https://picsum.photos/32/32/?random=4', views: '1m views', time: '6 month ago'},
        {src: 'https://picsum.photos/600/400/?random=5', title: 'AFROBEAT MIX 2021 | DAVIDO, BURNA BOY', artist: 'DAVIDO', artist_src: 'https://picsum.photos/32/32/?random=5', views: '6k views', time: '4 month ago'},
        {src: 'https://picsum.photos/600/400/?random=8', title: 'HIGH LEVEL SKILLS FOR PROGRAMMERS', artist: '2FACE', artist_src: 'https://picsum.photos/32/32/?random=6', views: '14k views', time: '1 day ago'},
        {src: 'https://picsum.photos/600/400/?random=6', title: 'WORKING WITH APIs', artist: 'WIZKID', artist_src: 'https://picsum.photos/32/32/?random=7', views: '120k views', time: '7 hours ago'},
        {src: 'https://picsum.photos/600/400/?random=7', title: 'JAVASCRIPT PROs AND CONs', artist: 'TIWA', artist_src: 'https://picsum.photos/32/32/?random=8', views: '1m views', time: '6 month ago'},
        
      ],
      sections: [
        {id: 'library', name: 'Library', icon: 'video_library'},
        {id: 'history', name: 'History', icon: 'history'},
        {id: 'your_videos', name: 'Your videos', icon: 'watch_later'},
        {id: 'watch_later', name: 'Watch later', icon: 'smart_display'},
        
      ],
       premiums: [
        {id: 'YouTube Premium', name: 'Premium', icon: 'smart_display'},
        {id: 'Gaming', name: 'Gaming', icon: 'sports_esports'},
        {id: 'Live', name: 'Live', icon: 'sensors'},
        {id: 'Sports', name: 'Sports', icon: 'emoji_events'},
        
      ],

      subs: [
        {id: 'vue_js', name: 'Vue Js', src: 'vue.jpg'},
        {id: 'codeng', name: 'Code Step', src: 'code.jpg'},
        {id: 'edureka', name: 'Edureka', src: 'edureka.jpg'},
        {id: 'freecodecamp', name: 'Freecodecamp', src: 'freecode.jpg'},
        {id: 'hng', name: 'HNG', src: 'hng.jpg'},
        {id: 'netninja', name: 'Netninja', src: 'net.jpg'},
        {id: 'tailwindcss', name: 'Tailwindcss', src: 'tailwind.jpg'},
        {id: 'traversy', name: 'Traversy', src: 'traversy.jpg'},
        
      ],
    setID: 'home'
    }
  }
}

</script>

<style src="./assets/index.css"/> 
 

