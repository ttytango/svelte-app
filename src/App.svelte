<script>
	// export let name;
	import Topnav from './Topnav.svelte';
	import Login from './Login.svelte';
	import Product from './Product.svelte';
	import Modal from './Modal.svelte';
	import Footer from './Footer.svelte';
	let showModal = false;
	let name = 'robots';
	// let src = 'images/undraw.png';

</script>


<main>
<Topnav />
	<h1>Hello {name}!</h1>

	<Login />
	<button class="btn btn-card btn-modal" on:click="{() => showModal = true}">
	Show Modal
	</button>
	<!-- <img {src} alt="some image" /> -->
	<Product />
	


{#if showModal}
	<Modal on:close="{() => showModal = false}">
		<h2 slot="header">
			<input type="text" id="myModalInput" placeholder="Enter a name" value="" />
		</h2>
	</Modal>
{/if}

<Footer />

</main>

<style>
img {
	margin-top: 5px;
	background: rgb(100,100,10);
	opacity: 0.5;
    /* animation-fill-mode: backwards; */
}

.btn-modal {
	font-size: 1.6rem;
	margin-bottom: 1rem;
}

#myModalInput {
	padding: 1rem 0.5rem;
	margin-bottom: 1rem;
	font-size: 1.6rem;
}



</style>
	<!-- /* p {
		padding: 1em;
		margin: 0 0 1em 0;
		background-color: #eee;
	} */
	/* :hover {
		box-shadow: 2px 4px 20px black;
		background-color: pink;
	} */

	/* .active {
		background-color: #ff3e00;
		color: white;
	}



@media (min-width: 640px) {
	main {
		max-width: none;
	}
}

</style>
 -->


