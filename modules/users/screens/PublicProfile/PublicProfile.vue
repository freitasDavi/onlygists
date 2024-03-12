<script setup lang="ts">
import PublicHeadline from '@/modules/users/components/PublicHeadline/PublicHeadline.vue';
import WidgetGroup from '@/modules/reports/components/Widget/Group/Group.vue'
import WidgetGroupLoader from '@/modules/reports/components/Widget/Group/Loader.vue'
import WidgetCondensed from '@/modules/reports/components/Widget/Condensed/Condensed.vue'
import GistCardGroup from '@/modules/gists/components/Card/Group/Group.vue';
import GistCardLoader from '@/modules/gists/components/Card/Group/Loader.vue';
import GistCardItem from '@/modules/gists/components/Card/Item/Item.vue';

const route = useRoute()
const router = useRouter()

const handlerNavigateToDetail = (id: string) => {
    const { username } = route.params

    router.push(`/${username}/gist/${id}`)
}

</script>

<template>
    <PublicHeadline />
    <WidgetGroup>
        <WidgetGroupLoader :loading="false" :amount="3">
            <WidgetCondensed :value="10" label="Gists do total" />
            <WidgetCondensed :value="5" label="Gists do gratuitos" />
            <WidgetCondensed :value="5" label="Gists do pagos" />
        </WidgetGroupLoader>
    </WidgetGroup>
    <WidgetDefault title="Todos os Gists">
        <GistCardGroup>
            <GistCardLoader :loading="false">
                <GistCardItem 
                    @tap="handlerNavigateToDetail"
                    id="123"
                    title="useCurrentUser"
                    description="Hook para controlar a **store** do usuário"
                    :price="10"
                    lang="typescript"
                />
                <GistCardItem 
                    @tap="handlerNavigateToDetail"
                    id="123"
                    title="useCurrentUser"
                    description="Hook para controlar a **store** do usuário"
                    :price="10"
                    lang="typescript"
                />
                <GistCardItem 
                    @tap="handlerNavigateToDetail"
                    id="123"
                    title="useCurrentUser"
                    description="Hook para controlar a **store** do usuário"
                    :price="10"
                    lang="typescript"
                />
                <GistCardItem 
                    @tap="handlerNavigateToDetail"
                    id="123"
                    title="useCurrentUser"
                    description="Hook para controlar a **store** do usuário"
                    :price="10"
                    lang="typescript"
                />
            </GistCardLoader>
        </GistCardGroup>
    </WidgetDefault>
    
</template>