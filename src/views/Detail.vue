<template>
    <div class="detail">
        <DetailBanner></DetailBanner>
        <DetailHeader></DetailHeader>
        <div class="content">
            <DetailList :list="list"></DetailList>
        </div>
    </div>
</template>

<script>
import DetailBanner from '@/components/DetailBanner'
import DetailHeader from '@/components/DetailHeader'
import DetailList from '@/components/DetailList'

export default {
    components: {
        DetailBanner,
        DetailHeader,
        DetailList
    },
    data () {
        return {
            list: [{
                title: 'Adult Ticket',
                children: [{
                    title: 'Adult Ticket for Opera',
                    children: [{
                        title: 'Adult Ticket for Opera - Las Miserables'
                    }]
                }]
            },
            {
                title: 'Student Ticket'
            },
            {
                title: 'Children Ticket'
            }, 
            {
                title: 'Special Discount Ticket'
            }]
        }
    }
}
</script>

<style lang="stylus" scoped>
    .content
        height 50rem
</style>
