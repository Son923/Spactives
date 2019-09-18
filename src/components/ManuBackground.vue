<template>
<!-- <main id="mainContent"> -->
    <div id="mainContent" class="col">
        <div class="row heading"></div>
        <div class="row heading-title">
            <div>
                <img id="profile-picture" src="@/assets/profile.png" alt="">
            </div>
            <div class="manu-title">
                <h1 class="mb-4 company-name">{{textSampleData.title}}<img src="@/assets/svg/Checker.svg" alt="" style="margin-left: 15px;"></h1>
                <p style="font-weight: 600;">CMT Garment Manufacturer</p>
                <p><img src="@/assets/svg/Marker.svg" alt="" style="margin-right: 13px;"> Can tho province, Viet Nam</p>
            </div>
            <div class="contact-group">
                <b-button class="contact-buttons" variant="outline-light">
                    <p style="color: #7291F7"><img src="@/assets/svg/Message.svg" alt="" style="margin-right: 10px;">Message</p>
                </b-button>
                <b-button class="contact-buttons" variant="primary">
                    <p style="color: white"><img src="@/assets/svg/Quotation.svg" alt="" style="margin-right: 10px;">Request for Quotation</p>
                </b-button>    
                <b-button class="contact-buttons" variant="outline-light">
                    <p style="color: #777777"><img src="@/assets/svg/Bookmark.svg" alt="" style="margin-right: 10px;">Bookmark</p>
                </b-button>       
            </div>
        </div>
        <div class="row info">
            <b-col class="grid">
                <div class="service">
                    <p class="title">Service Provide</p>
                    <div id="info-labels">
                        <div class="label"><p>Design</p></div>
                        <div class="label"><p>Print</p></div>
                        <div class="label"><p>Shipping</p></div>
                    </div>
                </div>
                <div class="service">
                    <p class="title">Rating</p>
                    <b-row class="grid">
                        <b-col class="grid">
                            <p>Positive Customer Ratings</p>
                            <p class="stat">9.5/10</p>
                        </b-col>
                        <b-col class="grid">
                            <p>Total Transactions</p>
                            <p class="stat">+1 Million</p>
                        </b-col>
                        
                    </b-row>
                </div>
            </b-col>

            <b-col class="grid about">
                <p class="title">About {{textSampleData.title}}</p>
                <p>Backing startup churn rate ecosystem pivot lean startup vesting period. Social media startup paradigm shift ecosystem interaction design rockstar branding stealth assets channels influencer analytics. Stock paradigm shift niche market hypotheses bandwidth scrum project buzz strategy return on investment facebook holy grail. User experience A/B testing interaction design rockstar beta.</p>
            </b-col>

        </div>
        <div class="row">
            <div class="col-12 mt-3">
                <b-breadcrumb class="bg-white">
                    <b-breadcrumb-item href="#">Master Detail</b-breadcrumb-item>
                    <b-breadcrumb-item active>{{textSampleData.title}}</b-breadcrumb-item>
                </b-breadcrumb>
            </div>
        </div>
    </div>
<!-- </main> -->
</template>

<script>
export default {
  name: "ManuBackground",
  props: {
    textSampleData: {
      type: Object,
      required: true,
      validator: function(value) {
        return (
          value.id !== undefined &&
          value.longDescription !== undefined &&
          value.orderDate !== undefined &&
          value.orderTotal !== undefined &&
          value.shipTo !== undefined &&
          value.status !== undefined &&
          value.title !== undefined
        );
      }
    }
  }
};
</script>

<style scoped>
#mainContent {
    margin-bottom: 30px;
    background-color: white;
    border-radius: 8px;
}
.title {
  font-weight: 700;
  margin-bottom: 0;
  font-size: 20px;
  padding-bottom: 20px;
  color: #444444;
}

.breadCrumbLink {
  color: #025fce;
}
.heading {
    /* background-color: wheat; */
  /* padding-top: 18em; */
  background-image: url("../assets/cover.png");
  height: 27vh;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
  min-height: 251px;
}
.heading-title {
    margin-top: 27px;
    display: grid;
    grid-template-columns: 300px 2fr 2fr;
}
.company-name {
    display: flex;
    flex-wrap: nowrap;
    align-items: center;
}
#profile-picture {
    left: 80px;
    position: absolute;
    border: solid 1px white;
    top: 170px;
}
.manu-title {
    top: -30px;
}
.contact-group {
    top: -20px;
    justify-content: center;
    display: flex;
    flex-wrap: wrap;
}
.contact-buttons {
    height: 40px;
}
.info {
    padding-left: 80px;
    padding-right: 144px;
    margin-top: 25px;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
}
.service {
    margin-bottom: 50px;
}
.stat {
    color: #287D3C;
    font-weight: 700;
}
#info-labels {
    display: flex;
}
.label {
    border: 1px solid #D9D9D9;
    border-radius: 4px;
    height: 40px;
    margin-right: 10px;
    padding: 5px 20px;
    align-items: center;
    text-align: center;
    box-sizing: border-box;
}
@media only screen and (max-width: 1136px) {
   #profile-picture {
    left: unset;
    right: 50%;
    top: 270px;
    transform: translate(50%,-50%);
  }
  .heading-title {
    margin-top: 0;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    text-align: center;
  }
  .company-name {
    display: block;
  }
  .info {
    margin-top: -45px;
    padding-left: 40px;
    padding-right: 40px;
  }
}
@media only screen and (max-width: 820px) {
  .info > .grid:first-child {
    flex: 0 0 100%;
  }
}
</style>