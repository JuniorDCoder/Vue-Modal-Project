<template>
    <div class="backdrop">
        <div class="modal">
            <h1>Modal Title</h1>
            <p>Modal Content</p>
            <button @click="ToggleClick">Cancel</button>
        </div>
    </div>
</template>

<script>
export default{
    props: {
        isClicked: Boolean,
        ToggleClick: {
            Function, 
            required: true
        }
    },
    methods: {
        hideModal(){
            this.isClicked = !this.isClicked
        }
    }
}
</script>

<style scoped>
    .modal{
        width: 400px;
        padding: 20px;
        margin: 200px auto;
        background: white;
        border-radius: 10px;
    }
    .backdrop{
        top: 0;
        position: fixed;
        background: rgba(0,0,0,0.5);
        width: 100%;
        height: 100%;
    }
    h1{
        color: #03cfb4;
        border: none;
        padding: 0;
    }
</style>