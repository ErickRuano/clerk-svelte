<script>

import { onDestroy, onMount } from 'svelte'
import { clerk } from './clerk.js'

    let userButtonElement

    let unsubscribe = ()=>{};
    
    onMount(()=>{

        unsubscribe = clerk.subscribe(Clerk => {
            if(Clerk){
                Clerk.mountUserButton(userButtonElement)
            }
        });
    })
 
    onDestroy(unsubscribe)

</script>

<div bind:this={userButtonElement}></div>