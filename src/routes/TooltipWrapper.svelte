<script>
    import { globalState } from './globalState.svelte.js'

    let {text, children, classes=""} = $props()

    function show() {
        globalState.tooltipText = text;
    }
    function hide() {
        globalState.tooltipText = "";
    }
</script>

<div class="{classes}" role="tooltip" onmouseenter={show} onmouseleave={hide}>
    {@render children()}
</div>