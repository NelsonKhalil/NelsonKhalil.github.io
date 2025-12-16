<script>
    import Topbar from './Topbar.svelte'
    import SmallCard from './SmallCard.svelte'
    import IconCard from './IconCard.svelte';
    import ScollIndicator from './ScollIndicator.svelte';
    import Card from './Card.svelte';
    import BigCard from './BigCard.svelte';
    import background from '$lib/assets/background.png';
    import Tooltip from './Tooltip.svelte';
	import OpenCard from './OpenCard.svelte';
	import UnfinishedLabel from './UnfinishedLabel.svelte';
	import TooltipWrapper from './TooltipWrapper.svelte';
    import Image from '$lib/assets/image.jpg';

    let age = getAge();
    function getAge() {
        return ((Date.now() / 1000) - 1289090760) / 31536000;
    }

    setInterval(() => {
        age = getAge();
    }, 100);
</script>

<main class="min-h-screen bg-repeat" style="background-image: url({background});">
    <Tooltip />
    <Topbar />

    <section id="start" class="min-h-[150vh] lg:min-h-screen flex flex-col lg:flex-row items-center justify-center gap-10 px-8">
        <img
          class="bg-gray-300 w-80 h-80 shadow-2xl border-t-6 border-l-6 border-b-6 border-r-6
            [border-top-color:#808080]
            [border-left-color:#808080]
            [border-bottom-color:#a0a0a0]
            [border-right-color:#a0a0a0]"
          src="{Image}"
          alt="Profilbild"
        />

        <div class="flex flex-col items-center lg:items-start gap-4 lg:gap-5">
        
          <div class="text-center lg:text-left">
            <span class="text-6xl font-black">Hallo</span><br />
            <span>Mein Name ist</span>
            <span class="border-b-3 border-violet-400">Nelson Khalil</span><span>,</span><br />
            <span>ich bin</span>
            <span class="border-b-2 border-violet-500 font-mono">{age.toFixed(8)}</span>
            <span>Jahre alt und</span><br />
            <span>mich fasziniert:</span>
          </div>
      
          <div class="flex gap-3">
            <SmallCard text="Programmieren" />
            <SmallCard text="Softwareentwicklung" />
            <SmallCard text="Minecraft modding" />
          </div>
      
          <div class="flex flex-col gap-3 items-center lg:items-start">
            <div class="flex gap-3">
              <IconCard text="Pyhton" icon="fi fi-rr-snake" />
              <IconCard text="Java" icon="fi fi-rr-mug-hot-alt" />
            </div>

            <div class="flex gap-3">
              <IconCard text="HTML" icon="fi fi-rr-layout-fluid" />
              <IconCard text="CSS" icon="fi fi-rr-palette" />
              <IconCard text="JavaScript" icon="fi fi-rr-cursor-finger" />
            </div>
          </div>
      
        </div>
    </section>



    <section id="informationen" class="scroll-mt-32 xl:text-base lg:text-[0.8rem] text-[0.5rem] grid grid-cols-16 grid-rows-4 gap-4 grid-flow-dense m-8 rounded p-4 backdrop-blur-[1px] outline-2 outline-white shadow-2xl">
        <Card classes="col-span-4 row-span-1" title="Nelson Khalil" text="Name" icon="fi fi-rr-user"/>
        <Card classes="col-span-4 row-span-1" title="nelsonkhalil111@gmail.com" text="Email" icon="fi fi-rr-envelope-open"/>
        <Card classes="col-span-4 row-span-1" title="07. 11. 2010" text="Geburtsdatum" icon="fi fi-rr-fingerprint"/>

        <BigCard classes="col-span-4 row-span-3" title="Sprachen" icon="fi fi-rr-world">
            {#snippet children(_)}
                <br>
                <span class="font-semibold">Deutsch</span>
                <br>
                <span>Muttersprache</span>
                <br><br>
                <span class="font-semibold">Englisch</span>
                <br>
                <span>B2</span>
                <br><br>
                <span class="font-semibold">Spanisch</span>
                <br>
                <span>A2</span>
            {/snippet}
        </BigCard>
        <BigCard classes="col-span-4 row-span-3" title="Bildungsweg" icon="fi fi-rr-books">
            {#snippet children(_)}
                <br>
                <span class="font-semibold">Käthe-Kollwitz-Gymnasium (MINT)</span>
                <br>
                <span>08 . 2022 - HEUTE</span>
                <br>
                <span class="italic">Dunckerstraße 65, 10439 Berlin</span>
                <br><br>
                <span class="font-semibold">Erika-Mann-Grundschule</span>
                <br>
                <span>09 . 2016 - 07 . 2022</span>
                <br>
                <span class="italic">Utrechter Str. 25, 13347 Berlin</span>
            {/snippet}
        </BigCard>
        <BigCard classes="col-span-8 row-span-3" title="Besondere Schulische Projekte" icon="fi fi-rr-physics">
            {#snippet children(_)}
                <br>
                <span class="font-semibold">mPa (mediengestüzte Projektarbeit)</span>
                <br>
                <span>09 . 2024 - 02 . 2025</span>
                <br>
                <span class="italic">Gobalisierung in Madagaskar</span>
                <br><br>
                <span class="font-semibold">Zukunftsprojekt (Futurium & Planetarium)</span>
                <br>
                <span>08 . 2023 - 07 . 2024</span>
                <br>
                <span class="italic">Erneuerbare Energien</span>
                <br><br>
                <span class="font-semibold">Forscherprojekt</span>
                <br>
                <span>01 . 2023 - 06 . 2023</span>
                <br>
                <span class="italic">Virtual-Reality</span>
            {/snippet}
        </BigCard>
        <TooltipWrapper classes="col-span-4 row-span-1" text="Informationen wie: Telefonnummer und Adresse wurden hier versteckt um sie vor dem Internet zu schützen.">
            <Card border="border-gray-400" title="Fehlende Informationen" text="Manche Informationen sind hier versteckt, benutzen sie die PDF-Bewerbung!" icon="fi fi-rr-eye-crossed"/>
        </TooltipWrapper>
    </section>

    <section id="projekte" class="scroll-mt-16 grid grid-cols-1 grid-rows-3 gap-4 m-8 mt-32 rounded p-4 backdrop-blur-[1px] outline-2 outline-white shadow-2xl">
        <div>
            <span class="m-2 text-3xl italic border-b-3 border-violet-600">Java</span>
            <div class="m-1 mt-8 grid xl:grid-cols-8 md:grid-cols-4 grid-cols-2 grid-rows-1 gap-4">
                <BigCard classes="relative" title="PyTools" icon="fi fi-rr-snake">
                    {#snippet children(_)}
                        <span>Ein JavaFX programm welches python programme mit Eingabefeldern ausführt.</span>
                        <OpenCard classes="absolute top-0 right-1 aspect-square" href="https://github.com/NelsonKhalil/PyTools" icon="fi fi-rr-link" />
                        <UnfinishedLabel classes="absolute top-0 right-9 aspect-square" />
                    {/snippet}
                </BigCard>
            </div>
        </div>
        <div>
            <span class="m-2 text-3xl italic border-b-3 border-violet-600">Python</span>
            <div class="m-1 mt-8 grid xl:grid-cols-8 md:grid-cols-4 grid-cols-2 grid-rows-1 gap-4">
                
            </div>
        </div>
        <div>
            <span class="m-2 text-3xl italic border-b-3 border-violet-600">Sonstiges</span>
            <div class="m-1 mt-8 grid xl:grid-cols-8 md:grid-cols-4 grid-cols-2 grid-rows-1 gap-4">
                <BigCard classes="relative" title="Lebenslauf Website" icon="fi fi-rr-resume">
                    {#snippet children(_)}
                        <span>Das ist diese Website!</span>
                        <IconCard classes="mt-5" text="Svelte" icon="fi fi-rr-code-simple" />
                        <OpenCard classes="absolute top-0 right-1 aspect-square" href="https://github.com/NelsonKhalil/nelson-khalil.github.io" icon="fi fi-rr-link" />
                    {/snippet}
                </BigCard>
            </div>
        </div>
    </section>

    <br><br><br>

    <ScollIndicator />
</main>


<style>
	:global(*) {
		font-family: Arial, Helvetica, sans-serif;
	}

    :global(*::-webkit-scrollbar) {
        width: 0.5rem;
    }

    :global(*::-webkit-scrollbar-track) {
        background: #d3d4d6;
    }

    :global(*::-webkit-scrollbar-thumb) {
        background-color: #9d96fa;
    }

</style>
