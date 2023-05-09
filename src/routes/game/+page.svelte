<script>
    import Classement from "../components/classement.svelte";
    import Statistique from "../components/statistique.svelte";

    function test() {
        console.log("bite")
    }

</script>

<div class="flex h-screen bg-black">
    <div class="flex flex-col">
        <div class="ml-10 mt-8 h-[60px] w-[750px] bg-[#74121D] rounded-full">
            <h1 class="text-center mt-3 text-3xl text-[#FFFFFF]">tu à actuellement 5000 points</h1>
        </div>
        <button class="mt-[100px] ml-[150px] " on:click={test}>
            <img src="./bouton.png" alt="bouton" class="pointer-events-none">
        </button>
    </div>
    <div class="flex-col">
        <div class="ml-[250px] mt-8 h-[250px] w-[300px] bg-[#74121D] rounded-3xl pt-2">
            <div class="mt-4 ml-4 h-[60px] w-[270px] bg-[#EBE9E9] rounded-full align-middle pt-[10px]">
                <h1 class="text-center text-[#74121D] text-3xl font-extrabold">Amélioration</h1>
            </div>
            <button class="mt-4 ml-6 h-[40px] w-[250px] bg-[#EBE9E9] rounded-full align-middle hover:bg-[#A7333F] hover:text-white text-[#74121D] transition-all">
                <h1 class="text-center text-2xl font-semibold">Gain par click</h1>
            </button>
            <button class="mt-4 ml-6 h-[40px] w-[250px] bg-[#EBE9E9] rounded-full align-middle hover:bg-[#A7333F] hover:text-white text-[#74121D] transition-all">
                <h1 class="text-center  text-2xl  font-semibold">temps entre 2 click</h1>
            </button>
        </div>
        <Statistique/>
    </div>
    <Classement/>


</div>