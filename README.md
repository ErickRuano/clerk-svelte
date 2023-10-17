**Warning** This repo hasn't been updated in a while.  PRs are welcomed.  Otherwise I hope to push some updates soon :)

# clerk-svelte

An unofficial implementation of Clerk components inspired by the official react implementation

Because of how the Clerk.js library is loaded a REPL example is not possible.

# Installation

```bash
npm i -D @erickruano/clerk-svelte
```

# Usage

```html
<script>
import { 
    /* Stores */
    Clerk,  // Svelte writable store that exposes Clerk for you instead of using window
    /* Components */
    ClerkProvider,  // This component must exist once in your App.svelte or equivalent.  This is the one that loads Clerk.js
    SignIn, // Place wherever you need. It will mount the SignIn flow UI
    SignUp, // Place wherever you need. It will mount the SignUp flow UI
    UserButton, // Place wherever you need. It will mount the User Button UI
    UserProfile, // Place wherever you need.  It will mount the User Profile UI
    SignedIn,  // Whatever you wrap inside this component will show only if a session exists in Clerk
    SignedOut  // Whatever you wrap inside this component will show only if no session exists in Clerk
} from '@erickruano/clerk-svelte'
</script>

<!-- src/App.js -->

<ClerkProvider frontendApi="your-api"/>

<!-- Anywhere in your project -->

Hello, {$Clerk.user.fullName}!

<SignIn/>

<SignUp/>

<UserButton/>

<UserProfile/>

<SignedIn>
    <!-- User is signed in, show dashboard  -->
</SignedIn>

<SignedOut>
    <!-- User is signed out, show sign-in flow  -->
    <SignIn />
</SignedOut>

```

# To-do

- Test components
- Add useClerk and useUser methods to mimic official React implementation
- Create demo site
- Edge case: Update Clerk store when session changes and custom navigate handler was provided
