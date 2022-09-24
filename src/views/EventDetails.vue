<template>
  <div class="event-card">
    <h4>{{ event.title }}</h4>
    <p>{{event.description}}</p>
  </div>
</template>

<script>
import EventService from '@/services/EventService.js'
export default {
props: ['id'],
data() {
    return {
        event: null,
    }
},
    created() {
    EventService.getEvent(this.id)
      .then(response => {
        this.event = response.data
      })
      .catch(error => {
        console.log(error)
      })
  }
}
</script>

<style scoped>
.event-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}

.event-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}
</style>
