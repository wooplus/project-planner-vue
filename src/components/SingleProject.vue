<template>
    <div class="title" @click="showDetail=!showDetail">
        <h2>
        {{project.title}}
        </h2>
        <p v-if="showDetail">{{project.detail}}</p>
    </div>
</template>

<script>
export default {
    props:['project'],
    data() {
        return{
            showDetail:false,
        }
    }
}
</script>

<style>
    .title {
        padding:20px;
        background-color: #f2f2f2;
        margin: 20px;
        cursor: pointer;
    }
    h2 {
        color: indianred;
    }
</style>