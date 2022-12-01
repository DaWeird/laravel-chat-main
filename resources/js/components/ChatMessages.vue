// resources/assets/js/components/ChatMessages.vue

<template>
  <ul>
    <li class="left clearfix" v-for="message in messages" :key="message.id">
      <div class="clearfix">
        <div class="header">
          <strong>
            {{ message.user.name }}
          </strong>
    <span>{{ new Date(message.created_at).toLocaleString() }}</span>

        </div>
        <p>
          {{ message.message }}
        </p>
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  props: ["messages"],
  computed: {
    date() {
      const created_at = getStatusDate(); // returns string 
      return dayjs(date, 'YYYY-MM-DD HH:mm')
    }
  }
};
</script>