<template>
  <div class="row">
    <div class="col">
      <router-link
        class="event-link"
        :to="{ name: 'PatientDetail', params: { id: event.id } }"
      >
        <div class="event-card">
          <h4 id="id">ID: {{ event.id }}</h4>
          <h3>{{ event.name }} {{ event.surname }}</h3>
          <h4>{{ event.vaccinateStatus }}</h4>
        </div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "PatientCard",
  props: {
    event: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.col {
  float: left;
  width: 50%;
  padding: 10px;
  height: 150px;
}
.row:after {
  content: "";
  display: table;
  clear: both;
}
#id {
  color: rgb(252, 76, 76);
}

.event-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
}

.event-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}

.event-link {
  color: #2c3e50;
  text-decoration: none;
}
</style>
