<template>
	<main id="Home-page">
		<h1>Finance</h1>

		<div class="menu">
			<nav>
				<router-link to="/" class="button">
					<span class="text">Dashboard</span>
				</router-link>
				<router-link to="/" class="button">
					<span class="text">Today's History</span>
				</router-link>
				<router-link to="/" class="button">
					<span class="text">Invoice</span>
				</router-link>


			</nav>
		</div>
	</main>
</template>

<style lang="scss" scoped>
.Homepage{
	margin-left: 50px;
	margin-top: 30px;
}
	.menu{
	margin-left: 3rem;
		margin-top: 20px;
		margin-bottom: 20px;

		.button {
			align-items: center;
			margin-left: 18px;
			text-decoration: none;

			transition: 0.2s ease-in-out;
			padding: 0;

			
			.text {
				color: var(--dark);
				transition: 0.2s ease-in-out;
			}

			&:hover {
				
				text-transform: bold

		
			}

			&.router-link-exact-active {
				border-bottom: 5px solid var(--primary);

				.text {
					color: var(--primary);
				}
			}
		}
	}
	
	
</style>