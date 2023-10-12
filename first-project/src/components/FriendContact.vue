<template>
	<li>
		<h2>{{ name }}</h2>
		<button @click="toggleDetails">{{ detailsVisible ? 'Hide' : 'Show' }} Details</button>
		<ul v-if="detailsVisible">
			<li><strong>Phone: </strong> {{ phoneNumber }}</li>
			<li><strong>Email: </strong> {{ email }}</li>
		</ul>
	</li>
</template>

<script>
export default {
	props: [
        'name',
        'phoneNumber',
        'email',
    ], 
	data() {
		return {
			detailsVisible: false,
			friend: {
				id: 'anna',
				name: 'Anna Wanna',
				phone: '012 345 678',
				email: 'email@email',
			},
		};
	},
	methods: {
		toggleDetails() {
			this.detailsVisible = !this.detailsVisible;
		},
	},
};
</script>
