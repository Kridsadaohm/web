<template>
    <div>
        <b-container class="topbar w-100" fluid>
            <b-row block>
                <b-col cols="12" sm="9">
                    <b-navbar-brand href="#">
                        <Logo />
                        Indoor Personal Tracking
                    </b-navbar-brand>
                </b-col>
                <b-col cols="12" sm="3">
                    <b-form-input size="sm" class="w-100 mr-sm-2 search-top" placeholder="Search"></b-form-input>
                </b-col>
            </b-row>
        </b-container>
        <Nuxt />
        <b-modal id="frist_zone_modal" hide-footer size="xl">
            <template #modal-header="{ close }">
                <!-- Emulate built in modal header close button action -->
                <b-button size="sm" variant="outline-secondary" @click="close()"><b-icon icon="chevron-left"></b-icon> Back</b-button>
            </template>

            <h2 class="text-center">Frist Zone</h2>

            <b-tabs pills content-class="mt-3" align="center">
                <b-tab title="Visaul" active><p>I'm the Visaul</p></b-tab>
                <b-tab title="Daily Population Graph"><p>I'm the Daily Population Graph</p></b-tab>
                <b-tab title="Check-in information"><p>I'm a Check-in information</p></b-tab>
            </b-tabs>
        </b-modal>
        <b-modal id="datetime-modal" hide-footer>
            <template #modal-header="{ close }">
                <!-- Emulate built in modal header close button action -->
                <b-button size="sm" variant="outline-secondary" @click="close()"> <b-icon icon="chevron-left"></b-icon> Cancel </b-button>
            </template>
            <label>Time</label>

            <b-row class="mb-2 text-center">
                <b-col><b-form-timepicker v-model="value" locale="th"></b-form-timepicker></b-col>
                <b-col cols="1">to</b-col>
                <b-col><b-form-timepicker v-model="value" locale="th"></b-form-timepicker></b-col>
            </b-row>

            <label>Date</label>
            <b-row class="mb-2 text-center">
                <b-col>
                    <b-form-datepicker id="example-datepicker" v-model="value" class="mb-2"></b-form-datepicker>
                </b-col>
            </b-row>
            <b-button class="mt-3 set-time-btn btn-lg" block @click="$bvModal.hide('datetime-modal')">Set Time</b-button>
        </b-modal>
    </div>
</template>

<style>
    body {
        background: #f4f7fc;
    }
    .topbar {
        background: white;
    }
    .navbar-brand {
      color: black;
    }
    .search-top {
        border-radius: 50px;
        min-width: 250px;
        height: 40px;
        margin-top: 10px;
         margin-bottom: 10px;
    }
</style>
