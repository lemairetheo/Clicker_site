<script>
    let names = ["Alice", "Bob", "Charlie", "bite", "bite", "bite", "bite", "bite"];
</script>

<div class="ml-[50px] mt-8 h-[830px] w-[480px] bg-[#74121D] rounded-3xl pt-2">
    <div class="mt-4 ml-4 h-[60px] w-[450px] bg-[#EBE9E9] rounded-full align-middle pt-[10px]">
        <h1 class="text-center text-[#74121D] text-3xl font-extrabold">Résumé</h1>
    </div>
    {#each names as name, index}
        <div class="flex flex-row">
            <div class="text-[#EBE9E9]">
                <h1 class="ml-[20px] mt-12 text-center text-2xl font-semibold">#{index + 1}</h1>
            </div>
            <div class="mt-10 ml-[20px] h-[50px] w-[330px] bg-[#EBE9E9] rounded-full align-middle hover:bg-[#A7333F] hover:text-white text-[#74121D] transition-all">
                <h1 class="text-center text-2xl font-semibold">{name}</h1>
            </div>
        </div>
    {/each}
</div>