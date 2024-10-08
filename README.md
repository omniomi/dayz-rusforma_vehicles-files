# dayz-rusforma_vehicles-files
Types and DayZ Expansion Market files for RUSForma_Vehicles - COMPLETE

## Introduction
These are DayZ types files and DayZ-Expansion-Market trader files for RUSForma_vehicles. I was unhappy with the various files floating around as some vehicles and attachments were missing, some vehicles would spawn from the trader missing attachments, some would spawn with both battery types, etc. 

I wrote a number of scripts to parse the actual vehicle script files from the mod to get every vehicle, vehicle variant, part, part variant, and default attachment. I then used those lists to construct these files programatically. They should be as near-complete as humanly possible. The only parts not included in these files are the license plates. 

## Files

* _RusFormaParts.json - Market file containing all vehicles and variants, use this OR the split files
* _RusFormaVehicles.json - Market file containing all parts and variants, use this OR the split files
* parttypes.xml - Types file for parts
* partvarianttypes.xml - Types file for part variants
* RusFormaCars.json - Market file containing cars
* RusFormaMilitary.json - Market file containing military vehicles
* RusFormaOther.json - Market file containing vans and buses
* RusFormaPartsDoors.json - Market file containing doors, hoods, etc
* RusFormaPartsOther.json - Market file containing all other parts
* RusFormaPartsWheels.json - Market file containing wheels
* RusFormaTrucks.json - Market file containing trucks and jeeps
* vehicletypes.xml - Types file for vehicles and variants

### Notes

* Trader config includes only default pricing. You will need to set your own prices.
* The types files are configured to not spawn parts in the environment. Tweak as needed.

## Spawn vehicles with number plates at trader

Follow these steps if you want to add license plates.

The included license plate classes in RUSForma_Vehicles:

* number_gos_706
* number_euro_1735
* number_gos_MILICIA
* number_gos_ARMY
* number_gos_6832
* number_gos_ARIADA
* number_gos_Black_Squad
* number_gos_POLIS
* number_gos_nasha_rasha
* RF_Number_Arctic_Long
* RF_Number_Arctic_Short (this is a square license plate that looks best on the front)

### Steps

1. Setup a types file or append to one of the parts files. Configure the min/nominal as desired for world spawning and set an appropriate lifetime.
2. If you wish to sell the plates create an appropriate market config or append to one of the parts files.
3. Edit the various vehicle market files using VS Code and follow exactly these steps:
  1. Double click the word **SpawnAttachments** in the first vehicle entry
  2. Hit <kbd>Ctrl</kbd>+<kbd>F2</kbd> on your keyboard to select every instance of **SpawnAttachments** (if this doesn't work you have the Find & Replace tool open in the top-right, close it.)
  3. Hit <kbd>End</kbd> on your keyboard followed by <kbd>Enter</kbd>. You are now typing at the top of every single **SpawnAttachments** list in the document.
  4. Type the class of the licenseplate you wish to use as a default in double-quotes followed by a comma.
  5. Hold <kbd>Alt</kbd>+<kbd>Shift</kbd> and tap <kbd>↓</kbd> one time to duplicate the plate class so it spawns front & rear.
