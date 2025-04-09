# EXP.NO.7-Simulation-of-Digital-Modulation-Techniques
7. Simulation of Digital Modulation Techniques Such as
   i) Amplitude Shift Keying (ASK)
   ii) Frequency Shift Keying (FSK)
   iii) Phase Shift Keying (PSK)

# AIM
To simulate and analyze digital modulation techniques such as:
i) Amplitude Shift Keying (ASK)
ii) Frequency Shift Keying (FSK)
iii) Phase Shift Keying (PSK)
using a computational tool (e.g., Scilab or MATLAB), and to understand the modulation process and waveform characteristics for digital data transmission.

# SOFTWARE REQUIRED
Scilab
# ALGORITHMS
Amplitude Shift Keying (ASK): Define binary data.

Set carrier frequency and sampling rate.

Generate time vector.

Generate message and carrier signals.

Modulate using ASK: Multiply carrier with data bits.

Plot message, carrier, and ASK signal.

Frequency Shift Keying (FSK): Define binary data.

Set two different frequencies for 1 and 0.

Create a time vector and message signal.

Generate modulated signal by selecting frequency according to the bit.

Plot message and FSK signal.

Phase Shift Keying (PSK): Define binary data.

Set carrier frequency and sampling rate.

Generate message and carrier signal.

Modulate using PSK: Use phase 0 for '1', phase π for '0'.

Plot message, carrier, and PSK signal.

# PROGRAM
**ASK MODULATION**
<pre> ```scilab// ASK modulation 
clear; 
clc; 
// Parameters 
data = [1 0 1 0 1 1 0 1]; // Binary data to be transmitted 
bit_duration = 1; // Duration of each bit 
fc = 10; // Carrier frequency (adjusted to ensure at least 10 cycles per bit) 
amplitude = 2; // Carrier amplitude 
sampling_rate = 1000; // Number of samples per bit 
// Time vector 
t = 0:1/sampling_rate:(bit_duration*length(data) - 1/sampling_rate); 
// Message signal 
message_signal = []; 
for k = 1:length(data) 
message_signal = [message_signal data(k) * ones(1, sampling_rate)]; 
end 
// Carrier signal 
carrier_signal = amplitude * sin(2 * %pi * fc * t); 
// ASK modulation 
ask_signal = []; 
for k = 1:length(data) 
if data(k) == 1 
ask_signal = [ask_signal amplitude * sin(2 * %pi * fc * (0:1/sampling_rate:bit_duration - 1/sampling_rate))]; 
else 
ask_signal = [ask_signal zeros(1, sampling_rate)]; 
end 
end 
// Plotting 
clf; 
subplot(3, 1, 1); 
plot(t, message_signal); 
title('Message Signal'); 
xlabel('Time'); 
ylabel('Amplitude'); 
subplot(3, 1, 2); 
plot(t, carrier_signal); 
title('Carrier Signal'); 
xlabel('Time'); 
ylabel('Amplitude'); 
subplot(3, 1, 3); 
plot(t, ask_signal); 
title('ASK Signal'); 
xlabel('Time'); 
ylabel('Amplitude'); 

**FSK MODULATION**
//FSK modulation 
clear; 
clc; 
// Parameters 
data = [1 0 1 0 1 1 0 1]; // Binary data to be transmitted 
bit_duration = 1; // Duration of each bit 
fc1 = 15; // Frequency for binary 1 (adjusted to ensure at least 10 cycles per bit) 
fc0 = 10; // Frequency for binary 0 (adjusted to ensure at least 10 cycles per bit) 
amplitude = 2; // Carrier amplitude 
sampling_rate = 1000; // Number of samples per bit 
// Time vector 
t = 0:1/sampling_rate:(bit_duration*length(data) - 1/sampling_rate); 
// Message signal 
message_signal = []; 
for k = 1:length(data) 
message_signal = [message_signal data(k) * ones(1, sampling_rate)]; 
end 
// Carrier signals 
carrier_signal_1 = amplitude * sin(2 * %pi * fc1 * t); 
carrier_signal_0 = amplitude * sin(2 * %pi * fc0 * t); 
// FSK modulation 
fsk_signal = []; 
for k = 1:length(data) 
if data(k) == 1 
fsk_signal = [fsk_signal amplitude * sin(2 * %pi * fc1 * (0:1/sampling_rate:bit_duration - 1/sampling_rate))]; 
else 
fsk_signal = [fsk_signal amplitude * sin(2 * %pi * fc0 * (0:1/sampling_rate:bit_duration - 1/sampling_rate))]; 
end 
end 
// Plotting 
clf; 
subplot(3, 1, 1); 
plot(t, message_signal); 
title('Message Signal'); 
xlabel('Time'); 
ylabel('Amplitude'); 
subplot(3, 1, 2); 
plot(t, carrier_signal_1, t, carrier_signal_0); 
title('Carrier Signals'); 
xlabel('Time'); 
ylabel('Amplitude'); 
legend("Carrier for 1", "Carrier for 0"); 
subplot(3, 1, 3); 
plot(t, fsk_signal); 
title('FSK Signal'); 
xlabel('Time'); 
ylabel('Amplitude');

**PSK MODULATION**
clear; 
clc; 
// Parameters 
data = [1 0 1 0 1 1 0 1]; // Binary data to be transmitted 
bit_duration = 1; // Duration of each bit 
fc = 10; // Carrier frequency (adjusted to ensure at least 10 cycles per bit) 
amplitude = 2; // Carrier amplitude 
sampling_rate = 1000; // Number of samples per bit 
// Time vector 
t = 0:1/sampling_rate:(bit_duration*length(data) - 1/sampling_rate); 
// Message signal 
message_signal = []; 
for k = 1:length(data) 
message_signal = [message_signal data(k) * ones(1, sampling_rate)]; 
end 
// Carrier signal 
carrier_signal = amplitude * sin(2 * %pi * fc * t); 
// PSK modulation 
psk_signal = []; 
for k = 1:length(data) 
if data(k) == 1 
psk_signal = [psk_signal amplitude * sin(2 * %pi * fc * (0:1/sampling_rate:bit_duration - 1/sampling_rate))]; 
else 
psk_signal = [psk_signal amplitude * sin(2 * %pi * fc * (0:1/sampling_rate:bit_duration - 1/sampling_rate) + %pi)]; 
end 
end 
// Plotting 
clf; 
subplot(3, 1, 1); 
plot(t, message_signal); 
title('Message Signal'); 
xlabel('Time'); 
ylabel('Amplitude'); 
subplot(3, 1, 2); 
plot(t, carrier_signal); 
title('Carrier Signal'); 
xlabel('Time'); 
ylabel('Amplitude'); 
subplot(3, 1, 3); 
plot(t, psk_signal); 
title('PSK Signal'); 
xlabel('Time'); 
ylabel('Amplitude');``` </pre>



# OUTPUT
ASK MODULATION
![image](https://github.com/user-attachments/assets/cb975c1c-bf37-4eae-96e9-21ca886167da)
FSK MODULATION
![image](https://github.com/user-attachments/assets/a31e7a57-9ce7-4493-8b46-5f27ce1c6ee4)
PSK MODULATION
![image](https://github.com/user-attachments/assets/53a53561-8cf0-4003-9872-ef5bd8c84f68)





 
# RESULT / CONCLUSIONS
The simulation of digital modulation techniques — ASK (Amplitude Shift Keying), FSK (Frequency Shift Keying), and PSK (Phase Shift Keying) — was successfully carried out using Scilab.
The corresponding waveforms of the message signal, carrier signal, and modulated signals were plotted and analyzed.
The results demonstrate how digital data can be represented through variations in amplitude, frequency, and phase of a carrier wave.
