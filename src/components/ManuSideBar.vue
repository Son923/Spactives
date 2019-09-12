<template>
  <div>
      <main id="mainContent" class="text-center">
        <a class="navbar-brand" href="/">
          <img class="avatar" src="@/assets/image.png" alt="">
        </a>
        <button
          id="Explore"
          class="list-group-item list-group-item-action styles.sidebarText"
          type="button"
        >
          <img class="" src="@/assets/svg/Explore.svg" alt="Explore" />
        </button>
        <button
          id="Newsfeed"
          class="list-group-item list-group-item-action styles.sidebarText"
          type="button"
        >
          <img class="" src="@/assets/svg/NewsFeed.svg" alt="Newsfeed" />
        </button>
        <button
          id="Marketplace"
          class="list-group-item list-group-item-action styles.sidebarText"
          type="button"
        >
          <img class="" src="@/assets/svg/Marketplace.svg" alt="Marketplace" />
        </button>
        <button
          id="Request"
          class="list-group-item list-group-item-action styles.sidebarText"
          type="button"
        >
          <img class="" src="@/assets/svg/Request.svg" alt="Request" />
        </button>
        <button
          id="Bookmark"
          class="list-group-item list-group-item-action styles.sidebarText"
          type="button"
        >
          <img class="" src="@/assets/svg/Bookmark.svg" alt="Bookmark" />
        </button>
      </main>
  </div>
</template>

<script>
export default {
  name: "ManuSideBar",
}
</script>

<style scoped>
#mainContent {
  width: 75px;
  margin-top: 20px;
}
button {
  border: 0px;
}

.avatar {
  border-radius: 50%;
  position: relative;
  right: -10px;
}
</style>