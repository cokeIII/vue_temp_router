<template>
    <div class="tab-monters">
        <div class="container">
            <div class="card shadow">
                <div class="card-body">
                    <h1>Tab Monters</h1>
                    <div class="monters" @click="tabDmg"></div>
                    <div v-if="tab">
                        <transition name="fade">
                            <div class="tabEf" style="transition-delay: 1.5s"></div>
                        </transition>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
// @ is an alias to /src
export default {
    name: 'tabMonters',
    components: {
    },
    data() {
        return {
            number: 0,
            tab: false,
        };
    },
    methods: {
        tabDmg() {
            this.tab = true
            setInterval(() => {
                 this.tab = false
            }, 1000)
        }
    }
}
</script>
<style>
.tabEf {
    background-image: url("~@/assets/tabEf.png");
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
    margin: auto;
    width: 350px;
    height: 300px;
    position: absolute;
    margin-top: -300px;
    margin-left: 300px;
}

.monters {
    background-image: url("~@/assets/poring.png");
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
    /* background-color: red; */
    margin: auto;
    width: 350px;
    height: 300px;
}
</style>