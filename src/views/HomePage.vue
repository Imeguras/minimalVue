<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Blank</ion-title>
      </ion-toolbar>
    </ion-header>

  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
import { BarcodeScanner } from '@capacitor-mlkit/barcode-scanning';
export default {
  name: "HomePage", 
  components: {
    IonContent, IonHeader, IonPage, IonTitle, IonToolbar, BarcodeScanner
  }, 
  
  mounted() {
    this.prepareBarcode(); 
    this.scanBarcode();
    

  },
  deactivated() {
    this.stopScan();
  },
  beforeUnmount() {
    this.stopScan();
  },
  methods: {
    async prepareBarcode(){
      const t = BarcodeScanner.checkPermission({ force: true });
      return t;
    },
    async scanBarcode() {
      const { barcodes } = BarcodeScanner.startScan().then((barcodes) => {
        console.log('Barcode data', barcodes);
      }).catch((err) => {
        console.log('Error', err);
      });

    }
  }
}
</script>

<style scoped>
#container {
  text-align: center;
  
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>
