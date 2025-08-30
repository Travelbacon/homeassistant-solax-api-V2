### Please consider this first
When using Solax energy metering to monitor your household consumption, please note that the Solax Cloud records data in 5-minute intervals. As a result, there may be small discrepancies between the values shown in the Solax Cloud and the readings from your official electricity meter regarding consumption from and to the grid. However, the solar panel production data is always accurate.
If precise consumption data is required, we recommend using a P1 meter to read the electricity meter directly.

For local network connection there is the [SolaX Power](https://www.home-assistant.io/integrations/solax) integration.
This works via your local network. The password for the local webserver can be found under **Backup password** in the [Solax Cloud](www.solaxcloud.com) under WiFi dongle.
Polling frequency remains at 5 minutes max, and it has no extra data and calculations from the cloud. For example the sum of total power from the arrays of your solar pannels.

### SolaX cloud for Home assistant
*Based on version 2 of the API*

### SolaX Cloud Integration for Home Assistant (Based on API V2)

This Home Assistant integration fetches data from the SolaX Cloud using the official API V2, as described in the 1.2 API documentation. It was initially developed as an improvement over the [API V1](https://github.com/lowprize/homeassistant-solax-api) integration from [lowprice](https://github.com/lowprize), from which it was forked. However, several significant changes have been made that a new repository was a logic choice.

### Features:

- The sensors are fully configured with measurement types, making them compatible with Home Assistant’s energy monitoring features.
- Icons indicate the status of a device.
- Difference witht the [original version](https://github.com/lowprize/homeassistant-solax-api/), is the use of a RESTful API.
  
### Requirements:

- **Inverter Serial Number:** Can be found on the [Solax Cloud](www.solaxcloud.com). The serial number of the communication dongle is needed and can be found under the Registration number.
- **Token ID:** [Generate here](https://www.solaxcloud.com/#/api)

### Installation:

1. Edit the `secrets.yaml` file (refer to `secrets.yaml.sample` for reference).
2. Create a `rest` directory in the configuration directory (`config/`).
3. Update the configuration file (refer to `configuration.yaml.sample`).
4. Optinally change the URL from https://global.solaxcloud.com to the URL mentioned int the Solax App. Note that the website of solaxgloud displays global.solaxcloud.com
5. Change `scan_interval` to 10 seconds for more realtime communication. Note that the setting Secondreporting under settings in the app must be enabled.

### Adding data to Energy
Add the following sensors to the energy settings.
- The **Solax grid energy import total** sensor (in kWh) for the Grid Consumption.
- The **Solax grid ehergy export total** for the Return to grid, for example, the solar panel energy you do not consume and return to the grid instead.
- The **Solax yield energy total** for the Solar production

### Additional Notes:

- The **SolaX Cloud site** displays the total energy yield of the entire site, while the API fetches data directly from the inverter. This can lead to differences in the reported totals, especially if a new inverter was installed or there were issues during the initial setup.
- For the most accurate and reliable energy data, it is recommended to pull information directly from the energy meter. The energy meter provides certified and precise readings, ensuring you get the correct data. Using the inverter's data might lead to discrepancies in total yield values.

### Sensors :

| Naam                          | Unit    |
|-------------------------------|---------|
| Solax battery capacity         | %       |
| Solax battery power            | W       |
| Solax battery status           | Status  |
| Solax cloud connection status  | Status  |
| Solax cloud last update        | DateTime|
| Solax consume power            | W       |
| Solax EPS A phase active power | W       |
| Solax EPS B phase active power | W       |
| Solax EPS C phase active power | W       |
| Solax grid energy export total | kWh     |
| Solax grid energy import total | kWh     |
| Solax grid export power        | W       |
| Solax inverter output power    | W       |
| Solax inverter status          | Status  |
| Solax meter 2 power           | W       |
| Solax PV total input power     | W       |
| Solax PV1 input power          | W       |
| Solax PV2 input power          | W       |
| Solax PV3 input power          | W       |
| Solax PV4 input power          | W       |
| Solax yield energy today       | kWh     |
| Solax yield energy total       | kWh     |


### Official API Documentation:

Official API Documentation: [SolaX API Documentation v1.2](https://github.com/Travelbacon/homeassistant-solax-api-V2/blob/main/misc/SolaXCloud%20User%20API%20V2-1-2.pdf).
