<script>
  import { onDestroy, onMount } from 'svelte'
  import { clerk } from './clerk.js'
  
      let userProfileElement, unsubscribe
      
      onMount(()=>{
          unsubscribe = clerk.subscribe(Clerk => {
              if(Clerk){
                  Clerk.mountUserProfile(userProfileElement)
              }
          });
      })
   
      onDestroy(unsubscribe)
  
  </script>
  
  <div bind:this={userProfileElement}></div>