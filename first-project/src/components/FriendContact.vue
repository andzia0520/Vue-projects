<template>
	<li>
		<h2>{{ name }} {{ isFavorite ? '(favorite)' : '' }}</h2>
		<button @click="toggleFavorite">Toggle favorite</button>
		<button @click="toggleDetails">{{ detailsVisible ? 'Hide' : 'Show' }} Details</button>
		<button @click="deleteData">Delete </button>
		<ul v-if="detailsVisible">
			<li><strong>Phone: </strong> {{ phoneNumber }}</li>
			<li><strong>Email: </strong> {{ email }}</li>
		</ul>
	</li>
	
</template>

<script>
export default {
	props: {
		id: {
			type: String,
			required: true,
		},
		name: {
			type: String,
			required: true,
		},
		phoneNumber: {
			type: String,
			required: true,
		},
		email: {
			type: String,
			required: true,
		},
		isFavorite: {
			type: Boolean,
			required: false,
			default: false,
		},
	},
	emits: ['toggle-favorite', 'delete-contact'],

	// emits: {
	// 	'toggle-favorite': function (id) {
	// 		if (id) {
	// 			return true;
	// 		} else {
	// 			return false;
	// 		}
	// 	},
	// },
	
	data() {
		return {
			detailsVisible: false,
		};
	},
	methods: {
		toggleDetails() {
			this.detailsVisible = !this.detailsVisible;
		},

		toggleFavorite() {
			this.$emit('toggle-favorite', this.id);
		},

		deleteData() {
			this.$emit('delete-contact', this.id);
		},
	},
};
</script>
