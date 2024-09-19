<script>
  export let label = "";
  export let type = "text";
  export let value = "";
  export let required = false;
  export let error = "";

  let inputId = "input-" + Math.random().toString(36).substring(2, 9);
</script>

<div class="input-wrapper">
  <label for={inputId}>{label}{required ? "*" : ""}</label>

  {#if type === "text"}
    <input
      id={inputId}
      type="text"
      bind:value
      class:error={!!error}
      {required}
    />
  {:else if type === "tel"}
    <input
      id={inputId}
      type="number"
      bind:value
      class:error={!!error}
      {required}
    />
  {:else if type === "email"}
    <input
      id={inputId}
      type="email"
      bind:value
      class:error={!!error}
      {required}
    />
  {:else if type === "textarea"}
    <textarea
      id={inputId}
      bind:value
      class:error={!!error}
      {required}
    />
  {/if}

  {#if error}
    <span class="error-message">{error}</span>
  {/if}
</div>

<style>
    .input-wrapper {
        margin-bottom: 20px;
    }
    label {
        color: rgb(121, 126, 163);
        font-size: 15px;
        font-weight: 300;
    }
    input, textarea {
        width: 100%;
        padding: 4px;
        border: none;
        background: none;
        border-bottom: 1px solid rgb(63, 67, 99);
    }
    textarea {
        resize: none;
    }
    textarea::-webkit-scrollbar {
        width: 5px;
    }
    textarea::-webkit-scrollbar-thumb {
        background: rgb(63, 67, 99);
        border-radius: 6px;
    }
    textarea::-webkit-scrollbar-track {
        background: none;
        border-radius: 6px;
    }
    input:focus-visible, textarea:focus-visible {
        outline: none;
        border-color: rgb(255, 255, 255);
    }
    .input-wrapper:focus-within label {
        color: rgb(255, 255, 255);
    }
    input.error {
        border-color: red;
    }
    .error-message {
        color: red;
        font-size: 12px;
    }

    @media screen and (max-width: 800px) {
        .input-wrapper {
            margin-bottom: 12px;
        }
        label {
            font-size: 12px;
        }
        .error-message {
            color: red;
            font-size: 10px;
        }
    }

</style>
