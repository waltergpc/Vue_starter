<template>
  <div>
    <p>This is the pop-up</p>
    <button @click="$emit('close')">Close pop up</button>
  </div>
</template>

<script>
export default {
  name: 'PopUp',
  emits: ['close'],
}
</script>

<style lang="scss" scoped></style>
