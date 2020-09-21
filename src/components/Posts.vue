<template>
    <div class="post-wrapper">
        <div v-bind:key="post.id" v-for="post in posts" class="post-container">
            <h3 class="post-title">{{ post.title }}</h3>
            <p class="post-date">{{ randomDate() }}</p>
            <!-- <p>{{ post.description }} </p> -->
            <div class="post-body"> {{ post.body }} </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'posts',
    props: [ "posts" ],

    methods: {
        addZero: function(value) {
            return (value < 10) ? `0${value}` : value
        },
        dateZero: function (date) {
            return (date === 0) ? date+=1 : date
        },
		randomDate: function() {
            let start = new Date('2019, 09, 01');
            let end = new Date();
            let date = new Date(start.getTime() + Math.random() * (end.getTime() - start.getTime()))
            return `Posted at: ${this.dateZero(date.getDay())} / ${this.dateZero(date.getMonth())} / ${date.getFullYear()} ${this.addZero(date.getHours())} : ${this.addZero(date.getMinutes())}`;
        }
	}
}
</script>

<style scoped>
.post-wrapper {
    margin-left: 30px;
    margin-right: 50px;
    margin-bottom: 45px;
    margin-top: 20px;
    color: #2e2a2aec;
}

.post-container {
    background-color:#DCDCDD;
    padding: 5px;
    padding-left: 33px;
    margin-top: 10px;
    margin-right: 50px;
    margin-left: 30px;
    border-radius: 5px;

}

.post-title {
    text-transform: uppercase;
    margin-bottom: 0;

}

.post-date {
    font-size: 13px;
    font-style: italic;
    margin-bottom: 15px;
    padding: 0;
    margin-top: 2px;
    color: #221a1a9f;
}

.post-body {
    padding-bottom: 15px;
}
</style>