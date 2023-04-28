<script>
  import Hero from "../../components/Hero.svelte";
	import TankCard from "../../components/TankCard.svelte";
  import StatsCard from "../../components/StatsCard.svelte";
  import ControlCard from "../../components/ControlCard.svelte";
</script>

<Hero />
<div class="flex flex-col items-center justify-center">
  <TankCard />
  <div class="grid grid-cols-1 md:grid-cols-2">
    <StatsCard />
    <ControlCard />
  </div>
</div>