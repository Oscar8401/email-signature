<template>
  <div class="row">
    <div class="col-md-5">
      <div class="jumbotron">
        <form>
          <div class="form-group row">
            <label class="col-sm-3 col-form-label">Name</label>
            <div class="col-sm-9">
              <input class="form-control" type="text" v-model="fields.name" />
            </div>
          </div>
          <div class="form-group row">
            <label class="col-sm-3 col-form-label">Position</label>
            <div class="col-sm-9">
              <input class="form-control" type="text" v-model="fields.position" />
            </div>
          </div>
          <div class="form-group row">
            <label class="col-sm-3 col-form-label">Location</label>
            <div class="col-sm-9">
              <input class="form-control" type="text" v-model="fields.address" />
            </div>
          </div>
          <div class="form-group row">
            <label class="col-sm-3 col-form-label">Email</label>
            <div class="col-sm-9">
              <input class="form-control" type="text" v-model="fields.email" />
            </div>
          </div>
          <div class="form-group row">
            <label class="col-sm-3 col-form-label">Mobile</label>
            <div class="col-sm-9">
              <input class="form-control" type="text" v-model="fields.mobile" />
            </div>
          </div>
          <div class="form-group row">
            <label class="col-sm-3 col-form-label">Phone</label>
            <div class="col-sm-9">
              <input class="form-control" type="text" v-model="fields.phone" />
            </div>
          </div>
          <div class="form-group row">
            <label class="col-sm-3 col-form-label">Website</label>
            <div class="col-sm-9">
              <input class="form-control" type="text" v-model="fields.website" />
            </div>
          </div>
        </form>
      </div>
    </div>
    <div class="col-md-7">
      <div class="card" >
        <div class="card-body">
          <div class="row">
            <div class="col-sm-12">
              <div class="btn-group btn-group-sm float-right" role="group" aria-label="Format Switcher">
                <button type="button" class="btn " :class="{ 'btn-primary': config.version === 1 }" @click.prevent="changeVerion(1)">Version 1</button>
                <button type="button" class="btn " :class="{ 'btn-primary': config.version === 2 }" @click.prevent="changeVerion(2)">Version 2</button>
              </div>
            </div>
          </div>
          <div v-show="config.version == 1" style="height: 350px; padding: 80px 40px;">
           <signature-horizontal :fields=fields />
          </div>
          <div v-show="config.version == 2" style="height: 350px; padding: 80px 40px;">
            <signature-vertical :fields=fields />
          </div>
        </div>
      </div>
      <div class="alert alert-light" role="alert">{{config.message}}</div>
    </div>
  </div>
</template>

<script>
import { Horizontal, Vertical } from '../components/index'

export default {
  name: 'home',
  components: {
    signatureHorizontal:Horizontal,
    signatureVertical:Vertical
	},
  data() {
    return {
      config:{
        version: 1,
        message:'Please copy the generated signature to Gmail setting to avoid wrong format.'
      },
      fields: {
        name: 'Eric Prom',
        position: 'Senior Developer',
        address: '33TH FLOOR, SUN TOWER B, BANGKOK THAILAND 10900',
        email: 'surasak@adapterdigital.com',
        mobile: '0888888888',
        phone: '026178320',
        website: 'www.adapterdigital.com',
      },
    };
  },
  methods: {
    changeVerion: function (version) {
      this.config.version = version;
    },
  }
};
</script>