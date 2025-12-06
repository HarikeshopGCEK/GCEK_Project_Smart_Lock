
### 1. ADC Conversion

Converting raw ADC reading to voltage:

$$ Vadc(t)=ADCrawADCmax×VrefV_{adc}(t) = \frac{ADC_{raw}}{ADC_{max}} \times V_{ref}Vadc​(t)=ADCmax​ADCraw​​×Vref $$​

Removing midpoint offset (for AC sensors):

$$ Vac(t)=Vadc(t)−Vref2V_{ac}(t) = V_{adc}(t) - \frac{V_{ref}}{2}Vac​(t)=Vadc​(t)−2Vref $$​​

---

# 2. Voltage Sensor (ZMPT101B)

RMS of sensor output:

$$ Vrms(sensor)=1N∑i=1NVac(i)2V_{rms(sensor)} = \sqrt{\frac{1}{N}\sum_{i=1}^{N} V_{ac}(i)^2}Vrms(sensor)​=N1​i=1∑N​Vac​(i)2 $$​

Scaling to real mains voltage:

Vactual=Vrms(sensor)×KvoltV_{actual} = V_{rms(sensor)} \times K_{volt}Vactual​=Vrms(sensor)​×Kvolt​

---

# 3. Current Sensor (ACS712 / CT)

Offset correction:

$$ Vac(t)=Vadc(t)−VoffsetV_{ac}(t) = V_{adc}(t) - V_{offset}Vac​(t)=Vadc​(t)−Voffset $$​

Instantaneous current:

$$ I(t)=Vac(t)SensitivityI(t) = \frac{V_{ac}(t)}{Sensitivity}I(t)=SensitivityVac​(t) $$​

RMS current:

$$Irms=1N∑i=1NI(t)2I_{rms} = \sqrt{\frac{1}{N}\sum_{i=1}^{N} I(t)^2}Irms​=N1​i=1∑N​I(t)2$$​

---

# 4. Power Calculations

Instantaneous power:

P(t)=V(t)×I(t)P(t) = V(t)\times I(t)P(t)=V(t)×I(t)

Real (active) power:

$$ Preal=1N∑i=1NP(t)P_{real} = \frac{1}{N}\sum_{i=1}^{N} P(t)Preal​=N1​i=1∑N​P(t) $$

Apparent power:

$$ S=Vrms×IrmsS = V_{rms} \times I_{rms}S=Vrms​×Irms $$​

Power factor:

$$ PF=PrealSPF = \frac{P_{real}}{S}PF=SPreal $$​​

---

# 5. Energy Calculation

Energy consumed over time:

$$ E=∑P(t)⋅ΔtE = \sum P(t)\cdot \Delta tE=∑P(t)⋅Δt $$

Energy in kilowatt-hours:

$$ EkWh=E3600000E_{kWh} = \frac{E}{3600000}EkWh​=3600000E $$​

---

# 6. Billing Amount

$$ Cost=EkWh×Tariff (₹/kWh)\text{Cost} = E_{kWh} \times \text{Tariff (₹/kWh)}Cost=EkWh​×Tariff (₹/kWh) $$