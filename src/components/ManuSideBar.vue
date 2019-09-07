<template>
  <div>
      <main id="mainContent" class="text-center">
        <button
          id="Explore"
          class="list-group-item list-group-item-action styles.sidebarText"
          type="button"
        >
          <img class="" src="@/assets/explore.png" alt="Explore" />
        </button>
        <button
          id="Newsfeed"
          class="list-group-item list-group-item-action styles.sidebarText"
          type="button"
        >
          <img class="" src="@/assets/NewsFeed.svg" alt="Newsfeed" />
        </button>
        <button
          id="Marketplace"
          class="list-group-item list-group-item-action styles.sidebarText"
          type="button"
        >
          <img class="" src="@/assets/Marketplace.svg" alt="Marketplace" />
        </button>
        <button
          id="Request"
          class="list-group-item list-group-item-action styles.sidebarText"
          type="button"
        >
          <img class="" src="@/assets/Request.svg" alt="Request" />
        </button>
        <button
          id="Bookmark"
          class="list-group-item list-group-item-action styles.sidebarText"
          type="button"
        >
          <img class="" src="@/assets/Bookmark.svg" alt="Bookmark" />
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
button {
  border: 0px;
}

</style>