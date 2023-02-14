<template>
    <JobCard 
        v-for="item in jobCardsData.slice((jobDataLength - 3), (jobDataLength))"
        v-bind:key="item.id"
        :name="item.company"
        :vacancy="item.name"
        :type="item.type"
        :location="item.location"
    />
</template>

<script>
import JobCard from '../components/JobCard.vue';

export default {
    name: "JobCards",
    props: {
        jobCardsData: JSON
    },
    data() {
        return {
            jobDataLength: Object.keys(this.jobCardsData).length
        }
    },
    components: {
        JobCard
    }
}
</script>

<style>

</style>