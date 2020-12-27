# LoRawan_Wisblock_BME680
my playground for thethingsnetwork LoRaWan using RakWireless new WISBLOCK "Lego" IoT blocks with Bosch BME680 (questionable IAQ sensor) and sensirion SCD30 (Awesome CO2 sensor)


Decoding in the TTN console:

function Decoder(bytes, port) {
  // Decode an uplink message from a buffer
  // (array) of bytes to an object of fields.
  var decoded = {};

  // if (port === 1) decoded.led = bytes[0];function Decoder(bytes, port) {
  var TEMP    = (bytes[1] << 8)  + bytes[2];
  var HUM     = (bytes[3] << 8)  + bytes[4];  
  var PRESS   = (bytes[5] <<24) + (bytes[6] <<16) + (bytes[7] <<8)   + bytes[8];
  var GAS     = (bytes[9] <<24) + (bytes[10] <<16) + (bytes[11] <<8)   + bytes[12];
  
  return {
  Temperature:     TEMP,
  Humidity:        HUM,
  Pressure:        PRESS,
  GAS:             GAS,
  };
  
}
