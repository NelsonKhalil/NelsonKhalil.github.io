<script>
	import Card from "./Card.svelte";
	import IconCard from "./IconCard.svelte";

    let {visible} = $props()
</script>

<div class="bg-gray-200 h-[calc(100%-60px)] p-5 w-60 right-0 bottom-0 flex flex-col fixed z-50 duration-300 {visible ? "translate-x-0" : "translate-x-full"}">
    <a href="#start">
        <Card title="Start" text="Bild und Einführung" icon="fi fi-rr-portrait" />
    </a>
    <a href="#informationen">
        <Card title="Informationen" text="Generelle Informationen" icon="fi fi-rr-info" />
    </a>
    <a href="#projekte">
        <Card title="Projekte" text="Manche unfertig" icon="fi fi-rr-blueprint" />
    </a>
</div>

<div class="backdrop-blur-[3px] backdrop-brightness-50 h-full w-full fixed left-0 top-0 z-30 pointer-events-none duration-300 {visible ? "opacity-100" : "opacity-0"}"></div>