# VINDTA troubleshooting

This section is organised based on where a problem will first be identified.  For many problems there are several possible solutions; these should be tried in the order that they are written, generally checking to see if the problem has been resolved between each step.  There are some notes on the sort of problems to expect from each component at the start of each section.

## Bad precision and/or results

Bad DIC precision is generally caused by lack of care with cell set-up – see [Coulometer section]().  Bad TA precision is more likely to be a technical issue.

### Bad DIC precision / coulometer noisy

  * See [Coulometer section]().

### Low DIC values

!!! note "Did the DIC pipette fill completely?"
    * Are you using the pipette full sensor?  (At NIOZ: no!)  Then see ‘Pipette full sensor not working’ in [VINDTA]().

!!! note "Did the DIC pipette empty completely?"
    Check to see if some of the sample is still in the DIC pipette after it has finished emptying into the stripper.

!!! note "Are the gas delivery tubes blocked?"

    Check for kinks in the tubing, and/or crystals forming in the cathode cell end of the tube - clear these out with deionised water.


!!! note "See also: back-pressure in system"
    Check issue 'DIC pipette not emptying into stripper' in [VINDTA section]().



    

### Bad TA precision

!!! note "Is the TA cell temperature good (25.0 ± 0.5 °C)?"

!!! note "Make a new batch of HCl titrant"
    You should routinely top up or replace the HCl titrant once the bottle is 20-30% full.  Note that CRMs measured before topping up or replacing the HCl cannot be used to calibrate samples from afterwards.

!!! note "Has the NaCl rinsing solution run out?"

!!! note "Keep the HCl bottle at constant temperature (25 °C)"


### EMF doesn't change on acid addition

!!! note "Is there a blockage in HCl delivery tube from the Titrino to the TA cell?"
!!! note "Is the delivery tube trapped inside the TA cell?"

## Computer

As with all computer problems, if unplugging and reattaching cables and switching USB positions doesn’t work, try restarting the system.

### Coulometer counts not appearing on computer

!!! note "Close the analysis program and re-allocate the coulometer port after restarting"

### Results not recorded

!!! note "Did you select the bottle name before starting the run?"
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

  * Temperature too high
    * Ensure power setting is on high enough on the computer
      * Usually should be in the range 45–55 %
      * Is reset to 0% automatically every time the analysis program is re-started
    * Make sure water bath pump is running
    * Tubing may be blocked, preventing flow
      * Try reversing pump inlet and outlet for 30 seconds (temporary fix)
      * Remove relevant tubing and clean out, especially the valves

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

Always take care that everything that goes in to the water bath is taken back out again, so it can’t block the circulation tubing or the motor.  The temperature dial is incorrectly calibrated, so use a thermometer to check the temperature.  It is the temperature of the sample as it is being analysed (e.g. in the TA cell) that is important, and sometimes a water bath temperature of up to 26.5°C is best to get the measurement at 25°C, depending upon the ambient temperature.

  * Gurgling sounds
      * Add more water
  * Incorrect temperature
      * Use a thermometer to test temperature and adjust temperature dial accordingly – it is not correctly calibrated or accurate enough
      * Ensure that both switches on the water bath are turned on
  * Pump not working
      * Dismantle water bath from top and check motor for blockages

