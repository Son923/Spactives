<template>
  <div>
    <main id="mainContent" class="container-fluid">
      <div class="row">
        <div class="col-0 p-0 border-right sidebar mx-3 pr-3">
          <ManuSideBar />
        </div>
        
        <MasterDetailPage :textSampleData="masterDetailText[currentDisplayTabIndex]" />
      </div>
    </main>
    <BaseWarningMessage
      v-if="WarningMessageOpen"
      :text="WarningMessageText"
      @onWarningClose="handleWarningClose"
    />
  </div>
</template>

<script>
import CONSTANTS from "@/constants";
import MasterDetailPage from "@/components/MasterDetailPage";
import MasterDetailSideBarTab from "@/components/MasterDetailSideBarTab";
import BaseWarningMessage from "@/components/BaseWarningMessage";

import ManuSideBar from "@/components/ManuSideBar";

export default {
  name: "Manu",

  components: {
    MasterDetailPage,
    MasterDetailSideBarTab,
    BaseWarningMessage,
    ManuSideBar
  },

  data() {
    return {
      masterDetailText: [
        {
          id: 0,
          longDescription: "",
          orderDate: "",
          orderTotal: 0,
          shipTo: "",
          status: "",
          title: ""
        }
      ],
      currentDisplayTabIndex: 0,
      WarningMessageOpen: false,
      WarningMessageText: ""
    };
  },

  created() {
    this.fetchTextAssets();
  },

  methods: {
    fetchTextAssets() {
      fetch(CONSTANTS.ENDPOINT.MASTERDETAIL)
        .then(response => {
          if (!response.ok) {
            throw Error(response.statusText);
          }
          return response.json();
        })
        .then(result => {
          this.masterDetailText = result;
        })
        .catch(error => {
          this.WarningMessageOpen = true;
          this.WarningMessageText = `${CONSTANTS.ERROR_MESSAGE.MASTERDETAIL_GET} ${error}`;
        });
    },
    handleWarningClose() {
      this.WarningMessageOpen = false;
      this.WarningMessageText = "";
    },
    handleDisplayTabClick(id) {
      this.currentDisplayTabIndex = id;
    }
  }
};
</script>

<style scoped>
.sidebar {
  /* full height - footer height - navbar height */
  min-height: calc(100vh - 160px - 57px);
}
</style>
