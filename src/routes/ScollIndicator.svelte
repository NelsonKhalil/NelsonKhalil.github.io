<script>
    import { onMount } from 'svelte';
    let hide = false;

    const handleScroll = () => {
      hide = window.scrollY > 0;
    };

    onMount(() => {
      window.addEventListener('scroll', handleScroll);
      return () => window.removeEventListener('scroll', handleScroll);
    });
</script>

<div class="absolute bottom-5 left-1/2 transform -translate-x-1/2 scale-250 animate-bounce duration-300 {hide ? "opacity-0" : "opacity-100"}">
    <i class="fi fi-rr-angle-small-down"></i>
</div>