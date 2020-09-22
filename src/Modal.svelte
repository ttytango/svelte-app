<script>
    import { createEventDispatcher, onDestroy } from 'svelte';

	const dispatch = createEventDispatcher();
	const close = () => dispatch('close');

	let modal;

	const handle_keydown = e => {
		if (e.key === 'Escape') {
			close();
			return;
		}

		if (e.key === 'Tab') {
			// trap focus
			const nodes = modal.querySelectorAll('*');
			const tabbable = Array.from(nodes).filter(n => n.tabIndex >= 0);

			let index = tabbable.indexOf(document.activeElement);
			if (index === -1 && e.shiftKey) index = 0;

			index += tabbable.length + (e.shiftKey ? -1 : 1);
			index %= tabbable.length;

			tabbable[index].focus();
			e.preventDefault();
		}
	};

	const previously_focused = typeof document !== 'undefined' && document.activeElement;

	if (previously_focused) {
		onDestroy(() => {
			previously_focused.focus();
		});
    }
    
    function openPopUp () {
		alert("Hello There " + myModalInput.value + "!");
		close();
		return;
    }
</script>


<svelte:window on:keydown={handle_keydown}/>


<div class="modal-background" on:click={close}></div>

<div class="modal" role="dialog" aria-modal="true" bind:this={modal}>
	<slot name="header"></slot>
	<slot></slot>


	<!-- svelte-ignore a11y-autofocus -->
	<button autofocus on:click={close}>close modal</button>
	<button on:click={openPopUp}>Open pop up</button>
</div>

<style>
	.modal-background {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: rgba(0,0,0,0.8);
	}

	.modal {
		position: absolute;
		z-index: 10;
		left: 50%;
		top: 50%;
		width: calc(100vw - 4em);
		max-width: 32em;
		max-height: calc(100vh - 4em);
		overflow: auto;
		transform: translate(-50%,-50%);
		padding: 1em;
		border-radius: 0.2em;
		background: rgba(255, 84, 17, 0.767);
	}

	button {
		display: inline-block;
		font-size: 1.6rem;
		padding: 0.5rem 0.5rem;
		border-radius: 4px;
		overflow: hidden;
	}
</style>