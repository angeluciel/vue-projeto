<script>
export default {
  methods: {
    closeModal() {
      this.$emit('close')
    }
  },
  props: ['theme']
}
</script>

<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ darkmode: theme === 'dark' }">
      <slot></slot>
      <div class="actions">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>

<style>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}

.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}

.modal h1 {
  color: #73e9cf;
  border: none;
  padding: 0;
}

.modal p {
  color: black;
}

.modal.darkmode {
  background: crimson;
  color: white;
}

.modal.darkmode h1 {
  color: white;
}

.modal .actions {
  text-align: center;
  margin: 30px 0 10px 0;
  color: #333;
}

.modal .actions a {
  margin: 0 1rem;
  align-items: center;
  justify-content: center;
  padding: 1rem 1rem;
  border: none;
  border-bottom: 0.2rem solid #e85281;
  background: #2c3e50;
  color: white;
  border-radius: 0.5rem;
  outline: none;
  cursor: pointer;
  overflow: hidden;
  text-align: center;
  transition: 0.25s ease all;
  font-family: 'Roboto', sans-serif;
  font-weight: 500;
  font-style: normal;
  font-size: 12px;
  text-decoration: none;
}

.modal .actions a:hover {
  background: #1e2b38;
}
.modal .actions a:focus:active {
  transform: perspective(0.1rem) scale3d(0.98, 0.98, 1) translate3d(0, 0.2rem, 0);
  background-color: #1e2b38;
  border-bottom: 0.2rem solid transparent;
}

.modal.darkmode .actions a {
  color: gray;
}
</style>
