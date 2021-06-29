<div class="content-wrapper">
  <slot></slot>
</div>
<style lang='scss'>
  .content-wrapper {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }
  .content-wrapper > :global(main) {
    flex: 1;
  }
</style>