***************************************
Voltage-Controlled PWM Motor Controller
***************************************
The MIT License (MIT)

=======
LTspice
=======

Spice files for testing the circuit viability.

=====
KiCAD
=====

KiCAD files of the schematic and PCB.

========================
Calibration Instructions
========================

Test Equipment
--------------

  1. +12 and -12 Volt bench power supply.
  2. +5 or +3.3 Volt bench power supply.
  3. Variable voltage bench supply (0V-3.3V or 0V-5V).
  4. Multimeter
  5. Oscilloscope
  6. Frequency Counter (Optional--Can use the scope)

First be sure your dual voltage power supply is as close to +12 and -12 volts
as possible. This will also be true in the actual environment that this PWM
will call home. If there is a slight offset between the absolute + and -
voltages there will also be a slight offset between the internal triangle wave
voltage. See below.

Calibration
-----------

  1. The R1 trimmer is used to adjust the internal triangle peak-to-peak
     reference voltage. This should nominally be 10 volts. Put your scope
     probes between TP2 (Triangle Wave) and TP0 (GND).
  2. The R3 trimmer is used to adjust the frequency of the triangle wave. This
     should nominally be 25K Hertz. Put your scope probes between TP2
     (Triangle Wave) and TP0 (GND).
  3. The R9 trimmer is used to adjust the symmetry of the sweep voltage. This
     is the Control Voltage that causes the modulates the PWM frequency. Adjust
     the variable power supply to 50% of 3.3V(1.65V) or 5V(2.5V) depending on
     your drive voltage then attach the supply to J3 and attach the multimeter
     probes to TP0 (GND) and TP3 (Sweep). Double check that the supply voltage
     is at 50% of your driving voltage then adjust R9 so the voltage on the
     multimeter is 0 (zero) volts.
  4. The R11 trimmer is used to set the peak-to-peak of the sweep voltage. Put
     the scope probes on J4 (PWM Output). Set the variable power supply to your
     drive voltage 5V or 3.3V and attache it to TP0 (GND) and TP3
     (Sweep). Adjust R11 so that the PWM goes high with no pulses, turn the
     supply to 50% and check that the PWM is 50%, then turn the sypply to 0
     (zero) volts or remove the supply and connect a wire accross J3 (Voltage
     Control Input). Check that the PWM is 0 (zero) volts.

TP1 gives you a square wave outputbut is not used in the calibration.

=========
Schematic
=========

.. image:: images/VoltageControlledPWM.png
  :width: 400
  :alt: Schematic


Feel free to contact me at: carl dot nobile at gmail.com
