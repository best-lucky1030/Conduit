<template>
  <div class="home-page">
    <div class="container page">
      <div class="row">
        <div class="col-md-9">
          <div class="feed-toggle">
            <ul class="nav nav-pills outline-active">
              <li class="nav-item">
                <a href="" @click.stop.prevent="selectedTab = 'YOUR_FEED'; filter = 'feed';" class="nav-link" :class="{ 'active': selectedTab == 'YOUR_FEED' }">Your Feed</a>
              </li>
              <li class="nav-item">
                <a href="" @click.stop.prevent="selectedTab = 'GLOBAL_FEED'; filter = '';" :class="{ 'nav-link': true, 'active': selectedTab == 'GLOBAL_FEED' }">
                  Global Feed
                </a>
              </li>
              <li v-if="selectedTab == 'TAG'" class="nav-item active">
                <a href="" class="nav-link active">
                  <i class="ion-pround"></i>{{currentTag}}
                </a>
              </li>
            </ul>
          </div>
        </div>

        <div class="col-md-3">
          <div class="sidebar">
            <p>Popular Tags</p>
            <div class="tag-list">
              <a href="" v-for="tag in tags" @click.stop.prevent="selectedTab = 'TAG'; currentTag=tag;  filter = 'tag=' + tag;" class="tag-default tag-pill">{{tag}}</a>
            </div>
          </div>
        </div>

      </div>

      <div class="footer">
        <img src="https://static.productionready.io/images/smiley-cyrus.jpg" class="homeBtn" />
      </div>
    </div>
  </div>
</template>

<script>
import Banner from '@/components/Banner';
import Feed from '@/components/Feed';
export default {

  components: {
    Banner,
    Feed,
  },
  data() {
    return {
      tags: [],
      currentTag: '',
      filter: '',
      selectedTab: 'GLOBAL_FEED'
    }
  },
}
</script>

<style>

.footer{
  position: static;
  width: 100%;
  left: 0px;
  bottom: 0px;
}

.homeBtn {
  display: flex;
  margin: auto;
}
</style>
