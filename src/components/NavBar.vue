<template>
    <nav class="navbar ">
        <div class="container">
            
            <div class="nav-right" id="navbarNav">
                <ul class="navbar-nav">
                    <li :class="{ active: activeTab === 'home' }" @click="setActiveTab('home')">
                        <router-link class="nav-link active" aria-current="page" to="/">Home</router-link>
                    </li>
                    <li :class="{ active: activeTab === 'about' }" @click="setActiveTab('about')">
                        <router-link class="nav-link" to="/about">About</router-link>
                    </li>

                </ul>
            </div>
        </div>
    </nav>
</template>
  
<script>
export default {
    name: "Navbar",
    data() {
        return {
            activeTab: 'home'
        };
    },
    methods: {
        setActiveTab(tabName) {
            this.activeTab = tabName;
        }
    }
};
</script>
  
<style lang="scss" scoped>

</style>
  