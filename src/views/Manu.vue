<template>
  <div>
    <main id="manuView" class="container-fluid border-top">
      <div class="row">
        <div class="col-0 border-right sidebar">
          <ManuSideBar />
        </div>
        <div class="col pl-4 pt-4">
          <ManuBackground :textSampleData="masterDetailText[currentDisplayTabIndex]" />
        </div>        
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
import BaseWarningMessage from "@/components/BaseWarningMessage";
import ManuSideBar from "@/components/ManuSideBar";
import ManuBackground from "@/components/ManuBackground";

export default {
  name: "Manu",

  components: {
    BaseWarningMessage,
    ManuSideBar,
    ManuBackground
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
#manuView {
  /* margin-top: 15px; */
  background-color: whitesmoke;
  /* border-top: solid 1px; */
}
.sidebar {
  /* full height - footer height - navbar height */
  min-height: calc(100vh - 160px - 57px);
  background-color: white;

}
</style>
