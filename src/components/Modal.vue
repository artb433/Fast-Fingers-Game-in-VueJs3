<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal">
      <slot></slot>
      <div class="actions">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Modal',
  props: [],
  methods: {
   closeModal(){
    this.$emit('close')
   }
  }
}
</script>

<style scoped>
.modal {
  padding: 20px;
  border-radius: 10px;
  width: 400px;
  margin: 100px auto;
  background:white;
}

.backdrop {
top: 0;
position: fixed;
background: rgba(0, 0, 0, 0.5);
width: 100%;
height: 100%
}

h1 {
 color: #03cfb4;
 border: none;
 padding: 0;
}

</style>