<template>
    <div v-on:click="modalOpen=true">
        <slot name="modal-trigger"></slot>
    </div>

    <teleport to="body">
        <div v-if="modalOpen" class="modal">
            <slot name="modal-content"></slot>
            <button @click="modalOpen=false">
                Close
            </button>
        </div>
    </teleport>
</template>

<script>

export default {
  name: 'Modal',
  
  data() {
      return {
        modalOpen: false
      }
  }
}
</script>

<style>
.modal {
    z-index: 100;
    position: fixed;
    top: 0; right: 0; bottom: 0; left: 0;
    background-color: rgba(0,0,0,.5);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.modal div {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: white;
    width: 300px;
    height: 300px;
    padding: 5px;
}
</style>