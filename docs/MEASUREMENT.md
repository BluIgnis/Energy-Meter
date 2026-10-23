# Measurement notes

## Voltage measurement

The voltage circuit reduced the input signal to a level suitable for measurement and provided electrical isolation between the input and the low-voltage electronics. Signal conditioning adapted the output for the ESP32 ADC.

The work included selecting the measurement range, filtering the signal and checking the output against an external instrument.

## Current measurement

The current sensor output was conditioned for the ADC input range. The circuit had to preserve the variation of the measured current while keeping the signal within the range used by the microcontroller.

Low-current readings were one limitation of the prototype. The original work recorded changes in the sensor midpoint that affected those readings.

## Sampling and calculations

The ESP32 sampled the voltage and current signals. A window of samples was used to calculate:

| Quantity | Role |
| --- | --- |
| RMS voltage | Effective voltage of the measured waveform |
| RMS current | Effective current of the measured waveform |
| Active power | Average of the products of the voltage and current samples |
| Apparent power | Product of RMS voltage and RMS current |
| Power factor | Ratio of active power to apparent power |

Sensor scaling and calibration linked the ADC readings to physical values. Calibration values belonged to the original prototype and were checked during its development.

## Power and energy

Power describes the rate of energy transfer. Energy consumption is obtained by integrating active power over time.

The recorded bench comparisons cover voltage, current and active power. They do not establish the accuracy of accumulated energy totals.

## Practical observations

The work showed the importance of signal conditioning, sensor offset and calibration when combining analogue circuits with an embedded ADC. Reference-instrument quality and the range of test conditions also limit what can be concluded from a bench comparison.

[Recorded results](RESULTS.md) · [Project overview](../README.md)
