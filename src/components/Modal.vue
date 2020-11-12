<template>
    <div v-on:click="modalOpen=true">
        <slot name="modal-trigger"></slot>
    </div>

    <teleport to="body">
        <div v-if="modalOpen" class="modal">
            <div class="modal__content">
                <slot name="modal-content"></slot>
                <button class="modal__close" @click="modalOpen=false">
                    <i class="fas fa-times"></i>
                </button>
            </div>
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

<style lang="scss">
.modal {
    z-index: 100;
    position: fixed;
    top: 0; right: 0; bottom: 0; left: 0;
    background-color: rgba(0,0,0,.5);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    &__content {
        display: flex;
        position: relative;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        max-width: calc(100% - 5rem);
        max-height: calc(100% - 5rem);
        width: auto;
        height: auto;

        >img {
            max-height: 100%;
        }
    }

    &__close {
        position: absolute;
        right: -2rem;
        top: -2rem;
        background: transparent;
        border: none;

        i.fas {
            text-shadow: 0px 1px 2px rgba(0, 0, 0, 0.4);
            font-size: 1.5rem;
            color: #fff;
        }
    }
}
</style>