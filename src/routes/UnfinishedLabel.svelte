<script>
	import TooltipWrapper from "./TooltipWrapper.svelte";

    let {classes=""} = $props()
</script>

<TooltipWrapper text="Dieses Projekt ist unfertig!">
    <div class="m-1 mx-0 p-1 bg-gray-100 rounded-2xl border-2 border-gray-300 hover:border-gray-400 shadow-2xl {classes}">
        <i class="fi fi-rr-calendar-xmark relative top-0.5"></i>
    </div>
</TooltipWrapper>