<script>
  export let type;
  export let label;
  export let id;
  export let placeholder;
  export let rows;
  export let value;
</script>

<div class="form-control">
  {#if type === "textarea"}
    <label for={id}>{label}</label>
    <textarea on:input {value} {id} {rows} {placeholder}></textarea>
  {:else}
    <label for={id}>{label}</label>
    <input on:input {type} {value} {id} {placeholder} />
  {/if}
</div>

<style>
  .form-control {
    margin: 1.5rem 0;
    width: 100%;
  }
  label {
    display: block;
    text-align: center;
  }

  input,
  textarea {
    outline: none;
    border: none;
    border-bottom: 1px solid gray;
    width: 100%;
    padding: 0.50rem 0.25rem;
  }
  input:focus,
  textarea:focus {
    border-bottom: 2px solid #cf0056;
  }
</style>
