# VINDTA troubleshooting

## Bad precision and/or results

### Bad DIC precision / coulometer noisy

  * See [Coulometer section]().

### **Unexpectedly low DIC values**

!!! trouble-tubes "Are the gas delivery tubes blocked?"

    Check for kinks in the tubing, and/or crystals forming in the cathode cell end of the tube.  If there are crystals, clear these out with deionised water and then blast the tube through with carrier gas to dry it out.

!!! trouble-tubes "See also: back-pressure in system"
    Check issue 'DIC pipette not emptying into stripper' in [VINDTA section]().

!!! trouble-flask "DIC pipette not (completely) filling or emptying?"
    See [pipette problems](#pipette-problems).


### **Unexpectedly low alkalinity values**

!!! trouble-switch "Is the cell valve closing properly?"
    The cell valve (at the bottom of the alkalinity cell) should be open during the NaCl rinsing process but securely shut during the titration.  If it comes open again, then a portion of the sample can escape through this tube during the titration and the alkalinity value comes out typically a few hundred µmol/kg lower than expected.

    This can sometimes be fixed by unplugging and replugging the cable to the servo motor that controls the cell valve or replacing the servo motor entirely.  However, there is also an underlying issue inside the VINDTA box which can be fixed with the help of the NIOZ electronics department.

!!! trouble-flask "Is the HCl titrant 0.1 M?"
    The HCl ampoules used to make up the acid are also available at 10 times stronger concentration, and they look identical apart from the label.  If you use one by mistake the alkalinity will appear to be much lower than expected (and the VINDTA software may not be able to find the endpoint at all, giving an error or zero value).

!!! trouble-flask "Alkalinity pipette not (completely) filling or emptying?"
    See [pipette problems](#pipette-problems).


### **Poor alkalinity precision**

!!! trouble-switch "Is the titanium reference electrode securely connected?"

!!! trouble-flask "Has the NaCl rinsing solution run out?"
!!! trouble-flask "Is the tube in the NaCl rinsing solution filled with air and floating on the surface?"

!!! trouble-thermo "Is the TA cell temperature good (25.0 ± 0.5 °C)?"
!!! trouble-thermo "Keep the HCl bottle at a constant temperature (25 °C)"

!!! trouble-flask "Make a new batch of HCl titrant"
    You should routinely top up or replace the HCl titrant once the bottle is 20-30% full.  Note that CRMs measured before topping up or replacing the HCl cannot be used to calibrate samples from afterwards.


### **EMF doesn't change on acid addition**

!!! trouble-tubes "Is there a blockage in the HCl delivery tube from the Titrino to the TA cell?"
!!! trouble-tubes "Is the delivery tube trapped inside the TA cell?"

## **Computer**

As with all computer problems, if unplugging and reattaching cables and switching USB positions doesn’t work, try restarting the system.

### **Coulometer counts not appearing on computer**

!!! trouble-computer "Close the analysis program and re-allocate the coulometer port after restarting"

### **Results not recorded**

!!! trouble-computer "Did you select the bottle name before starting the run?"
    The bottle name must be selected (highlighted in blue) on the sample list in the VINDTA software before starting the run, otherwise no file will be saved.  If this has happened, then the DIC can still be recovered from logfile (with a bit of work), but TA is lost.

 
## Coulometer

The main problems with the coulometer are noise and the screen freezing (newer touch-screen models).

**Noise** is usually caused by a dirty cell and/or lack of care while making up the cell.  If a mistake is made while making up a cell and you are unsure whether it will make a difference, it is generally better to stop and make up a fresh cell correctly straight away rather than risk wasting an hour or two to find out.

The **screen freezing** is frustrating and its cause poorly understood.  It might be due to loose electrical connections inside the coulometer, or bad connections between the coulometer and the computer.  Often the screen will not freeze for several weeks and then it will freeze many times in a single day, for no apparent reason.

  * Run cell set-up is noisy, coulometer is noisy, and/or DIC precision is poor
    * Check solution cathode compartment for any particles e.g. bits of tissue
    * If not long since cell was prepared, leave for a while longer to stabilise
    * If there are lots of bubbles in the cathode solution, turn off the gas supply for a couple of minutes to allow them to dissipate
      * Gas supply must be switched on and bubbles flowing through cell for Run Cell Set-up
    * Check Peltier temperature is in the range 1–3 °C
    * Ensure base of coulometer cell is pushed flat against the floor of the coulometer
    * Run more Junks
    * Clean cell and frit by soaking for a couple of hours first in 10% HNO3 solution then deionised water
    * Use new bottles of cathode and anode solution
    * Ensure all of the KI in the anode compartment has not dissolved
    * Change CO2 scrubber chemicals
    * Switch to new nitrogen gas bottle
    * Use a voltage stabiliser
    * Check that the stirrer is in the coulometer cell
  * Screen frozen (accompanied by “VISA: I/O Error” on computer)
    * Turn coulometer power switch off then back on immediately
    * Select CM5011 Emulation then Start Analysis (do NOT run cell set-up)
    * If screen freezes repeatedly, try changing the USB port

## Peltier

Problems with the Peltier are generally caused either by forgetting to turn it on, forgetting to turn the circulating water bath on, or by blockages in the tubing connecting it to the water bath.

!!! trouble-thermo "Is the Peltier switched on?"
    Ensure power setting is on high enough on the computer (should be in the range 45–55%, but is reset to 0% automatically every time the analysis program is re-started) or on the Peltier box.

!!! trouble-thermo "Is there a water flow through the Peltier?"
    Make sure the circulating water bath pump is running and check for tubing blockages.  If there is a blockage, try reversing pump the inlet and outlet for 30 seconds as a temporary fix.  Better is to remove the blocked tubing and clean it out, especially around the connector valves.

## Titrino

The Titrino has on a few occasions simply stopped communicating with the computer for no apparent reason.  After several frustrating hours of repeated restarting and checking connections and settings it begins working again.  The cause of the problem and the solution both remain unclear.  When removing bubbles it is important to use a low dV/dt as described in the instructions else if the flow is too fast additional bubbles may be induced and the whole process must be repeated.

  * Bubbles in green tubing and/or burette
    * Follow instructions from step 8 of analysis session start-up routine
  * Not communicating with computer
    * Restart system
    * Use Titrino keyboard to check RS control is on
      * Press CONFIG x 3, ENTER, CONFIG x 5
    * Check cables are all connected securely
    * Change USB port
  * Screen is blank
    * Contrast control wheel is beneath DOS button
  * Unstable electrode EMF (standard deviation too high)
    * Check that there is liquid in the cell
    * Use the switch on the VINDTA box to turn the stirrer on
      * Lack of mixing is likely to be the problem especially if acid has been added while setting up the Titrino
    * Check that there are no crystals in the electrode

## VINDTA

Parts of the VINDTA will often not communicate with the computer immediately after start-up but once fixed generally work fine for the whole session of analysis.  The TA cell full sensor does not work on this VINDTA.

### **Pipette problems**

!!! trouble-tubes "Did the DIC / alkalinity pipette not fill completely?"
    Are you using the pipette full sensor?  (At NIOZ: no!)  Then see ‘Pipette full sensor not working’ in [VINDTA]().
    
    Otherwise, increase the time for this step in the method file and/or increase the carrier gas pressure so the water flows in more quickly.

!!! trouble-tubes "Did the DIC / alkalinity pipette not empty completely?"
    Check to see if some of the sample is still in the pipette after it has finished emptying into the stripper / titration cell.  Increase the time for this step in the method file and/or increase the carrier gas pressure so the water flows out more quickly

  * DIC pipette not emptying into stripper
    * May be accompanied by fluid leaking from connection on tube between valves 11 and 12
    * Back-pressure has built up in coulometer cell and stripper
    * Ensure there are no blockages in tubing
      * Gas delivery tube to coulometer cell
      * Waste gas tube from coulometer cell
      * Disconnect tubing into coulometer cell as a temporary measure to relieve the pressure
  * Gas flow reading incorrect after using Set Flow
    * Use 3C DIC read gas flow method to update the measurement
    * Check gas valve into VINDTA is open
    * Check nitrogen gas bottle is not empty
  * Parts not responding to computer (e.g. valves, thermometers, Peltier)
    * Remove and re-attach USB cables
      * Try changing USB ports if this doesn’t work
    * Ensure relevant cables on the VINDTA itself are connected properly
    * System restart
  * Pipette full sensor not working
    * Usually, falsely recording a full pipette rather than the opposite
    * Pull sensor (metal rods) out of septum and clean with lint-free tissue
    * Clean septum and red lid with lint-free tissue
    * Check electrical connections
    * System restart
  * Rinsing NaCl solution overflows from TA cell
    * Disconnect Pump 2 and wait for it to stop
    * Do not use methods that require the cell full sensor
    * Unscrew clip on Pump 2 a little to reduce pressure on tubing and reduce flow rate
  * TA pipette empty sensor not working
    * Sensor light should be red when pipette is empty, green otherwise
    * Carefully adjust position of tube passing through black sensor below TA pipette

## Water bath

Always make sure that everything that goes in to the water bath is taken back out again, so it can’t block the circulation tubing or the motor.  The temperature dial is often incorrectly calibrated, so use a thermometer to check the temperature.  It is the temperature of the sample as it is being analysed (e.g., in the TA cell) that is important, and sometimes a water bath temperature of up to 26.5°C is best to get the measurement at 25°C, depending upon the ambient temperature.

!!! trouble-tubes "The water bath circulation tubing keeps getting dirty and stuff grows inside"
    **Never put sample bottles into the circulation water bath!**  Use a separate water bath for warming your sample bottles before analysis.  Fill the system with deionised water plus a small amount of non-harmful sterilising agent.

  * Gurgling sounds
      * Add more water
  * Incorrect temperature
      * Use a thermometer to test temperature and adjust temperature dial accordingly – it is not correctly calibrated or accurate enough
      * Ensure that both switches on the water bath are turned on
  * Pump not working
      * Dismantle water bath from top and check motor for blockages

