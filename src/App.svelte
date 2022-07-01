<script>
  import { onMount } from 'svelte';
  import { IfcViewerAPI } from 'web-ifc-viewer';
  
  let container;

  onMount(async () => {
    const viewer = new IfcViewerAPI({ container });

    viewer.axes.setAxes();
    viewer.grid.setGrid();

    viewer.IFC.loadIfcUrl('/martin.ifc');
  });

</script>

<div bind:this={container}></div>

<style>
  div {
    width: 100vw;
    height: 100vh;
  }
</style>