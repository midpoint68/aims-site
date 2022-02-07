<script type="ts">
  import Header from "$src/components/Header.svelte";
</script>

<div id="wrapper">
  <Header />
  <slot></slot>
</div>

<style>
  #wrapper {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background-image: radial-gradient(
          farthest-side at center 20%,
          var(--bg-color) 0,
          var(--bg-color) 30%,
          var(--bg-color-2) 100%
      );
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      align-items: stretch;
  }
</style>