<template lang="html">
    <section>
        <new-rocket-form
            :addRocket="addRocket">
        </new-rocket-form>
        <rocket-list 
            :removeRocket="removeRocket"
            :rockets="rockets">
        </rocket-list>
    </section>
</template>

<script>
import { mapGetters } from 'vuex';

import NewRocketForm from '@/components/NewRocketForm'
import RocketList from '@/components/RocketList'

export default {
    name: 'rockets',
    components: {
        NewRocketForm,
        RocketList,
    },
    computed: mapGetters(['rockets']),
    async mounted() {
        this.$store.dispatch('getRockets');
    },

}
</script>

<style lang="css">

</style>

