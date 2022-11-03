<!-- eslint-disable vue/valid-template-root -->
<template>
  <li>
    <h2>{{ name }} {{ isFavourite ? "★" : "" }}</h2>
    <button @click="$emit('fav-person', name)">Favourite</button>
    <button @click="$emit('data-visible', name)">
      {{ show ? "Hide" : "Show" }} Details
    </button>
    <ul v-if="show">
      <li><strong>Phone:</strong> {{ phoneNumber }}</li>
      <li><strong>Email:</strong> {{ emailAdress }}</li>
      <button @click="$emit('delete-friend', name)">Delete</button>
    </ul>
  </li>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
    phoneNumber: {
      type: String,
      required: true,
    },
    emailAdress: {
      type: String,
      required: true,
    },
    isFavourite: {
      type: Boolean,
      required: false,
      default: false,
    },
    show: {
      type: Boolean,
      required: false,
      default: false,
    },
  },
  emits: ["data-visible", "fav-person", "delete-friend"],
};
</script>
