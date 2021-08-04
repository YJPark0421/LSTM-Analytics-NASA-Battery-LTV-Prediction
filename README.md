# SOH-prediction-using-NASA-Dataset

▶Data Description:
A set of four Li-ion batteries (# 5, 6, 7 and 18) were run through 3 different operational profiles (charge, discharge and impedance) at room temperature. Charging was carried out in a constant current (CC) mode at 1.5A until the battery voltage reached 4.2V and then continued in a constant voltage (CV) mode until the charge current dropped to 20mA. Discharge was carried out at a constant current (CC) level of 2A until the battery voltage fell to 2.7V, 2.5V, 2.2V and 2.5V for batteries 5 6 7 and 18 respectively. Impedance measurement was carried out through an electrochemical impedance spectroscopy (EIS) frequency sweep from 0.1Hz to 5kHz. Repeated charge and discharge cycles result in accelerated aging of the batteries while impedance measurements provide insight into the internal battery parameters that change as aging progresses. The experiments were stopped when the batteries reached end-of-life (EOL) criteria, which was a 30% fade in rated capacity (from 2Ahr to 1.4Ahr). This dataset can be used for the prediction of both remaining charge (for a given discharge cycle) and remaining useful life (RUL).

▶Files:
▷B0005.mat	Data for Battery #5
B0006.mat	Data for Battery #6
B0007.mat	Data for Battery #7
B0018.mat	Data for Battery #18

▶Data Structure:
▷cycle:	top level structure array containing the charge, discharge and impedance operations
	①type: 	operation  type, can be charge, discharge or impedance
	②ambient_temperature:	ambient temperature (degree C)
	③date_time: 	the date and time of the start of the cycle, in MATLAB  date vector format
	
	▷data: 
	　(data structure containing the measurements → Split multiple array columns into rows)
            
	▶charge fields are:
		④voltage_measured: 	Battery terminal voltage (Volts)
		⑤current_measured:		Battery output current (Amps)
		⑥temperature_measured: 	Battery temperature (degree C)
		⑦current_charge:		Current measured at charger (Amps)
		⑧voltage_charge:		Voltage measured at charger (Volts)
		⑨time:			Time vector for the cycle (secs)
	  
	 ▶discharge fields are:
		④voltage_measured: 	Battery terminal voltage (Volts)
		⑤current_measured:		Battery output current (Amps)
		⑥temperature_measured: 	Battery temperature (degree C)
		⑦current_charge:		Current measured at load (Amps)
		⑧voltage_charge:		Voltage measured at load (Volts)
		⑨time:			Time vector for the cycle (secs)
		⑩capacity:			Battery capacity (Ahr) for discharge till 2.7V 
	   
	　▶impedance fields are:
	　　(data array containing the two type measurements → Separate two values(real, imag) inside a array)

		(sense_current:)		Current in sense branch (Amps)
		④sense_current_real:
		⑤sense_current_imag:
		(battery_current:)		Current in battery branch (Amps)
		⑥battery_current_real:
		⑦battery_current_imag:
		(current_ratio:)		Ratio of the above currents 
		⑧current_ratio_real:
		⑨current_ratio_imag:
		(battery_impedance:)	Battery impedance (Ohms) computed from raw data
		⑩battery_impedance_real:
		⑪battery_impedance_imag:
		(rectified_impedance:)	Calibrated and smoothed battery impedance (Ohms)
		⑫rectified_impedance_rea:
		⑬rectified_impedance_imag: 
		⑭re:			Estimated electrolyte resistance (Ohms)
		⑮rct:			Estimated charge transfer resistance (Ohms)

