<script>
    let {title, icon, classes="", children} = $props()
</script>

<div class="m-1 mx-0 p-1 bg-gray-100 rounded-2xl border-2 border-violet-300 shadow-2xl flex items-start {classes}">
    <i class="{icon} m-2 relative top-1"></i>
    <div class="flex flex-col items-start">
        <span class="font-bold text-[1.25em] m-2">{title}</span>
        <div class="leading-tight m-2">
            {@render children()}
        </div>
    </div>

</div>