<template>
	<section>
		<header><h1>My friends</h1></header>
		<new-friend @add-contact="addContact" ></new-friend>
		<ul>
			<friend-contact
				v-for="friend in friends"
				:key="friend.id"
				:id="friend.id"
				:name="friend.name"
				:phone-number="friend.phone"
				:email="friend.email"
				:is-favorite="friend.isFavorite"
				@toggle-favorite="toggleFavoriteStatus"
				@delete-contact="deleteContact"
			></friend-contact>
		</ul>
	</section>
</template>

<script>
import FriendContact from './components/FriendContact.vue';
import NewFriend from './components/NewFriend.vue';
export default {
	components: { FriendContact, NewFriend },
	data() {
		return {
			friends: [
				{
					id: 'anna',
					name: 'Anna Wanna',
					phone: '012 345 678',
					email: 'email@email',
					isFavorite: true,
				},
				{
					id: 'julia',
					name: 'Julia Bulia',
					phone: '111 222 333',
					email: 'julia@email',
					isFavorite: false,
				},
			],
		};
	},
	methods: {
		toggleFavoriteStatus(friendId) {
			const indentifindFriend = this.friends.find(friend => friend.id === friendId);
			console.log(indentifindFriend);
			indentifindFriend.isFavorite = !indentifindFriend.isFavorite;
			console.log(indentifindFriend.isFavorite);
		},

		addContact(name, phone, email) {
			const newFriendContact = {
				id: new Date().toISOString,
				name: name,
				phone: phone,
				email: email,
				isFavorite: false,
			};
			this.friends.push(newFriendContact);
		},
		deleteContact(friendId) {
			// this.friends = this.friends.filter(friend => friend.id !== friendId)

			console.log(this.friends);
		
		const searchedFriend = this.friends.map( f => f.id).indexOf(friendId)
			this.friends.splice(searchedFriend, 1);
		},
	},
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Jost&display=swap');
* {
	box-sizing: border-box;
}

html {
	font-family: 'Jost', sans-serif;
}

body {
	margin: 0;
}

header {
	box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
	margin: 3rem auto;
	border-radius: 10px;
	padding: 1rem;
	background-color: #58004d;
	color: white;
	text-align: center;
	width: 90%;
	max-width: 40rem;
}

#app form {
	display: block;
	box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
	margin: 0 auto;
	border-radius: 10px;
	padding: 1rem;
	text-align: center;
	width: 90%;
	max-width: 40rem;
}

#app form label {
	display: block;
	text-align: center;
	margin-bottom: 10px;
	margin-top: 5px;
	font-weight: bold;
}

#app form input,
select {
	display: block;
	margin: 0 auto;
	margin-bottom: 10px;
	margin-top: 5px;
	border-radius: 5px;
}

#app ul {
	margin: 0;
	padding: 0;
	list-style: none;
}

#app li {
	box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
	margin: 1rem auto;
	border-radius: 10px;
	padding: 1rem;
	text-align: center;
	width: 90%;
	max-width: 40rem;
}

#app h2 {
	font-size: 2rem;
	border-bottom: 4px solid #ccc;
	color: #58004d;
	margin: 0 0 1rem 0;
}

#app button {
	margin-right: 10px;
	font: inherit;
	cursor: pointer;
	border: 1px solid #ff0077;
	border-radius: 4px;
	background-color: #ff0077;
	color: white;
	padding: 0.05rem 1rem;
	box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}

#app button:hover,
#app button:active {
	background-color: #ec3169;
	border-color: #ec3169;
	box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}
</style>
