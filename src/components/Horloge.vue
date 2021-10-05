<template>
    <div class="horloge">
        <span class="hour">{{ hour }}:</span>
        <span class="mins">{{ mins }}:</span>
        <span class="secs">{{ secs }}</span>
    </div>
</template>

<script>
export default {
    data() {
        return {
            now: new Date(),
            intervalID: null,
        }
    },

    computed: {
        hour() {
            return (this.now.getHours() < 10 ? `0${this.now.getHours()}` : this.now.getHours())
        },
        mins() {
            return (this.now.getMinutes() < 10 ? `0${this.now.getMinutes()}` : this.now.getMinutes())
        },
        secs() {
            return (this.now.getSeconds() < 10 ? `0${this.now.getSeconds()}` : this.now.getSeconds())
        }
    },

    beforeMount() {
        this.intervalID = setInterval(() => {
            this.now = new Date()
        }, 1000)
    },
    beforeDestroy() {
        clearInterval(this.intervalID)
    }
}
</script>

<style>
    .horloge {
        text-align:center;
        font-size: 40px;
        color:goldenrod;
    }

</style>
