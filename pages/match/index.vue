<template>
    <div class="bg-cover bg-gray-800" style="background-image:url(/images/bg/body-bg2.webp);">

        <HeaderSection/>

        <OffCanvasMobileMenu :class="{'show-mobile-menu' : navOpen}" @togglenav="navOpen = !navOpen" />

        <Breadcrumb :BreadcrumbTitle="BreadcrumbTitle" :BreadcrumbSubTitle="BreadcrumbSubTitle"/>

        <UpcomingMatches/>

        <CounterUp/>

        <ContactBanner :paddingTop="paddingTop"/>

        <Footer></Footer>

    </div>
</template>

<script>
import matchesData from '@/data/matches.json'
export default {
    components: {
        HeaderSection: () => import('@/components/HeaderSection'),
        OffCanvasMobileMenu: () => import('@/components/Header/OffCanvasMobileMenu'),
        Breadcrumb: () => import('@/components/Breadcrumb'),
        CounterUp: () => import('@/components/CounterUp'),
        ContactBanner: () => import('@/components/ContactBanner'),
        Footer: () => import('@/components/Footer'),
        UpcomingMatches: () => import('@/components/UpcomingMatches')
    },
    data() {
        return {
            matchesData,
            navOpen: false,
            BreadcrumbTitle: "Upcoming Match",
            BreadcrumbSubTitle: "Match",
            paddingTop: "pt-0"
        }
    },
}
</script>