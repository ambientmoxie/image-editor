<script>
  import { postConfig } from "../js/stores";
  import ColorPicker from "./ColorPicker.svelte";
  import { downloadPost } from "../js/helpers";
</script>

<div id="form">
  <div id="form-left">
    <div class="input-container">
      <!-- svelte-ignore a11y-label-has-associated-control -->
      <label> Job title: </label>
      <input
        bind:value={$postConfig.content.tags}
        placeholder="ex: Node.js expert"
      />
    </div>

    <div class="input-container">
      <!-- svelte-ignore a11y-label-has-associated-control -->
      <label> Job description: </label>
      <textarea
        bind:value={$postConfig.content.description}
        placeholder="ex: Nullam imperdiet hendrerit dui ut rhoncus. Morbi faucibus eu diam a tincidunt. Praesent metus lacus, auctor vitae risus in, scelerisque sagittis sem. In dapibus faucibus ante sit amet ullamcorper. Donec mauris nisi, iaculis quis ullamcorper."
      />
    </div>

    <div class="input-container">
      <!-- svelte-ignore a11y-label-has-associated-control -->
      <label> Salary: </label>
      <input
        bind:value={$postConfig.content.salary}
        placeholder="ex: 60K to 50K"
      />
    </div>

    <div class="input-container">
      <!-- svelte-ignore a11y-label-has-associated-control -->
      <label> Location: </label>
      <input
        bind:value={$postConfig.content.location}
        placeholder="ex: Paris and remote"
      />
    </div>

    <div class="input-container">
      <!-- svelte-ignore a11y-label-has-associated-control -->
      <label> Contract: </label>
      <input
        bind:value={$postConfig.content.contract}
        placeholder="ex: Open-ended contract"
      />
    </div>
  </div>
  <div id="form-right">
    <ColorPicker
      label="Background color"
      placeholder="ex: #FFFFFF"
      bind:value={$postConfig.theme.background}
    />

    <ColorPicker
      label="Text color"
      placeholder="ex: #000000"
      bind:value={$postConfig.theme.text}
    />
  </div>
</div>

<button
  on:click={() => downloadPost(2000, $postConfig.target)}
  class="download-button">download</button
>

<style lang="scss">
  #form {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    width: 100%;
    max-width: 61rem;
    > div {
      flex: 1;
      > :global(*:not(:last-child)) {
        margin-bottom: 1rem;
        min-width: 30rem;
      }
    }
  }

  :global(.input-container) {
    font-size: 1.1rem;
    display: flex;
    flex-direction: column;
    :global(label) {
      margin-bottom: 5px;
    }
  }
</style>
