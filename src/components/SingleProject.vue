<template>
  <div class="project">
    <div class="actions">
      <h3 @click="toggleShowDetails">{{ project.title }}</h3>
      <div class="icons">
        <span class="material-symbols-outlined">edit</span>
        <span class="material-symbols-outlined">delete</span>
        <span class="material-symbols-outlined">done</span>
      </div>
    </div>
    <div class="details" v-if="showDetails">
      <p>
        {{ project.details }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: ['project'],
  data() {
    return {
      showDetails: false,
    };
  },
  methods: {
    toggleShowDetails() {
      this.showDetails = !this.showDetails;
    },
  },
};
</script>

<style>
.project {
  margin: 20px auto;
  background: white;
  padding: 10px 20px;
  border-radius: 4px;
  box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.05);
  border-left: 4px solid #e90074;
}

h3 {
  cursor: pointer;
}

.actions {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.material-symbols-outlined {
  font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 48; /* per Google's instructions */
  font-size: 24px;
  margin-left: 10px;
  color: #bbb;
  cursor: pointer;
}

.material-symbols-outlined:hover {
  color: #777;
}
</style>
