<script setup>
import { defineProps } from 'vue';
import ProfileImage from './ProfileImage.vue';
import User from './User.vue';
import Timestamp from './Timestamp.vue';
import Message from './Message.vue';
import Actions from './Actions.vue';

const props = defineProps({
  tweet: Object
})

const { timestamp, message, user } = props.tweet;
const { image } = user;
</script>

<template>
  <div class="tweet">
    <ProfileImage :image="image" />
    <div class="body">
      <div class="top">
        <User :user=user />
        <Timestamp :timestamp=timestamp />
      </div>
      <Message :message=message />
      <Actions />
    </div>
    <i class="fas fa-ellipsis-h"></i>
  </div>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
