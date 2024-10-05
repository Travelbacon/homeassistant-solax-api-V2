**SolaX cloud for Home assistant**
*Based on version 2 of the API*

### SolaX Cloud Integration for Home Assistant (Based on API V2)

This Home Assistant integration fetches data from the SolaX Cloud using the official API V2, as described in the 1.2 API documentation. It was initially developed as an improvement over the [API V1](https://github.com/lowprize/homeassistant-solax-api) integration from [lowprice](https://github.com/lowprize), from which it was forked. However, several significant changes have been made that a new repository was a logic choice.

### Features:

- The sensors are fully configured with measurement types, making them compatible with Home Assistant’s energy monitoring features.
- Icons indicate the status of a device.
- Difference witht the [original version](https://github.com/lowprize/homeassistant-solax-api/), is the use of a RESTful API.
  
### Requirements:

- **Inverter Serial Number:** Can be found on the [Solax Cloud](www.solaxcloud.com). The serial number of the communication dongle is needed.
- **Token ID:** [Generate here](https://www.solaxcloud.com/#/api)

### Installation:

1. Edit the `secrets.yaml` file (refer to `secrets.yaml.sample` for reference).
2. Create a `rest` directory in the configuration directory (`config/`).
3. Update the configuration file (refer to `configuration.yaml.sample`).

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
