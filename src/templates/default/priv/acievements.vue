<template>
  <div>
    <div class="achievement title">
      <h3 class="text-uppercase" contenteditable>Achievements</h3>
      <button @click="count++" class="btn btn-primary btn-xs hidden-print add"><i class="fa fa-plus"></i> </button>
    </div>

    <removeable-container v-for="c in count" :onRemove="x => count--">
      <div>
        <strong contenteditable>2017</strong>
        <strong style="color: #F44337; font-size: 0.95em" class="text-uppercase" contenteditable>{{ lipsum.generate(4) }}</strong>
      </div>
      <p class="paragraph" contenteditable>
        {{ lipsum.generate(10) }}
      </p>
    </removeable-container>
  </div>
</template>

<script>
  import lipsum from "@/utils/lipsum"
  import RemoveableContainer from "@/components/RemovableContainer.vue"

  export default {
    components: {
      RemoveableContainer
    },
    data: () => ({
      lipsum,
      count: 1
    })
  }
</script>

<style lang="scss">
  .achievement.title {
    position: relative;

    .btn.add {
      visibility: hidden;
      position: absolute;
      right: 0;
      top: 0;
    }

    &:hover { .btn.add { visibility: visible; } }
  }
</style>
