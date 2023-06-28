<template>
    <div class="card">
        <form>
            <div class="flex gap-5 items-end">
                <div class="w-5/12">
                    <label for="url" class="text-white">Orignal URL</label>
                    <input type="text" name="url" id="url">
                </div>
                <div class="w-5/12">
                    <label for="shortKey" class="text-white">Custom Key</label>
                    <input type="text" name="shortKey" id="shortKey">
                </div>
                <div class="w-2/12">
                    <button class="btn py-3">Shorten</button>
                </div>
            </div>
        </form>
    </div>
</template>

<script setup>

</script>

<style>

</style>