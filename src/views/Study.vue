<script setup>

</script>

<template>
    <div>
        <div class="main">
            <div class="fixed l1">固定200px</div>
            <div class="auto r1">自动充满</div>
        </div>
        <div class="main2">
            <div class="fixed l2">固定200px</div>
            <div class="auto r2">自动充满</div>
        </div>
        <div class="main3">
            <div class="fixed l3">固定200px</div>
            <div class="auto r3">自动充满</div>
        </div>
        <div class="main4">
            <div class="fixed l4">固定200px</div>
            <div class="auto r4">自动充满</div>
        </div>
        <div class="main5">
            <div class="fixed l5">固定200px</div>
            <div class="auto r5">自动充满</div>
        </div>
    </div>
</template>

<style>
    .main, .main2, .main3, .main4, .main5 {
        width: 1200px;
        position: relative;
    }

    .fixed {
        background-color: blueviolet;
        width: 200px;
        height: 200px;
    }

    .auto {
        height: 200px;
        background-color: goldenrod;
    }

    .l1 {
        float: left
    }

    .r1 {
        width: 100%;
        padding-left: 200px;
        box-sizing: border-box;
    }

    .main2 {
        display: flex;
    }

    .l2 {
        flex: 0 0 200px;
    }

    .r2 {
        flex: 1;
    }

    .l3 {
        float: left;
    }

    .r3 {
        margin-left: 200px;
    }

    .r4 {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        box-sizing: border-box;
        padding-left: 200px;
        z-index: -1;
    }

    .l5 {
        position: relative;
        float: left;
    }
    
    .r5 {
        float: left;
        margin-left: -200px;
        padding-left: 200px;
        width: 100%;
        box-sizing: border-box;
    }
</style>