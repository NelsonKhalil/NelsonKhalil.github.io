<script>
    import Sidemenu from "./Sidemenu.svelte";
    let visible = false;

    function hamburgerMenuClick() {
        visible = !visible;
    }
</script>

<div class="bg-gray-100 w-full p-5 h-15 flex items-center justify-between fixed etched-rectangle z-40">
    <div class="flex space-x-1">
        <i class="fi fi-rr-angle-small-right relative top-0.5"></i>
        <span>Nelson Khalil</span>
    </div>
    <button class="flex duration-100 hover:scale-120" aria-label="hamburger-menu-button" onclick={hamburgerMenuClick}>
        <i class="{visible ? "fi fi-rr-cross-small" : "fi fi-rr-menu-burger"}"></i>
    </button>
</div>

<Sidemenu {visible} />

<style>
    .etched-rectangle {
        clip-path: polygon(
          0% 0%,
          100% 0%,
          100% 100%,
          75% 100%,
          75% 90%,
          25% 90%,
          25% 100%,
          0% 100%
        );
    }
</style>