<template>
  <router-link
    class="event-link"
    :to="{ name: 'event-show', params: { id: '1' } }"
  >
    <div class="event-card -shadow">
      <span class="eyebrow">@{{ event.time }} on {{ event.date }}</span>
      <h4 class="title">{{ event.title }}</h4>
      <BaseIcon name="users" />
      <span>{{ event.attendees.length }} attending</span>
    </div>
  </router-link>
</template>

<script>
export default {
  data() {
    return {
      event: {
        id: 1,
        title: "Park Cleanup +++",
        date: "Tues Dec 1, 2020",
        time: "4:00",
        attendees: [
          { id: "abc123", name: "Otho Otho" },
          { id: "dav123", name: "Darth Vader" },
        ],
      },
    };
  },
};
</script>

<style scoped>
.event-card {
  padding: 20px;
  margin-bottom: 24px;
  transition: all 0.2s linear;
  cursor: pointer;
}
.event-card:hover {
  transform: scale(1.2);
  box-shadow: 0 3px 12px 0 rgb(255, 251, 1), 0 1px 15px 0 rgba(255, 0, 0, 0.938);
}
.event-card > .title {
  margin: 0;
}
.event-link {
  color: black;
  text-decoration: none;
  font-weight: 100;
}
</style>
