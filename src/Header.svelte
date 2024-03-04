<script>
  import { username, user } from './user';

  function signout() {
    user.leave();
    username.set('');
  }
</script>

<header>
<h1>Quintus</h1>
  {#if $username}
    <div class="user-bio">
      
      <span>Welcome, <strong>{$username}</strong></span>
      <img src={`https://api.dicebear.com/7.x/initials/svg?seed=${$username}`} alt="avatar" /> 
    </div>

    <button class="signout-button" on:click={signout}>Sign Out</button>

    {:else}

      <h3>Decentralised Chat</h3>
  {/if}
</header>