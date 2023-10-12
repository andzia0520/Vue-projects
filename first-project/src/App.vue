<template>
	<section>
		<h2>My friends</h2>
		<ul>
			<li></li>
		</ul>
	</section>
</template>

<script>
export default {
	data() {
		return {
			friends: [
				{
					id: 'anna',
					name: 'Anna Wanna',
					phone: '012 345 678',
					email: 'email@email',
				},
				{
					id: 'julia',
					name: 'Julia Bulia',
					phone: '111 222 333',
					email: 'julia@email',
				},
			],
		};
	},
};
</script>
