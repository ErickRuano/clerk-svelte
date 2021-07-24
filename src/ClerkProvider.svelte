<script>

import {onMount} from 'svelte'
import { clerk } from './clerk.js'
export let frontendApi = "";
export let navigate = ()=>{  }



	onMount(()=>{
	
		const script = document.createElement('script');
		script.setAttribute('data-clerk-frontend-api', frontendApi);
		script.async = true;
		script.src = `https://${api}/npm/@clerk/clerk-js@1/dist/clerk.browser.js`
		script.addEventListener('load', function(){
            window.Clerk.load({ navigate }).then((e)=>{
                clerk.update(() => window.Clerk)
            })
		});
		document.body.appendChild(script);

});

</script>

<div style="display:none;">Clerk loader</div>