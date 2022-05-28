<template>
    <div :class="typeClass">{{ typeTxt }}</div>
</template>

<script>

export default {
    name: 'TypeItem',
    props: {
        type: String
    },
    computed: {
        typeClass() {
            let t = 'type';
            switch(this.type){
                case '':
                    break;
                default:
                    break;
            }
            return t;
        },
        typeTxt() {
            let t = '';
            switch(this.type){
                case '':
                    break;
                default:
                    t = this.type;
                    break;
            }
            return t;
        }
    }
}
</script>

<style lang="scss" scoped>

.type {
    border: 1px solid;
    border-radius: 10px;
    margin: 0 5px;
    padding: 3px 5px;

    &-nomal {
        background-color: white;
    }
}

</style>