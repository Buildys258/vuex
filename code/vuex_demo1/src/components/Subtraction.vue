<template>
    <div>
        <!-- <h3>当前最新的count值为：{{count}}</h3> -->
        <h3>{{showNum}}</h3>
        <button @click="btnHandler1">-1</button>
        <button @click="btnHandler2">-N</button>
        <button @click="subAsync">-1 Async</button>
    </div>
</template>

<script>
import { mapState, mapMutations, mapActions, mapGetters } from 'vuex'


export default {
    data() {
        return {

        }
    },
    computed: {
        ...mapState(['count']),
        ...mapGetters(['showNum'])
    },
    methods: {
        //将mutations中的方法作为一个数组传进来
        ...mapMutations(['sub','subN']),
        //将actions中的方法作为一个数组传进来
        ...mapActions(['subAsync']),
        btnHandler1() {
            this.sub()
        },
        btnHandler2() {
            this.subN(3)
        },
    }
}
</script>
