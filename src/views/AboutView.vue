<template>
  <div class="about">

    <div class="about-tab">
      <TabWrapper>
        <Tabs title="Tab-1">
          <div class="slide-content">
            <div class="slide-top">
              <h3 class="slide-box1">Slide Box-1</h3>
              <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis qui odit quibusdam et aliquid
                voluptatum natus beatae, commodi rem saepe?
              </p>
              <div class="link"> <router-link :to="{ name: 'fetch' }">Card-slot</router-link></div>
            </div>
            <div class="slide">
              <div>
                <AboutSlider :slideData="slidedata1"></AboutSlider>
              </div>

            </div>
          </div>
        </Tabs>
        <Tabs title="Tab-2">

          <div class="slide-content">
            <div class="slide-top">
              <h3 class="slide-box1">Slide Box-2</h3>
              <p>
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis qui odit quibusdam et aliquid
                voluptatum natus beatae, commodi rem saepe?
              </p>
              <div class="link"> <router-link :to="{ name: 'subabout' }">Fetch-Api</router-link></div>
            </div>
            <div class="slide">
              <div>
                <AboutSlider :slideData="slidedata1"></AboutSlider>
              </div>

            </div>
          </div>
        </Tabs>

        <Tabs title="Tab-3">
          <Posts />
        </Tabs>
      </TabWrapper>
    </div>


  </div>
</template>
<script>
import SubAbout from './SubAbout.vue';
import Posts from '../components/Post.vue';
import Tabs from '../components/Tab.vue';
import TabWrapper from '../components/TabWrapper.vue';
import AboutSlider from '../components/AboutSlider.vue'
export default {
  components: {
    SubAbout,
    Tabs,
    TabWrapper,
    AboutSlider,
    Posts
  },
  data() {
    return {
      slidedata1: {
        img: new URL('@/assets/images/Group 4.png', import.meta.url).href,
        img1: new URL('@/assets/images/Group 3.png', import.meta.url).href,
      },
      slidedata2: {
        img: new URL('../assets/images/Group 4.png', import.meta.url).href,
      },
      slidedata3: {
        img: new URL('../assets/images/Group 3.png', import.meta.url).href,
      },
      slidedata4: {
        img: new URL('../assets/images/Group 4.png', import.meta.url).href,
      },
    }
  }
}
</script>
