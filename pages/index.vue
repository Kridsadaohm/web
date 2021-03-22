<template>
    <div>
        <b-container fluid>
   
                <b-row>
                    <b-col md="9">
                        <div class="main-content">
                        <b-row>
                            <b-col md="12">
                                <h2>Floor Overview</h2>
                            </b-col>
                        </b-row>
                        <b-row>
                            <b-col md="9">
                               
                                <b-tabs class="d-none d-md-flex" v-model="tabIndex" pills vertical>
                                    <b-tab @click="tabIndex--" class="text-center" title="chevron-up">
                                        <template #title><b-icon icon="chevron-up"></b-icon> </template>
                                    </b-tab>
                                    <b-tab class="text-center" title="F6"><b-card-text>F6</b-card-text></b-tab>
                                    <b-tab class="text-center" title="F5"><b-card-text>F5</b-card-text></b-tab>
                                    <b-tab class="text-center" title="F4"><b-card-text>F4</b-card-text></b-tab>
                                    <b-tab class="text-center" title="F3"><b-card-text>F3</b-card-text></b-tab>
                                    <b-tab class="text-center" title="F2" active>
                                        <div v-b-modal="'frist_zone_modal'" class="total-user-h" style="top: 30%; right: 70%;">{{ total_frist_zone }} <b-icon icon="people-fill"></b-icon></div>

                                        <div class="total-user-h" style="top: 17%; right: 20%;">{{ total_second_zone }} <b-icon icon="people-fill"></b-icon></div>

                                        <div class="total-user-h" style="top: 65%; right: 40%;">{{ total_third_zone }} <b-icon icon="people-fill"></b-icon></div>

                                        <img class="w-100" src="~/assets/img/f2.jpeg" />

                                        
                                    </b-tab>
                                    <b-tab class="text-center" title="G"><b-card-text>G</b-card-text></b-tab>
                                    <b-tab @click="tabIndex++" class="text-center" title="chevron-down">
                                        <template #title><b-icon icon="chevron-down"></b-icon> </template>
                                    </b-tab>
                                </b-tabs>
                                <b-tabs class="d-block d-md-none" v-model="tabIndex" pills>
                                    <b-tab @click="tabIndex--" class="text-center" title="chevron-left">
                                        <template #title><b-icon icon="chevron-left"></b-icon> </template>
                                    </b-tab>
                                    <b-tab class="text-center" title="F6"><b-card-text>F6</b-card-text></b-tab>
                                    <b-tab class="text-center" title="F5"><b-card-text>F5</b-card-text></b-tab>
                                    <b-tab class="text-center" title="F4"><b-card-text>F4</b-card-text></b-tab>
                                    <b-tab class="text-center" title="F3"><b-card-text>F3</b-card-text></b-tab>
                                    <b-tab class="text-center" title="F2" active>
                                        <div v-b-modal="'frist_zone_modal'" class="total-user-h" style="top: 30%; right: 70%;">{{ total_frist_zone }} <b-icon icon="people-fill"></b-icon></div>

                                        <div class="total-user-h" style="top: 17%; right: 20%;">{{ total_second_zone }} <b-icon icon="people-fill"></b-icon></div>

                                        <div class="total-user-h" style="top: 65%; right: 40%;">{{ total_third_zone }} <b-icon icon="people-fill"></b-icon></div>

                                        <img class="w-100 pb-4 pt-4" src="~/assets/img/f2.jpeg" />

                                       
                                    </b-tab>
                                    <b-tab class="text-center" title="G"><b-card-text>G</b-card-text></b-tab>
                                    <b-tab @click="tabIndex++" class="text-center" title="chevron-right">
                                        <template #title><b-icon icon="chevron-right"></b-icon> </template>
                                    </b-tab>
                                </b-tabs>
                            </b-col>
                          
                            <b-col md="3">
                                <b-table class="w-100" hover :items="items" :fields="fields"></b-table>
                            </b-col>
                        </b-row>
                        </div>
                    </b-col>
                    <b-col md="3" class="main-sidebar">
                        <div class="side-box text-center">
                            <h1>18:05:12</h1>
                            <b-button v-b-modal="'datetime-modal'" class="w-100 btn-primary">Start set time</b-button>
                            <!-- <b-button v-b-modal="'datetime-modal'" class="w-100 btn-danger">Back to current Time</b-button> -->
                            Tuesday, 5 January 2021
                          
                        </div>
                        <div class="side-box">
                            <b-row>
                                <b-col md="7">
                                    Current population<br />
                                    <span class="text-success">1.8% <b-icon icon="arrow-up"></b-icon> </span> last peak
                                </b-col>
                                <b-col class="text-right" md="5">
                                    <h1>1,242</h1>
                                </b-col>
                            </b-row>
                            <hr />
                            <b-row>
                                <b-col md="7">
                                    Daily Maximum peak
                                </b-col>
                                <b-col class="text-right" md="5">
                                    1,455
                                </b-col>
                                <b-col md="7">
                                    Daily Minimun peak
                                </b-col>
                                <b-col class="text-right" md="5">
                                    430
                                </b-col>
                            </b-row>
 <hr />
                              <b-button size="sm" class="btn-light my-2 my-sm-0" type="submit">Logout</b-button>
                        </div>
                    </b-col>
                </b-row>
          
        </b-container>
    </div>
</template>

<script>
    export default {
        layout: "topbar",
        data() {
            return {
                total_frist_zone: 88,
                total_second_zone: 42,
                total_third_zone: 35,
                tabIndex: 1,
                fields: [
                    {
                        key: "floor",
                        label: "Floor",
                    },
                    {
                        key: "percentage",
                        label: "Percentage",
                    },
                    {
                        key: "population",
                        label: "Population",
                    },
                ],
                items: [
                    { floor: "F6", percentage: "21%", population: "255" },
                    { floor: "F5", percentage: "22%", population: "264" },
                    { floor: "F4", percentage: "6%", population: "85" },
                    { floor: "F3", percentage: "18%", population: "211" },
                    { floor: "F2", percentage: "20%", population: "242" },
                    { floor: "G", percentage: "15%", population: "185" },
                ],
            };
        },
    };
</script>

<style>
    .total-user-h {
        display: inline-block;
        position: absolute;
        z-index: 2;
        font-size: 28px;
    }
    .nav-pills .nav-link {
        color: black;
        padding: 15px;
    }
    .set-time-btn {
        background: #0058ff !important;
        color: white;
    }
    .wrapper {
        padding: 10px;
    }
    .main-content {
        background: white;
        margin-top:15px;
        padding: 15px 10px;
    }
    .main-sidebar {
        margin-top:15px;
    }
    .side-box {
        background: white;
        padding: 20px;
        margin-bottom: 20px;
    }
    .table th,
    .table td {
        padding: 0.3rem;
        vertical-align: top;
        border-top: 1px solid #f4f7fb;
    }
    .btn-danger {
        background: red;
        font-size: 22px;
    }
    .btn-primary {
        background: #0058ff !important;
        font-size: 22px;
    }
    .selecter-floor-btn {
        border: none;
        width: 100%;
        display: block;
        max-width: 50px;
        margin: 20px 0px;
        color: #000;
    }
    .selecter-floor-btn.active {
        background: #0058ff !important;
        border: none;
        width: 100%;
        display: block;
        max-width: 50px;
        margin: 20px 0px;
        color: white !important;
    }
    .vcenter-item {
        display: block;
        align-items: center;
        text-align: center;
    }
    @media only screen and (max-width: 600px) {
  .nav-pills .nav-link {
 
    padding: 5px;
}
}
</style>
