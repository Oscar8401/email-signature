<template>
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
</template>

<script>
export default {
  name: 'vertical',
  props: {
    fields: Object,
  }
};
</script>