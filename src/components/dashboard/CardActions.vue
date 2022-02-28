<template>
  <div
    class="actions-container bg-primary-layer pv-10 ph-5"
  >
    <div
      class="flex-row font-small-med text-primary justify-around"
    >
      <flex-col
        col="2"
        class="pointer-cursor"
        @click="cardAction('toggle-card-active')"
      >
        <div
          class="action-container"
        >
          <img
            :src="require('@assets/media/svg/ice_flake.svg')"
            class="bg-primary p-2 radius-15 freeze-card"
          >
        </div>
        <div
          class="action-container"
        >
          <span>
            Freeze Card
          </span>
        </div>
      </flex-col>
      <flex-col
        col="2"
      >
        <div
          class="action-container"
        >
          <img
            :src="require('@assets/media/svg/dashboard.svg')"
            class="bg-primary p-5 radius-15 spend-limit"
          >
        </div>
        <div
          class="action-container"
        >
          <span>
            Set spend limit
          </span>
        </div>
      </flex-col>
      <flex-col
        col="2"
      >
        <div
          class="action-container"
        >
          <img
            :src="require('@assets/media/svg/gpay.svg')"
            class="add-to-gpay"
          >
        </div>
        <div
          class="action-container"
        >
          <span>
            Add to GPay
          </span>
        </div>
      </flex-col>
      <flex-col
        col="2"
      >
        <div
          class="pb-10 mt-6 action-container"
        >
          <span
            class="bg-primary pt-4 pb-5 ph-7 radius-15"
          >
            <i class="fas fa-undo text-white font-small" />
          </span>
        </div>
        <div
          class="action-container"
        >
          <span>Replace Card</span>
        </div>
      </flex-col>
      <flex-col
        col="2"
        class="pointer-cursor"
        @click="cardAction('cancel-card')"
      >
        <div
          class="pb-10 mt-6 action-container"
        >
          <span
            class="bg-primary pt-4 pb-5 ph-8 radius-15"
          >
            <i class="far fa-trash-alt text-white font-small" />
          </span>
        </div>
        <div
          class="action-container"
        >
          <span>Cancel Card</span>
        </div>
      </flex-col>
    </div>
  </div>
</template>

<script>
import FlexCol from '@components/utils/FlexCol';

export default {
  components: { FlexCol },
  emits: ['event-emitted'],
  setup (_, { emit }) {
    function cardAction (action, payload) {
      emit('event-emitted', action, payload);
    }
    return {
      cardAction
    };
  }
};
</script>

<style lang="scss" scoped>
.action-container{
    text-align:center;
    // padding:5px;

    .freeze-card{
      height:20px;
      width:20px;
    }

    .spend-limit{
      height:15px;
      width:15px;
    }

    .add-to-gpay{
      height:25px;
      width:25px
    }
}

@media screen and (max-width:720px){
  .actions-container{
    background:#edf3ff;
    padding-right:10px;
    border-radius:15px 15px 0 0;
  }
}

@media screen and (min-width:720px){
  .actions-container{
    border-radius:15px;
  }
}
</style>
