<script>
  const PayPalButton = paypal.Buttons.driver("vue", window.Vue);
  Vue.component("app", {
    template: `
      <paypal-buttons [props]="{
          createOrder: createOrder,
          onApprove: onApprove
      }"></paypal-buttons>
    `,
    components: {
      "paypal-buttons": PayPalButton,
    },
    computed: {
      createOrder: function (data, actions) {
        return actions.order.create({
          purchase_units: [
            {
              amount: {
                value: "0.01",
              },
            },
          ],
        });
      },
      onAuthorize: function (data, actions) {
        return actions.order.capture();
      },
    },
  });
  var vm = new Vue({
    el: "#container",
  });
</script>