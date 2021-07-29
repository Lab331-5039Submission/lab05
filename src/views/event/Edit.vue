<template>
    <p>Edit data here</p>
    <button @click="edit">Edit data</button>
</template>

<script>
export default {
    props: ['event'],
    inject: ['GStore'],
    methods: {
        edit() {
            this.GStore.flashMessage = 'Data has been updated in ' + this.event.title
            setTimeout(() => {
                this.GStore.flashMessage = ''
            }, 3000)
            this.$router.push({
                name: 'EventDetails',
                params: { id: this.event.id },
            })
        },
    },
}
</script>