<script setup lang="ts">
import PublicHeadline from '@/modules/users/components/PublicHeadline/PublicHeadline.vue';
import WidgetGroup from '@/modules/reports/components/Widget/Group/Group.vue'
import WidgetGroupLoader from '@/modules/reports/components/Widget/Group/Loader.vue'
import WidgetCondensed from '@/modules/reports/components/Widget/Condensed/Condensed.vue'

</script>

<template>
    <PublicHeadline />
    <WidgetGroup>
        <WidgetGroupLoader :loading="true" :amount="3">
            <WidgetCondensed :value="10" label="Gists do total" />
            <WidgetCondensed :value="5" label="Gists do gratuitos" />
            <WidgetCondensed :value="5" label="Gists do pagos" />
        </WidgetGroupLoader>
    </WidgetGroup>
    <WidgetDefault title="Todos os Gists">gists</WidgetDefault>
</template>