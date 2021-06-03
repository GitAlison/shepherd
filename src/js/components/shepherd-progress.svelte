<script>
  export let tour;
  $: steps = tour.steps;
  $: currentStep = tour.getCurrentStep().id;

</script>

<div class="shepherd-progress">
  {#if steps}
    {#each steps as step}
      <span
        class="shepherd-progress-dot"
        class:active={currentStep == step.id}
      />
    {/each}
  {/if}
</div>

<style global>
  .shepherd-progress {
    border-bottom-left-radius: 5px;
    border-bottom-right-radius: 5px;
    display: flex;
    align-items: center;
    padding: 0 5px;
  }
  .shepherd-progress .shepherd-progress-dot:first-child {
    padding-left: 5px;
  }
  .shepherd-progress .shepherd-progress-dot:last-child {
    padding-right: 5px;
  }
  .shepherd-progress .shepherd-progress-dot {
    width: 10px;
    height: 10px;
    border-radius: 10px;
    background-color: #c6d6ff;
    margin: 0px 5px;
  }
  .shepherd-progress .shepherd-progress-dot.active {
    background-color: #4c6cdd;
  }

</style>
