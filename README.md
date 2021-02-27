<p align="center">
  <a href="https://github.com/grzegorz914/homebridge-enphase-envoy"><img src="https://raw.githubusercontent.com/grzegorz914/homebridge-enphase-envoy/master/graphics/envoy.png" height="140"></a>
</p>

<span align="center">

# Homebridge Enphase Envoy-S
[![verified-by-homebridge](https://badgen.net/badge/homebridge/verified/purple)](https://github.com/homebridge/homebridge/wiki/Verified-Plugins)
[![npm](https://badgen.net/npm/dt/homebridge-enphase-envoy?color=purple)](https://www.npmjs.com/package/homebridge-enphase-envoy) [![npm](https://badgen.net/npm/v/homebridge-enphase-envoy?color=purple)](https://www.npmjs.com/package/homebridge-enphase-envoy)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/grzegorz914/homebridge-enphase-envoy.svg)](https://github.com/grzegorz914/homebridge-enphase-envoy/pulls)
[![GitHub issues](https://img.shields.io/github/issues/grzegorz914/homebridge-enphase-envoy.svg)](https://github.com/grzegorz914/homebridge-enphase-envoy/issues)

Homebridge plugin for Photovoltaic Energy System manufactured by Enphase.                                           
Supported *Envoy-IQ, Envoy-S Metered/Standard* and all peripheral devices.

</span>

# Bonus Top Bar on Mac!!!
The file is currentlly prepared to work with Envoy-S with installed Current Meter. You can allways comment not nedde lines to correct work with other Envoys.
If U have special wish or do not know how to change the file, please let me know of Your Photovoltaic config.

1. Download `enphase_envoy.15s.rb`.
2. Open the Terminal app. 
3. Install homebrew: `mkdir homebrew && curl -L https://github.com/Homebrew/brew/tarball/master | tar xz --strip 1 -C homebrew`.
4. Install digest auth: `gem install net-http-digest_auth`.
5. Instal BitBar `brew install bitbar`.
6. Edit `enphase_envoy.15s.rb` file and change the `MICROINVERTERS_SUM_WATTS = 5400` to Your microinverters power.
7. Edit `enphase_envoy.15s.rb` file and change `ENVOY_IP = envoy.local` to IP Address of Your Envoy if nedded.
8. If You already changed Your standard Envoy password, edit `enphase_envoy.15s.rb` and change `uri.password = envoySerial[-6,6]`.
9. Run [BitBar](https://github.com/matryer/bitbar) and go to Preferences>>Change Plugin Folder... and chose folder where You placed the `enphase_envoy.15s.rb`.
10. After a few seconds You will see all data on the Top Bar:

### Quick info about file name and its function:
1. The `enphase_envoy` just the file name.
2. The `15s` data refresh time.
3. The `rb` file extension.

Data refresh time
* 15s - 15 seconds
* 1m - 1 minute
* 1h - 1 hour

<p align="left">
  <a href="https://github.com/grzegorz914/homebridge-enphase-envoy"><img src="https://raw.githubusercontent.com/grzegorz914/homebridge-enphase-envoy/master/graphics/envoy_topbar.png" height="350"></a>
</p>


## Package
1. [Homebridge](https://github.com/homebridge/homebridge)
2. [Homebridge Config UI X](https://github.com/oznu/homebridge-config-ui-x)

## Installation
1. Follow the step-by-step instructions on the [Homebridge Wiki](https://github.com/homebridge/homebridge/wiki) for how to install Homebridge.
2. Follow the step-by-step instructions on the [Homebridge Config UI X](https://github.com/oznu/homebridge-config-ui-x/wiki) for how to install Homebridge Config UI X.
3. Install homebridge-enphase-envoy using: `npm install -g homebridge-enphase-envoy` or search for `Enphase or Envoy` in Config UI X.

## Know issues
1. If use with Hoobs possible config incompatibilty.

## HomeKit pairing
1. Each accessories needs to be manually paired. 
2. Open the Home <img src='https://user-images.githubusercontent.com/3979615/78010622-4ea1d380-738e-11ea-8a17-e6a465eeec35.png' height='16.42px'> app on your device. 
3. Tap the Home tab, then tap <img src='https://user-images.githubusercontent.com/3979615/78010869-9aed1380-738e-11ea-9644-9f46b3633026.png' height='16.42px'>. 
4. Tap *Add Accessory*, and select *I Don't Have a Code or Cannot Scan*. 
5. Enter the Homebridge PIN, this can be found under the QR code in Homebridge UI or your Homebridge logs, alternatively you can select *Use Camera* and scan the QR code again.

## Info v4.5.x and above!!!
1. Versin 4.5.0 and above need to be used with Homebridge min. v1.3.x.

## Info v4.x.x and above!!!
1. Version 4.0.0 whole new concept.
2. All devices in PV are detected automatically (Envoy, Q-Relays, Encharges, Meters, Microinverters).
3. Envoy authentication is detected automatically or can be added in config if was chenged.
4. For best experiences please use *Controller App* or *EVE app* for iOS
5. Installer Password which is nedded to read communications level of (Microinverters, Q-Relays, Encharges) need to be generated in externall app, more info here: https://thecomputerperson.wordpress.com/2016/08/28/reverse-engineering-the-enphase-installer-toolkit/"

## Info v3.x.x
1. With release v3.0.0 the plugin is present as Power Meter and the Power is displayed in (kW) and Energy in (kWh).
2. Max power detection is now supported.

## Info v2.3.x
1. The plugin is present as C02(ppm) sensors and the Power is displayed in Watt and Energy in Wh/kWh.
2. Production Current Level (W) - is the current Power production in (W). If the value is (< 0) and display (`-`values) then the PV consumed power from Grid.
3. Consumption Current Level Total (W) - is the Total Power Consumption in (W)).
4. Consumption Current Level Net (W) - is the Power Consumption from Grid in (W). If the value is (< 0) and display (`-`values) then the Power is exported to the Grid.
5. Peak Level (W) - display the maximum Power production/consumption.
6. Production Current Level (Wh)/(kWh) - is the Energy production (Lifetime and 7Days in kWh, Today in Wh).
7. Consumption Current Level (Wh)/(kWh) - is the Total and Net Energy Consumption (Lifetime and 7Days in kWh, Today in Wh).

## Configuration
1. Please use the [Homebridge Config UI X](https://github.com/oznu/homebridge-config-ui-x) to configure the plugin (strongly recomended), or update your configuration file manually. See `sample-config.json` in this repository or add the bottom example to Your config.json file.
2. In `host` set the *IP Address* or *host Name* or leave empy(will be used default path `envoy.local`).
3. In `refreshInterval` set the data refresh time in seconds.
4. If `disableLogInfo` is enabled, the log info will be disabled, all values and state will not be displayed in Homebridge log console.
5. In `enchargeStorage` check *ON* if encharge storage is installed. (not available from v3.5.0)
6. In `enchargeStorageOffset` set the *Offset* of encharge storage energy if nedded in (Wh),(+/-).
7. In `powerConsumptionMetersInstalled` check *ON* if consumption meters are installed. (not available from v3.5.0)
8. In `powerProductionMeter` select which *meter* will be used to display Power production. (not available from v3.5.0)
9. In `powerProductionMaxDetected` set the *maximum production Power*, if the Power production will be >= `powerProductionMaxDetected` then You get notification message from the HomeKit.
10. In `energyProductionLifetimeOffset` set the *Offset* of lifetime energy production if nedded in (Wh),(+/-).
11. In `powerConsumptionMeter` select which *meter* will be used to display Power consumption. (not available from v3.5.0)
12. In `powerConsumptionTotalMaxDetected` set the *maximum total consumption Power*, if the total Power consumption will be >= `powerConsumptionTotalMaxDetected` then You get notyfication message from the HomeKit.
13. In `energyConsumptionTotalLifetimeOffset` set the offset of lifetime total energy consumption if nedded in (Wh),(+/-).
14. In `powerConsumptionNetMaxDetected` set the maximum Power consumption from Grid, if the Power consumption will be >= `powerConsumptionNetMaxDetected` then You get notyfication message from the HomeKit.
15. In `energyConsumptionNetLifetimeOffset` set the offset of lifetime net energy consumption if nedded in (Wh),(+/-).
16. `manufacturer`, `model`, `serialNumber`, `firmwareRevision` - optional branding data displayed in Home.app, `firmware` and `serialNumber`. (not available from v4.1.0)
17. In `envoyUser` here set the envoy user or leave empty, standard is `envoy`.
18. In `envoyPasswd` here set the envoy password (only if U already changed the default password).
19. In `installerUser` here set the optional installer user, standard is `installer`.
20. In `installerPasswd` here set optional the installer password, need to be generated, more info here: https://thecomputerperson.wordpress.com/2016/08/28/reverse-engineering-the-enphase-installer-toolkit/"
<p align="left">
  <a href="https://github.com/grzegorz914/homebridge-enphase-envoy"><img src="https://raw.githubusercontent.com/grzegorz914/homebridge-enphase-envoy/master/graphics/ustawienia.png" height="150"></a>
</p>

```json
        {
            "platform": "enphaseEnvoy",
            "devices": [
                {
                    "name": "Envoy",
                    "host": "192.168.1.35",
                    "refreshInterval": 30,
                    "disableLogInfo": false,
                    "envoyUser": "envoy",
                    "envoyPasswd": "password",
                    "installerUser": "installer",
                    "installerPasswd": "password",
                    "enchargeStorageOffset": 0,
                    "powerProductionMaxDetected": 5400,
                    "energyProductionLifetimeOffset": 0,
                    "powerConsumptionTotalMaxDetected": 10000,
                    "energyConsumptionTotalLifetimeOffset": 0,
                    "powerConsumptionNetMaxDetected": 10000,
                    "energyConsumptionNetLifetimeOffset": 0,
                    "manufacturer": "Manufacturer",
                    "modelName": "Model"
                }
            ]
        }
```

## Whats new:
https://github.com/grzegorz914/homebridge-enphase-envoy/blob/master/CHANGELOG.md

## Development
- Pull request and help in development highly appreciated.
