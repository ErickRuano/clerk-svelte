<script>
  import { onDestroy, onMount } from 'svelte'
  import { clerk } from './clerk.js'
  
      let signUpElement
  
      let unsubscribe = ()=>{};
      
      onMount(()=>{
  
          unsubscribe = clerk.subscribe(Clerk => {
              if(Clerk){
                  Clerk.mountSignUp(signUpElement)
              }
          });
      })
   
      onDestroy(unsubscribe)
  
  </script>
  
  <div bind:this={signUpElement}></div>