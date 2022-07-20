<template>
    <div class="card">
        <div class="card__inner" :class="{'is-filpped': isFilpped}" @click="onToggleFilpCard"  >
            <div class="card__face card__face--front" >
                <div class="card__content">
                    front
                </div>
            </div>
            <div class="card__face card__face--back">
                <div class="card__content">
                    back
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    datat() {
        return {
            isFlipped: false,
        }
    },
    methods: {
        onToggleFilpCard() {
            this.isFlipped = !this.isFlipped;
        },
    }
}
</script>
<style lang="css" scoped>
    .card {
        display: inline-block;
        margin-right: 1.6rem;
        margin-bottom: 1.6rem;
        width: 9rem;
        height: 12rem;
    }
    .card__inner {
        width: 100%;
        height: 100%;
        transition: transform 2s;
        transform-style: preserve-3d;
        cursor: pointer;
        position: relative;
        z-index: 1;
    }
    .card__inner.is-filpped {
        transform: rotateY(-180deg);
    }
    .card__face {
        position: absolute;
        width: 100%;
        height: 100%;
        backface-visibility: hidden;
        overflow: hidden;
        border-radius: 1.6rem;
        padding: 1.6rem;
        box-shadow: 0 3px 10px 3px rgba(0, 0, 0, .2);
    }
    .card__face--back {
        background-color: var(--light);
        transform: rotateY(-180deg);
    }
</style>