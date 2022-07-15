<script>
  export let style = "primary";
  export let disabled = false;
  export let type = Button;
</script>

<button {type} {disabled} class={style}> <slot /> </button>

<style>
  button {
    color: #fff;
    border: 0;
    border-radius: 2px;
    color: #fff;
    min-width: 160px;
    height: 40px;
    cursor: pointer;
    font-weight: bold;
  }

  .primary {
    background-color: #00b4b3;
  }

  .secondary {
    background: #ff6a95;
  }

  button:hover {
    transform: scale(0.98);
    opacity: 0.9;
  }

  button:disabled {
    background-color: #cccccc;
    color: #333;
    cursor: auto;
  }

  button:disabled:hover {
    transform: scale(1);
    opacity: 1;
  }
</style>
