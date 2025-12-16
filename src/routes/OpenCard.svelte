<script>
	import TooltipWrapper from "./TooltipWrapper.svelte";

    let {href, icon, classes=""} = $props()
</script>

<TooltipWrapper text='Link öffnen:<br><span class="text-blue-400 decoration-blue-500 underline">{href}'>
    <a aria-label="openCard" target="_blank" href={href} class="m-1 mx-0 p-1 bg-gray-100 rounded-2xl border-2 border-gray-300 hover:border-gray-400 shadow-2xl {classes}">
        <i class="{icon} relative top-0.5"></i>
    </a>
</TooltipWrapper>