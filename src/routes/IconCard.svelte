<script>
    let {text, icon, classes=""} = $props()
</script>

<div class="m-1 mx-0 p-1 bg-gray-100 rounded-2xl border-2 border-gray-300 shadow-2xl {classes}">
    <i class="{icon} relative top-0.5"></i>
    <span>{text}</span>
</div>