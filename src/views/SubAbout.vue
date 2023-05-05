<template lang="">
    <div >
        <li  class="about-link ">
          <router-link :to="{ name: 'about' }">Back</router-link>
        </li>
      <TabWrapper>
            <Tabs title="Tab1">
                <div>
                    <FetchApi />
                </div>

            </Tabs>
            <Tabs title="Tab2">
                <div>
                   <FetchApi />
                </div>

            </Tabs>
        </TabWrapper>
    </div>
</template>
<script>
    import Tabs from "../components/Tab.vue"; 
    import TabWrapper from "../components/TabWrapper.vue";
    import FetchApi from "../components/FetchApi.vue";
export default {
    name:"SubAbout",
    components:{
        TabWrapper,
        Tabs,
        FetchApi
    }
}
</script>
