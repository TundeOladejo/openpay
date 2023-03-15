<script>
export default {
    data() {
        return {
            navigationList: [
                { icon: "house-door", name: "Dashboard" },
                { icon: "receipt", name: "Invoices" },
                { icon: "chat-dots", name: "Messages", notification: 5 },
                { icon: "credit-card", name: "My Wallets" },
                { icon: "pie-chart", name: "Activity" },
                { icon: "clipboard-data", name: "Analytics" }
            ],
            otherList: [
                { icon: "exclamation-circle", name: "Get Help" },
                { icon: "gear", name: "Settings" },
            ],
            extraClass: false,
            isExtraClass: '',
            isActive: '',
            active: false,
            showNavbar: true,
            window: {
                width: 0,
                height: 0
            },
        }
    },
    methods: {
        handleResize() {
            this.window.width = window.innerWidth;
            this.window.height = window.innerHeight;

        },
        respNav() {
            if (this.window.width <= 767) {
                this.isActive = true;
                this.extraClass = true;
            }
            if (this.window.width >= 768) {
                this.isActive = false;
                this.extraClass = false;
            }
        },
        showMobilemenu() {
            this.active = !this.active;
            this.extraClass = !this.extraClass
        },

    },
    mounted() {
        window.addEventListener('resize', this.handleResize);
        this.handleResize();
        this.respNav();

    },
    destroyed() {
        window.removeEventListener('resize', this.handleResize);
    },
}
</script>
<template>
    <aside class="menu">
        <div class="is-flex is-3 is-justify-content-space-between navbar-brand px-5">
            <span class="is-flex is-align-items-center">
                <figure class="image is-24x24 mr-3">
                    <img src="../assets/open.svg" alt="openpay logo">
                </figure>
                <span class="has-text-weight-bold">OpenPay</span>
            </span>

            <a role="button" id="burger" class="navbar-burger" :class="active ? 'is-active' : ''" @click="showMobilemenu"
                aria-label="menu" aria-expanded="false" data-target="navbarBasicExample">
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
            </a>
        </div>
        <div id="navbarBasicExample" class="navigation-items py-5" :class="active ? 'is-active' : ''">
            <ul class="menu-list">
                <li v-for="(item, index) in navigationList" :key="index" class="navigationList">
                    <a class="is-flex is-flex-wrap-wrap is-justify-content-space-between py-4">
                        <span><i class="bi pr-3" :class="`bi-` + item.icon"></i>{{ item.name }}</span>
                        <span v-if="item.notification != null" class="tag is-rounded ml-3"
                            style="background-color: #0177FB; color: white">{{ item.notification }}</span>
                    </a>
                </li>
            </ul>
            <ul class="menu-list">
                <li v-for="(item, index) in otherList" :key="index" class="navigationList">
                    <a class="py-4 pl-4">
                        <span><i class="bi pr-3" :class="`bi-` + item.icon"></i>{{ item.name }}</span>
                        <span v-if="item.notification != null" class="tag is-rounded pl-2"
                            style="background-color: #0177FB;, color: white">{{ item.notification }}</span>
                    </a>
                </li>
            </ul>
            <!-- </div> -->
        </div>
    </aside>
</template>

<style lang="scss">
.navigationList {
    padding: 0px 16px;

    &:hover {
        border-left: 3px solid #0177FD;
    }

    i {
        color: #A4B4CB;
    }

    &:hover i {
        color: #0177FD;
    }

    & a {
        border-radius: 4px;
        color: #131635;
        font-weight: 500;

        &:hover {
            background-color: #E5F1FF;
            color: #0177FD;
        }
    }
}
</style>