<script>
export default {
  props: ['item', 'index']
}
</script>

<template>
  <div class="bombastic">
    <div class="limiter">
      <ul>
        <li id="add">item</li>
        <li id="add">banana</li>
        <li id="add">banana</li>
        <li id="add">banana</li>
      </ul>
    </div>
    <button class="edit" @click="closeEdit">Edit</button>
  </div>
</template>

<style scoped>
.limiter {
  text-align: center;
  justify-content: center;
  align-items: center;
  background: #141e29;
  margin: 5px;
  border-radius: 6px;
}

ul {
  display: inline-block;
  text-align: left;
  padding: 0;
}

.edit {
  margin: 0 1rem;
  align-items: center;
  justify-content: center;
  border: none;
  background: #141e29;
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
  font-size: 14px;
  width: 5rem;
  height: 3rem;
}
</style>
