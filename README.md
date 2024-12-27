//Example-of-Sending-a-Signal-Using-433-MHz-Modules.Transmitter-Code-Arduino-1-
#include <VirtualWire.h>

void setup() {
  vw_setup(2000);  // Bits per second (baud rate)
  vw_set_tx_pin(12);  // Transmitter is connected to pin 12
}

void loop() {
  const char *msg = "Hello";  // Message to send
  vw_send((uint8_t *)msg, strlen(msg));  // Send the message
  vw_wait_tx();  // Wait for message to be sent
  delay(1000);  // Send message every second
}
