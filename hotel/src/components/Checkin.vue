<template lang="html">
  <div class="sighting">
    <p>{{ checkin.name }} on {{ checkin.date |formatDate}}</p>
    <p>email address: {{ checkin.email }}</p>
    <p>Checked In: {{ checkin.isCheckedIn }}</p>

    <button v-on:click="handleDelete(checkin._id)">Delete</button>
  </div>
</template>

<script>

import { eventBus } from '../main';

export default {
  name: "checkin",

  props: ['checkin'],

	filters: {
    formatDate(value) {
      return new Date(value).toLocaleString().substring(0, 10);
    }
  }
}
</script>

<style lang="css" scoped>
.sighting {
	width: 30%;
	background: rgba(255, 255, 255, 0.7);
	margin-bottom: 20px;
	padding: 25px;
}

button {
	color: #fff;
	border: none;
	font-size: 18px;
	padding: 10px;
	margin-top: 10px;
	background: #F55536;
}

h2 {
	padding: 0;
	margin: 0;
} 
</style>
