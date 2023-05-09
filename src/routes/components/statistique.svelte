<script>
    let stats = ["12/04 : 10000 Point", "12/04 : 10000 Point","12/04 : 10000 Point","12/04 : 10000 Point","12/04 : 10000 Point","12/04 : 10000 Point","12/04 : 10000 Point", "..."]
</script>

<div class="ml-[250px] mt-8 h-[550px] w-[300px] bg-[#74121D] rounded-3xl pt-2">
    <div class="mt-4 ml-4 h-[60px] w-[270px] bg-[#EBE9E9] rounded-full align-middle pt-[10px]">
        <h1 class="text-center text-[#74121D] text-3xl font-extrabold">Résumé</h1>
    </div>
    {#each stats as stat}
        <div class="mt-4 ml-6 h-[40px] w-[250px] bg-[#EBE9E9] rounded-full align-middle hover:bg-[#A7333F] hover:text-white text-[#74121D] transition-all">
            <h1 class="text-center text-2xl font-semibold">{stat}</h1>
        </div>
    {/each}
</div>