<template>
  <div class="w-screen h-screen bg-primary text-gray-200/80 overflow-x-hidden overflow-y-scroll">
    <div class="max-w-full w-full h-full">
      <!-- Header -->
      <div class="h-1/2 bg-[url('/images/background.jpg')] flex justify-center items-center">
        <div class="flex flex-col justify-center items-center gap-8">
          <div class="text-5xl">Welcome to our system !</div>
          <div class="text-xl">Make your monitoring and controlling devices easier  !!</div>
        </div>
      </div>
      <!-- Content -->
      <div class="p-12">
        <div class="grid grid-rows-4 grid-cols-3 grid-flow-col gap-8 h-[600px]">
          <CardInfo class="row-span-4 h-full">
            <div class="w-full h-full p-12 flex flex-col gap-4">
              <div class="text-4xl font-semibold">System status</div>
              <div class="h-[1px] bg-gray-400/60"></div>
              <div class="text-2xl">Sat, 02/08/2023 - 18:40:32</div>
              <div class="flex flex-col gap-4 text-lg tracking-wide">
                <div class="flex gap-2">
                  <div class="font-semibold flex items-center justify-start gap-3">
                    <svg xmlns="http://www.w3.org/2000/svg" width="26" height="26" viewBox="0 0 24 24"><path fill="currentColor" d="M12 21q-1.05 0-1.775-.725T9.5 18.5q0-1.05.725-1.775T12 16q1.05 0 1.775.725T14.5 18.5q0 1.05-.725 1.775T12 21Zm0-11q1.875 0 3.563.6t3.062 1.65q.5.375.513.988T18.7 14.3q-.425.425-1.05.438t-1.125-.338q-.95-.65-2.1-1.025T12 13q-1.275 0-2.425.375t-2.1 1.025q-.5.35-1.125.325t-1.05-.45q-.425-.45-.425-1.062t.5-.988q1.375-1.05 3.063-1.638T12 10Zm0-6q3.125 0 5.888 1.025t4.962 2.9q.5.425.525 1.05t-.425 1.075q-.425.425-1.05.438t-1.125-.388q-1.8-1.475-4.037-2.287T12 7q-2.5 0-4.737.813T3.225 10.1q-.5.4-1.125.388t-1.05-.438Q.6 9.6.625 8.975t.525-1.05q2.2-1.875 4.963-2.9T12 4Z"/></svg>
                    <span>WIFI connection:</span>
                  </div> 
                  <span class="flex items-center gap-2 opacity-60">
                    {{ wifi }}
                  </span>
                </div>
                <div class="flex gap-2">
                  <div class="font-semibold flex items-center justify-start gap-3">
                    <svg xmlns="http://www.w3.org/2000/svg" width="26" height="26" viewBox="0 0 24 24"><path fill="currentColor" d="M20.245 4.004c.967 0 1.75.784 1.75 1.75V18.25a1.75 1.75 0 0 1-1.75 1.75h-7.247c-.087 0-.172-.007-.256-.019V4.023c.083-.012.169-.019.256-.019h7.247Zm-9.247-.002a1.8 1.8 0 0 1 .245.017V19.98a1.8 1.8 0 0 1-.245.017H3.75A1.75 1.75 0 0 1 2 18.247V5.752c0-.967.784-1.75 1.75-1.75h7.248ZM19.75 6.5h-4.502a.75.75 0 0 0-.101 1.493l.101.007h4.502a.75.75 0 0 0 .102-1.493L19.75 6.5Z"/></svg>
                    <span>Activity State:</span>
                  </div> 
                  <span class="flex items-center gap-2 opacity-60">
                    {{ state }}
                  </span>
                </div>

              </div>
            </div>
          </CardInfo>
          <CardInfo class="row-span-2 col-span-2 p-6">
            <div class="grid grid-cols-3 gap-6 h-full w-full">
              <!-- Temperature -->
              <CardDetailInfo>
                <div class="flex flex-col justify-center items-center w-full h-full">
                  <span class="text-2xl">Temperature</span>
                  <svg class="-mr-10" xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 32 32"><path fill="currentColor" d="M26 13h4v2h-4zm-3-5.414l2.828-2.828l1.414 1.414L24.414 9zm0 12.828L24.414 19l2.828 2.828l-1.414 1.414zM17 2h2v4h-2zm1 6a6.037 6.037 0 0 0-1 .09v2.052A3.957 3.957 0 0 1 18 10a4 4 0 0 1 0 8v2a6 6 0 0 0 0-12zm-8 12.184V7H8v13.184a3 3 0 1 0 2 0z"/><path fill="currentColor" d="M9 30a6.993 6.993 0 0 1-5-11.89V7a5 5 0 0 1 10 0v11.11A6.993 6.993 0 0 1 9 30ZM9 4a3.003 3.003 0 0 0-3 3v11.983l-.332.299a5 5 0 1 0 6.664 0L12 18.983V7a3.003 3.003 0 0 0-3-3Z"/></svg>
                  <div class="flex justify-center pt-2 gap-10 text-2xl w-ful">
                    <div class="flex items-center gap-1">
                      <span>{{ temperature }}</span>
                      <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 14 14"><g fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"><circle cx="2" cy="2" r="1.5"/><path d="M13.5 1.84a6 6 0 1 0-2 11.66a6 6 0 0 0 2-.34"/></g></svg>
                    </div>
                    <div class="flex items-center gap-1">
                      <span>{{ temperature*9/5 + 32 }}</span>
                      <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 14 14"><g fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"><circle cx="2.5" cy="2" r="1.5"/><path d="M7 13.5v-12h6M7 7h4"/></g></svg>
                    </div>
                  </div>
                </div>
              </CardDetailInfo>
              <!-- Air humidity -->
              <CardDetailInfo>
                <div class="flex flex-col justify-center items-center w-full h-full">
                  <span class="text-2xl">Air humidity</span>
                  <svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 24 24"><path fill="currentColor" d="M14.5 18q.625 0 1.063-.437T16 16.5q0-.625-.437-1.062T14.5 15q-.625 0-1.062.438T13 16.5q0 .625.438 1.063T14.5 18Zm-5.75-.75q.3.3.7.3t.7-.3l5.1-5.1q.3-.3.3-.7t-.3-.7q-.3-.3-.712-.3t-.713.3L8.75 15.825q-.3.3-.3.713t.3.712ZM9.5 13q.625 0 1.063-.437T11 11.5q0-.625-.437-1.062T9.5 10q-.625 0-1.062.438T8 11.5q0 .625.438 1.063T9.5 13Zm2.5 9q-3.425 0-5.712-2.35T4 13.8q0-1.55.7-3.1t1.75-2.975Q7.5 6.3 8.725 5.05T11 2.875q.2-.2.463-.287T12 2.5q.275 0 .538.088t.462.287q1.05.925 2.275 2.175t2.275 2.675Q18.6 9.15 19.3 10.7t.7 3.1q0 3.5-2.287 5.85T12 22Zm0-2q2.6 0 4.3-1.763T18 13.8q0-1.825-1.513-4.125T12 4.65Q9.025 7.375 7.513 9.675T6 13.8q0 2.675 1.7 4.438T12 20Zm0-8Z"/></svg>
                  <div class="flex justify-center pt-2 gap-10 text-2xl w-ful">
                    <div class="flex items-center gap-1">
                      <span>{{ humidity }}%</span>
                    </div>
                  </div>
                </div>
              </CardDetailInfo>
              <!-- Soil humidity -->
              <CardDetailInfo>
                <div class="flex flex-col justify-center items-center w-full h-full">
                  <span class="text-2xl">Soil humidity</span>
                  <svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 24 24"><path fill="#171717" d="M12 21.5q-3.325 0-5.662-2.312Q4 16.875 4 13.6q0-1.65.613-3.063q.612-1.412 1.737-2.487L12 2.5l5.65 5.55q1.125 1.075 1.738 2.487Q20 11.95 20 13.6q0 3.275-2.337 5.588Q15.325 21.5 12 21.5Zm0-16.2L7.75 9.5q-.75.725-1.188 1.6q-.437.875-.537 1.925h11.95q-.1-1.05-.537-1.925q-.438-.875-1.188-1.6Z"/></svg>
                  <div class="flex justify-center pt-2 gap-10 text-2xl w-ful">
                    <div class="flex items-center gap-1">
                      <span>{{ soilMoisture }}%</span>
                    </div>
                  </div>
                </div>
              </CardDetailInfo>
            </div>
          </CardInfo>
          <CardInfo class="row-span-2 col-span-2 p-6">
            <div class="grid grid-cols-2 gap-6 h-full w-full">
              <!-- Water pump -->
              <CardDetailInfo>
                <div class="h-full flex justify-between items-center gap-4 py-5 px-10">
                    <div @click="updateWaterPump" class="w-[150px] min-w-[150px] flex items-center justify-center shadow-lg bg-primary/20 rounded-full aspect-[1/1]">
                        <svg v-if="!waterPumpActive" xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 24 24"><path fill="currentColor" d="M5.7 2.5A2 2 0 0 1 7 2h2a2 2 0 0 1 2 2v1h8a2 2 0 0 1 2 2v4a1 1 0 0 1 0 2h-4a1 1 0 0 1 0-2V9h-4.8m8.64 13.73l1.27-1.27L11 10.34L2.39 1.73L1.11 3l2.54 2.54A2 2 0 0 0 5 9v9H4a2 2 0 0 0-2 2v2h12v-2a2 2 0 0 0-2-2h-1v-5.11Z"/></svg>
                        <svg v-else xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 24 24"><path fill="#0369a1" d="M19 14.5s2 2.17 2 3.5a2 2 0 0 1-2 2a2 2 0 0 1-2-2c0-1.33 2-3.5 2-3.5M5 18V9a2 2 0 0 1-2-2a2 2 0 0 1 2-2V4a2 2 0 0 1 2-2h2a2 2 0 0 1 2 2v1h8a2 2 0 0 1 2 2v4a1 1 0 0 1 1 1a1 1 0 0 1-1 1h-4a1 1 0 0 1-1-1a1 1 0 0 1 1-1V9h-6v9h1a2 2 0 0 1 2 2v2H2v-2a2 2 0 0 1 2-2h1Z"/></svg>
                    </div>
                    <div class="h-full flex flex-col items-center justify-center gap-8">
                        <span class="text-2xl text-center">Water pump</span>
                        <div>
                            <ToggleButton @updateStatus="updateWaterPump" :is-active="waterPumpActive" :disabled="disabledDevice"></ToggleButton>
                        </div>
                    </div>
                </div>
              </CardDetailInfo>
              <!-- Light -->
              <CardDetailInfo>
                <div class="h-full flex justify-between items-center gap-4 py-5 px-10">
                    <div @click="updateLight" class="w-[150px] min-w-[150px] flex items-center justify-center shadow-lg bg-primary/20 rounded-full aspect-[1/1]">
                        <svg v-if="!lightActive" xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 24 24"><path fill="currentColor" d="M9 21c0 .55.45 1 1 1h4c.55 0 1-.45 1-1v-1H9v1zm3-19C8.14 2 5 5.14 5 9c0 2.38 1.19 4.47 3 5.74V17c0 .55.45 1 1 1h6c.55 0 1-.45 1-1v-2.26c1.81-1.27 3-3.36 3-5.74c0-3.86-3.14-7-7-7zm2.85 11.1l-.85.6V16h-4v-2.3l-.85-.6A4.997 4.997 0 0 1 7 9c0-2.76 2.24-5 5-5s5 2.24 5 5c0 1.63-.8 3.16-2.15 4.1z"/></svg>
                        <svg v-else xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 24 24">
                            <path class="stroke-yellow-500/80 fill-gray-700" d="M12 6a6 6 0 0 1 6 6c0 2.22-1.21 4.16-3 5.2V19a1 1 0 0 1-1 1h-4a1 1 0 0 1-1-1v-1.8c-1.79-1.04-3-2.98-3-5.2a6 6 0 0 1 6-6m2 15v1a1 1 0 0 1-1 1h-2a1 1 0 0 1-1-1v-1h4m6-10h3v2h-3v-2M1 11h3v2H1v-2M13 1v3h-2V1h2M4.92 3.5l2.13 2.14l-1.42 1.41L3.5 4.93L4.92 3.5m12.03 2.13l2.12-2.13l1.43 1.43l-2.13 2.12l-1.42-1.42Z"/></svg>
                    </div>
                    <div class="h-full flex flex-col items-center justify-center gap-8">
                        <span class="text-2xl text-center">Light</span>
                        <div>
                            <ToggleButton @updateStatus="updateLight" :is-active="lightActive" :disabled="disabledDevice"></ToggleButton>
                        </div>
                    </div>
                </div>
              </CardDetailInfo>
            </div>
          </CardInfo>
        </div>
      </div>
      <!-- Footer -->
      <div class="px-36 py-12 border-t-2 border-solid border-secondary">
        <div class="h-full w-full flex justify-between">
          <div class="flex flex-col justify-start max-w-xs gap-2">
            <div class="text-2xl flex justify-start items-center gap-1 font-bold">
              <svg 
                xmlns="http://www.w3.org/2000/svg"
                width="32"
                height="32"
                viewBox="0 0 24 24"
              >
                <path
                  fill="#16a34a"
                  d="M5.525 18q1.05 0 1.775-.725t.725-1.775q0-.6-.275-1.175t-.825-.925l-.9-.6V6.5q0-.225-.137-.363T5.525 
                    6q-.225 0-.363.138t-.137.362v6.3l-.9.6q-.55.375-.825.925T3.025 15.5q0 1.05.725 1.775T5.525 18Zm0 2q-1.875 
                    0-3.187-1.3t-1.313-3.2q0-1.2.55-2.15t1.45-1.55V6.5q0-1.05.725-1.775T5.525 4q1.05 0 1.775.725T8.025 
                    6.5v5.3q.9.6 1.45 1.55t.55 2.15q0 1.875-1.312 3.188T5.525 20Zm8.175-5q-1.2-.825-1.95-2.125T11 10q0-2.5 
                    1.75-4.25T17 4q2.5 0 4.25 1.75T23 10q0 1.575-.75 2.875T20.3 15h-6.6Zm.7-2h5.3q.675-.6.988-1.35T21 
                    10q0-1.65-1.175-2.825T17 6q-1.65 0-2.825 1.175T13 10q0 .9.363 1.65T14.4 13Zm2.6 7q-.6 
                    0-1.05-.45t-.45-1.05h3q0 .6-.45 1.05T17 20Zm-2-2q-.425 0-.712-.288T14 17q0-.425.288-.712T15 
                    16h4q.425 0 .713.288T20 17q0 .425-.288.713T19 18h-4Zm-9.475-2.5ZM17 9.5Z"
                />
              </svg>
              <span class="bg-clip-text text-transparent bg-gradient-to-r from-green-700 from-10% to-emerald-700">BRK Ship</span>
            </div>
            <div>Make your monitoring and controlling devices easier !!</div>
          </div>
          <div class="flex flex-col justify-start max-w-sm gap-2">
            <div class="text-xl font-semibold">Contact us</div>
            <div class="flex flex-col gap-1">
              If you have any questions, please contact us with the email below
              <span class="font-semibold">brk.ship.team@gmail.com</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
import CardInfo from '../components/Card.vue';
import CardDetailInfo from '../components/CardDetail.vue';
import ToggleButton from '../components/Button/Toggle.vue';
import mqtt from "mqtt";

const topics = {
  temperature: 'NHIETDO',
  humidity: 'DOAM',
  soilMoisture: 'DOAMDAT',
  light: 'AUTO_BONGDEN',
  waterPump: 'AUTO_MAYBOM',
  m_light: 'MANUAL_BONGDEN',
  m_waterPump: 'MANUAL_MAYBOM',
  wifi: 'WIFI',
  state: 'STATE',
  websiteWaterPump: 'WEBSITE_PUMP',
  websiteLight: 'WEBSITE_LIGHT',
}

const states = {
  manual: 'MANUAL MODE',
  auto: 'AUTO MODE',
}

const wifi = ref('');
const state = ref(states.manual);

const temperature = ref(25);
const humidity = ref(25);
const soilMoisture = ref(25);

const lightActive = ref(false);
const waterPumpActive = ref(false);
const disabledDevice = ref(false);

const updateWaterPump = () => {
    waterPumpActive.value = !waterPumpActive.value;
    if (waterPumpActive.value) {
      doPublish(topics.websiteWaterPump, "ON", 0);
      console.log('WaterPump turn ON');
    } else {
      doPublish(topics.websiteWaterPump, "OFF", 0);
      console.log('WaterPump turn OFF');
    }
}
const updateLight = () => {
    lightActive.value = !lightActive.value
    if (lightActive.value) {
      doPublish(topics.websiteLight, "ON", 0);
      console.log('Light turn ON');
    } else {
      doPublish(topics.websiteLight, "OFF", 0);
      console.log('Light turn OFF');
    }
}

watch(state, (value) => {
  if (value === states.manual) {
    disabledDevice.value = false;
  } else {
    disabledDevice.value = true;
  }
})

const connection = ref({
  protocol: 'ws',
  host: 'ta28acee.emqx.cloud',
  port: 8083,
  path: "/mqtt",
  clientId: 'clientID - ' + Math.random().toString(16).substring(2, 8),
  username: 'test_26_11',
  password: 'nam12345',
})

const client = mqtt.connect('ws://ta28acee.emqx.cloud', {
  clientId: connection.value.clientId,
  username: connection.value.username,
  password: connection.value.password,
  port: connection.value.port,
  path: connection.value.path
})

const doSubscribe = () => {
  for (let key in topics) {
    client.subscribe(
      topics[key],
      { qos: 0 },
      (error: Error, granted: mqtt.ISubscriptionGrant[]) => {
        if (error) {
          console.log("subscribe error:", error);
          return;
        }
        console.log("subscribe successfully:", granted);
      }
    );
  }
};

// Send message
const doPublish = (topic: string, payload: string, qos: number) => {
  client.publish(topic, payload, { qos }, (error) => {
    if (error) {
      console.log("publish error:", error);
      return;
    }
    console.log(`published message: ${payload}`);
  });
};

// Read message
client.on("message", (topic: string, message) => {
  switch (topic) {
    case topics.temperature: {
      const value = +message.toString();
      if (value) {
        temperature.value = value;
      }
      break;
    }
    case topics.humidity: {
      const value = +message.toString();
      if (value) {
        humidity.value = value;
      }
      break;
    }
    case topics.soilMoisture: {
      soilMoisture.value = +message.toString();
      break;
    }
    case topics.wifi: {
      wifi.value = message.toString();
      break;
    }
    case topics.state: {
      state.value = message.toString();
      break;
    }
    case topics.waterPump: {
      waterPumpActive.value = message.toString() == 'ON' ? true : false
      break;
    }
    case topics.light: {
      lightActive.value = message.toString() == 'ON' ? true : false
      break;
    }
    case topics.m_waterPump: {
      waterPumpActive.value = message.toString() == 'ON' ? true : false
      break;
    }
    case topics.m_light: {
      lightActive.value = message.toString() == 'ON' ? true : false
      break;
    }
  }
});

setTimeout(() => {
  doSubscribe();
}, 1000)
</script>