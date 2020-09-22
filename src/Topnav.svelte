<script>
	let user = { loggedIn: false };

	function toggle() {
		user.loggedIn = !user.loggedIn;
    }

</script>



<nav class="main-nav">
    <ul class="main-nav__links">
    <li>
    <a href="#">Home</a>
    </li>    
    <li>
    <a href="#">Blog</a>
    </li>    
    <li>
    <a href="#">Contact</a>
    </li>    
    <li>
    <a href="#">About Us</a>
    </li>
    <li>{#if user.loggedIn}
	<button on:click={toggle}>
		Log out
	</button>
{/if}

{#if !user.loggedIn}
	<button on:click={toggle}>
		Log in
	</button>
{/if}</li>
    </ul>
</nav>