<script>
    let username = '';
    let password = '';
    
    function handleLogin() {
      // Handle login logic here
    }
  </script>
  
  <div class="card p-4 mx-auto w-fit relative top-[50%] translate-y-[-50%]">
    <form on:submit|preventDefault={handleLogin}
        class='grid gap-4'>
      <div class="">
        <label for="username" class="label">Username</label>
        <input id="username" bind:value={username} class="input" type="text" placeholder="Enter your username" required />
      </div>
      <div class="">
        <label for="password" class="label">Password</label>
        <input id="password" bind:value={password} class="input" type="password" placeholder="Enter your password" required />
      </div>
      <button type="submit" class="btn variant-filled">Sign In</button>
    </form>
  </div>