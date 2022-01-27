<script>
  let className;

  export let value = false;
  export let disabled = false;
  export let type = 'button';
  export let label = 'Button';
</script>

<button value={value} disabled={disabled} type={type} aria-label={label}>
  <slot></slot>
</button>