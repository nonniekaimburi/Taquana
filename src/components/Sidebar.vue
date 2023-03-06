<template>
	<aside :class="`${is_expanded ? 'is-expanded' : ''}`">
		<div class="logo">
			<h2>TQ-HMS</h2> 
		</div>

		<!-- <div class="menu-toggle-wrap">
			<button class="menu-toggle" @click="ToggleMenu">
				<span class="material-icons">keyboard_double_arrow_right</span>
			</button>
		</div> -->

		
		<div class="menu">
			<router-link to="/" class="button">
				<!-- <span class="material-icons">dashboard</span> -->
				<span class="text">Dashboard</span>
			</router-link>
			<router-link to="/about" class="button">
				<!-- <span class="material-icons">description</span> -->
				<span class="text">Finance</span>
			</router-link>
			<router-link to="/labs" class="button">
				<!-- <span class="material-icons">group</span> -->
				<span class="text">Labs</span>
			</router-link>
			
		</div>

		<div class="flex"></div>
		
		<!-- <div class="menu">
			<router-link to="/settings" class="button">
				<span class="material-icons">settings</span>
				<span class="text">Settings</span>
			</router-link>
		</div> -->
	</aside>
</template>

<script setup>
import { ref } from 'vue'
import logoURL from '../assets/logo.png'

const is_expanded = ref(localStorage.getItem("is_expanded") === "true")

const ToggleMenu = () => {
	is_expanded.value = !is_expanded.value
	localStorage.setItem("is_expanded", is_expanded.value)
}
</script>

<style lang="scss" scoped>
aside {
	display: fixed;
	flex-direction: column;

	background-color: var(--light);
	color: var(--dark);

	width: calc(2rem + 32px);
	overflow: hidden;
	min-height: 100vh;
	padding: 1rem;

	transition: 0.2s ease-in-out;

	.flex {
		flex: 1 1 0%;
	}

	.logo {
		margin-bottom: 3rem;

		img {
			width: 2rem;
		}
	}

	.menu-toggle-wrap {
		display: flex;
		justify-content: flex-end;
		margin-bottom: 1rem;

		position: relative;
		top: 0;
		transition: 0.2s ease-in-out;

		.menu-toggle {
			transition: 0.2s ease-in-out;
			.material-icons {
				font-size: 2rem;
				color: var(--dark);
				transition: 0.2s ease-out;
			}
			
			&:hover {
				.material-icons {
					color: var(--primary);
					transform: translateX(0.5rem);
				}
			}
		}
	}

	h3, .button .text {
		opacity: 0;
		transition: opacity 0.3s ease-in-out;
	}

	h3 {
		color: var(--dark);
		font-size: 0.875rem;
		margin-bottom: 0.5rem;
		text-transform: uppercase;
	}

	.menu {
		margin: 0 -1rem;
		

		.button {
			display: flex;
			align-items: center;
			text-decoration: none;

			transition: 0.2s ease-in-out;
			padding: 0.5rem 1rem;

			// .material-icons {
			// 	font-size: 2rem;
			// 	color: var(--light);
			// 	transition: 0.2s ease-in-out;
			// }
			.text {
				color: var(--dark);
				transition: 0.2s ease-in-out;
			}

			&:hover {
				background-color: var(--light);

				
			}

			&.router-link-exact-active {
				background-color: var(--light);
				border-left: 5px solid var(--primary);

				.material-icons, .text {
					color: var(--primary);
				}
			}
		}
	}

	// .footer {
	// 	opacity: 0;
	// 	transition: opacity 0.3s ease-in-out;

	// 	p {
	// 		font-size: 0.875rem;
	// 		color: var(--grey);
	// 	}
	// }

	&.is-expanded {
		width: var(--sidebar-width);

		.menu-toggle-wrap {
			top: -3rem;
			
			.menu-toggle {
				transform: rotate(-180deg);
			}
		}

		h3, .button .text {
			opacity: 1;
		}

		.button {
			.material-icons {
				margin-right: 1rem;
			}
		}

		.footer {
			opacity: 0;
		}
	}

	@media (max-width: 1024px) {
		position: absolute;
		z-index: 99;
	}
}
</style>