<template>
<div class="main-container">
    <side-bar/>
    <task-box/>
</div>
</template>

<script>
import SideBar from "./side-bar.vue"
import TaskBox from  "./task-box.vue"
export default {
    name : "MainContainer",
    components :{
        SideBar,
        TaskBox,
    },
}
</script>

<style>

</style>