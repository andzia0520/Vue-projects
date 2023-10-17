<template>
	<form @submit.prevent="submitData">
		<h2>Add new friend</h2>
		<div><label for="name">Name</label> <input type="text" id="name" v-model="enteredName" /></div>
		<div>
			<label for="phone">Phone number</label>
			<input type="tel" id="phone" v-model="enteredPhone" />
		</div>
		<div><label for="email">Email</label> <input type="email" id="email" enteredEmail /></div>

		<button>Add contact</button>
	</form>
</template>

<script>
export default {
	emits: ['add-contact'],
	data() {
		return {
			enteredName: '',
			enteredPhone: '',
			enteredEmail: '',
		};
	},
	methods: {
		submitData() {
			this.$emit('add-contact', this.enteredName, this.enteredPhone, this.enteredEmail);
		},
	},
};
</script>
