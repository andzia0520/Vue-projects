<template>
	<section>
		<h2>My friends</h2>
		<ul>
			<friend-contact></friend-contact>
			<friend-contact></friend-contact>
		</ul>
	</section>
</template>

<script>
import FriendContact from './components/FriendContact.vue';
export default {
  components: { FriendContact },
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
