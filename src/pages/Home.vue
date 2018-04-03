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
            <div id="signature-wrapper" style="width: 100%; max-width: 500px; font-family: 'Arial', sans-serif; display: inline-block; margin-top: 20px;">
              <table width="60" align="left" border="0" cellpadding="0" cellspacing="0">
                <tbody>
                <tr>
                  <td align="left" style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; margin: 0px; font-size: 11px;">
                    <a href="https://www.adapterdigital.com" target="_blank">
                      <img src="../assets/images/logo.gif" style="max-width: 100%; height: auto;">
                    </a>
                  </td>
                </tr>
                </tbody>
              </table>
              <table width="200" align="left" border="0" cellpadding="0" cellspacing="0" style="color: rgb(0, 0, 0); font-size: 13px; letter-spacing: normal; margin-bottom: 30px;">
                <tbody>
                <tr>
                  <td align="left" style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; margin: 0px; font-size: 11px; padding-left: 10px; padding-right: 10px; line-height: 15px;">
                    <b style="font-size: medium;">{{fields.name}}</b><br>
                    <span>{{fields.position}}</span><br>
                    <span><a :href="`mailto:${fields.email}`" target="_blank" style="color: rgb(255, 100, 105); text-decoration: none;">{{fields.email}}</a></span><br>
                    <span v-show="fields.mobile">mobile#&nbsp;<a :href="`tel:${fields.mobile}`" target="_blank" style="color: rgb(255, 100, 105); text-decoration: none;">{{fields.mobile}}</a></span>
                  </td>
                </tr>
                </tbody>
              </table>
              <table width="200" align="left" border="0" cellpadding="0" cellspacing="0" style="color: rgb(0, 0, 0); font-size: 13px; letter-spacing: normal; padding-top: 17px;">
                <tbody>
                  <tr>
                    <td align="left" style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; margin: 0px; font-size: 11px; line-height: 16.5px;">
                      <b style="font-size: medium;"></b><br>
                      <span>{{fields.address}}</span><br>
                      <span v-show="fields.phone">phone#&nbsp;<a :href="`tel:${fields.phone}`" target="_blank" style="color: rgb(255, 100, 105); text-decoration: none;">{{fields.phone}}</a></span>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
          <div v-show="config.version == 2" style="height: 350px; padding: 80px 40px;">
            <div id="signature-wrapper" style="width: 100%; max-width: 500px; font-family: 'Arial', sans-serif; display: inline-block; margin-top: 20px;">
              <table width="100%" align="left" border="0" cellpadding="0" cellspacing="0" style="color: rgb(0, 0, 0); font-size: 13px; letter-spacing: normal; margin-bottom: 30px;">
                <tbody>
                <tr>
                  <td align="left" style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; margin: 0px; font-size: 11px; padding-left: 10px; padding-right: 10px; line-height: 15px;">
                    <strong style="font-size: 18px;">{{fields.name}}</strong>
                  </td>
                </tr>
                <tr>
                  <td align="left" style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; margin: 0px; font-size: 11px; padding-left: 10px; padding-right: 10px; line-height: 15px;">
                    <span style="font-size: 14px;">{{fields.position}}</span><br>
                  </td>
                </tr>
                <tr>
                  <td align="left" style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; margin: 0px; font-size: 11px; padding-top: 10px; padding-left: 10px; padding-right: 10px; line-height: 15px;">
                    <a href="https://www.adapterdigital.com" target="_blank">
                      <img src="../assets/images/adapter.gif" style="max-height: 50px; height: auto;">
                    </a>
                  </td>
                </tr>
                <tr>
                  <td align="left" style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; margin: 0px; font-size: 11px; padding-top: 10px; padding-left: 10px; padding-right: 10px; line-height: 16.5px;">
                    <span style="font-size: 12px;">{{fields.address}}</span>
                  </td>
                </tr>
                <tr>
                  <td align="left" style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; margin: 0px; font-size: 11px; padding-left: 10px; padding-right: 10px; line-height: 16.5px;">
                    <span v-show="fields.phone" style="font-size: 12px;">Company Line#&nbsp;<a :href="`tel:${fields.phone}`" target="_blank" style="color: rgb(255, 100, 105); text-decoration: none;">{{fields.phone}}</a></span>
                  </td>
                </tr>
                <tr>
                  <td align="left" style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; margin: 0px; font-size: 11px; padding-left: 10px; padding-right: 10px; line-height: 16.5px;">
                    <span v-show="fields.mobile" style="font-size: 12px;">Mobile#&nbsp;<a :href="`tel:${fields.mobile}`" target="_blank" style="color: rgb(255, 100, 105); text-decoration: none;">{{fields.mobile}}</a></span>
                  </td>
                </tr>
                <tr>
                  <td align="left" style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; margin: 0px; font-size: 11px; padding-left: 10px; padding-right: 10px; line-height: 16.5px;">
                    <a :href="`http://${fields.website}`" target="_blank">
                      {{fields.website}}
                    </a>
                  </td>
                </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
      <div class="alert alert-light" role="alert">{{config.message}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'home',
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
      console.log(version);
      this.config.version = version;
    },
  }
};
</script>