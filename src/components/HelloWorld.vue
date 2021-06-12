<template>
  <v-card style="margin:50px; padding:20px">
    <v-text-field
      v-model="num_wacth"
      label="Outlined"
      outlined
      clearable
    ></v-text-field>
  </v-card>
</template>


<script>
export default {
  name: "HelloWorld",

  data: () => ({
    num_wacth: "",
    intervalid1: "",
    enviar: false,
    intervalid2: "",
    saveban: false
  }),
  watch: {
    num_wacth: function(new_num, old_num) {
      if (new_num != "" && new_num != old_num) {
        this.enviar = true;
        this.intervalid1 = setInterval(this.hola.bind(this), 2000);
      }
    }
  },
  beforeDestroy() {
    clearInterval(this.intervalid1);
  },
  methods: {
    hola() {
      if (this.enviar) {
        this.flashMessage.success({
          title: "Auto-saving",

          time: 1000
        });
        this.saveban = true;
        this.intervalid2 = setInterval(this.save.bind(this), 1000);
      }
      this.enviar = false;
    },
    save() {
      if (this.saveban) {
        this.flashMessage.success({
          title: "Saved",

          time: 1000
        });
      }
      this.saveban = false
    }
  },
  computed: {
    changes: {
      get: function() {
        return this.num_wacth;
      },
      set: function(v) {
        this.num_wacth = v;
      }
    }
  },
  created() {}
};
</script>
