<script>
    let {title, text, icon, classes="", border="border-violet-300"} = $props()
</script>

<div class="m-1 mx-0 p-1 bg-gray-100 rounded-2xl border-2 {border} shadow-2xl flex flex-col items-center {classes}">
    <i class="{icon} m-2"></i>
    <div class="flex flex-col text-center">
        <span class="font-bold text-[1.25em]">{title}</span>
        <span class="mb-2">{text}</span>
    </div>
</div>
