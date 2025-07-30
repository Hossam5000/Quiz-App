<template>
    <div class="card">
        <img src="https://marvel-b1-cdn.bc0a.com/f00000000026007/resilienteducator.com/wp-content/uploads/2012/11/AdobeStock_60467600_cup.jpg"
            alt="card 1">
        <div class="card-text">
            <h2>math</h2>
            <p class="desc">3 questions</p>
        </div><!--./card-text-->
    </div><!--./card-->
</template>

<script setup>

</script>

<style scoped>
.card {
    width: 310px;

    margin: 0 20px 0 35px;
    border-radius: 2%;

    box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    cursor: pointer;
}

.card img {
    width: 100%;
    height: 190px;
    margin: 0;
}

.card .card-text {
    padding: 0 5px;
}

.card .card-text h2 {
    font-weight: bold;
}
</style>