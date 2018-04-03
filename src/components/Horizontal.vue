<template>
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
</template>

<script>
export default {
  name: 'horizontal',
  props: {
    fields: Object,
  }
};
</script>