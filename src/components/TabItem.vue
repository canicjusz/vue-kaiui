<template>
  <div class="kaiui-tabitem-wrapper" v-if="isActive">
    <div class="kaiui-tabitem-slot-content">
      <!-- Use this slot to include components in a tab-item. -->
      <slot></slot>
    </div>
  </div>
</template>

<script>
/**
 * The `<kaiui-tab-item>` component.
 *
 * @author Sebastian Baar
 * @license MIT
 */
export default {
  name: "kaiui-tab-item",
  props: {
    /**
     * The Name
     */
    name: {
      type: String,
      required: true,
    },
    /**
     * If the Tab Item should be selected
     */
    selected: {
      type: Boolean,
      default: false,
    },
  },
  mounted() {
    this.isActive = this.selected;
  },
  data: () => ({
    /**
     * @private
     */
    isActive: false,
  }),
};
</script>

<style>
.kaiui-tabitem-wrapper {
  display: flex;
  flex-direction: column;
  height: 100%;
  flex: 1;
  min-width: 100%;
}
.kaiui-tabitem-wrapper .kaiui-tabitem-slot-content {
  display: flex;
  flex-direction: column;
  min-height: 0;
  flex: 1;
  overflow: hidden;
}
</style>
