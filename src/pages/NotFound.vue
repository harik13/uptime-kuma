<template>
    <div>
        <!-- Desktop header -->
        <header v-if="! $root.isMobile" class="d-flex flex-wrap justify-content-center py-3 mb-3 border-bottom">
            <router-link to="/" class="d-flex align-items-center mb-3 mb-md-0 me-md-auto text-dark text-decoration-none">
                <object class="bi me-2 ms-4" width="40" height="40" data="/icon.svg" />
                <span class="fs-4 title">Vconsol Eyes</span>
            </router-link>
        </header>

        <!-- Mobile header -->
        <header v-else class="d-flex flex-wrap justify-content-center pt-2 pb-2 mb-3">
            <router-link to="/dashboard" class="d-flex align-items-center text-dark text-decoration-none">
                <object class="bi" width="40" height="40" data="/icon.svg" />
                <span class="fs-4 title ms-2">Vconsol Eyes</span>
            </router-link>
        </header>

        <div class="content">
            <div>
                <strong>🐻 {{ $t("Page Not Found") }}</strong>
            </div>

            <div class="guide">
                {{ $t("Most likely causes:") }}
                <ul>
                    <li>{{ $t("The resource is no longer available.") }}</li>
                    <li>{{ $t("There might be a typing error in the address.") }}</li>
                </ul>

                {{ $t("What you can try:") }}<br />
                <ul>
                    <li>{{ $t("Retype the address.") }}</li>
                    <li><a href="#" class="go-back" @click="goBack()">{{ $t("Go back to the previous page.") }}</a></li>
                    <li><a href="/" class="go-back">{{ $t("Go back to home page.") }}</a></li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    async mounted() {

    },
    methods: {
        /**
         * Go back 1 in browser history
         * @returns {void}
         */
        goBack() {
            history.back();
        }
    }
};
</script>

<style scoped lang="scss">
@import "../assets/vars.scss";

.go-back {
    text-decoration: none;
    color: $primary !important;
}

.content {
    display: flex;
    justify-content: center;
    align-content: center;
    align-items: center;
    flex-direction: column;
    gap: 50px;
    padding-top: 30px;

    strong {
        font-size: 24px;
    }
}

.guide {
    max-width: 800px;
    font-size: 14px;
}

.title {
    font-weight: bold;
}

.dark {
    header {
        background-color: $dark-header-bg;
        border-bottom-color: $dark-header-bg !important;

        span {
            color: #f0f6fc;
        }
    }

    .bottom-nav {
        background-color: $dark-bg;
    }
}
</style>
