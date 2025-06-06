## <img src="./../../logo/lbnl_logo.png" alt="logo" width="150"/> Teststand data 
LBNL measurement protocol 

<style>
@media (prefers-color-scheme: dark) {
  .logo-inline {
    content: url("./../../logo/lbnl_logo_dark.png");
  }
}
</style>

## General measurement information
| | |
|:----------------| :----------------|
| Setup name | `ppc01`|
| period | 3 | 
| runs | 17 - 26 | 
| Location | LBNL, building 70,  room 70-141 |
| Date of measurement (yyyy-mm-dd) | 2025-02-24  | 
| Operators | Alexey Drobizhev, Ryutaro Matsumoto | 
| Goal of measurement | Trigger Averaging window length optimization as part of parameters Config optimization with new digitizer.  Characterization of ASIC with **buffer** (but without the very long cables)  |
| | |

## Experimental setup description
Germanium detector in vaccum cryostat. The pressure was kept to `~ 1e-7 hPa` with a turbomolecular pump. The vacuum chamber is cooled via cold finger in liquid nitrogen dewar to `91.7~ 91.9 K`. 

## Germanium detector
|        |                                          |
| ------ | ---------------------------------------- |
| Type   | PPC                                      |
| Name   | `DetectorId(:LBNL_PP01)`  `ChannelId(1)` |
| Weight | `~ 900 g`                                |
| Bias voltage | `2.71 kV (± 0.02 kV) `. |
|        |                                          |

## Radioactive source
Co-60 10µCi. Placed on top of vacuum cryostat with 2 styrofoam plates as distance keepers. 

## Electronics
LBNL ASIC `l1k65n`. Board `A`. The **buffer** is activated and we make use of the differential output. The positive and negative output waveforms are subtracted frmo each other. We use a board with charged capacitors + LDO for the ASIC power supply. 
| | |
|:----------------| :----------------|
|||
| Name | `l1k65n` |
| Buffer | yes |
| Cables | `~ 2 m` |
 `V_ref` | `+ 2.59 V` |

The reference voltage of the ASIC `V_ref` was provided by a stationary power supply (Keysight `E36313A`). To reduce noise 
we added a board with super-capacitors and LDOs between the ASIC and the power supply. The super-capacitors were pre-charged and then disconnected before the measurement to provide low-noise power to the ASIC.

## DAQ
Skutek Digitizer "FemtoDAQ Vireo". 
Used PHW of 30.00µs and PHAW of 0.08, 0.32µs, which showed good energy resolution in r003-r014.
| | |
|:----------------| :----------------|
|  |  | 
| Sample rate | `100 MHz` | 
| Number of samples | `4096` | 
| Waveform length | `40.96 µs` |
| Trigger threshold (ADC) | 200 (channel 0) |
| Resolution | `14` bit | 
| Pulse Height Window | `30.00`µs |
| Pulse Height Avaraging Window | `0.08`µs(r017-r021), `0.32`µs(r022-026)|
| Trigger Averaging Window | ranging `0.02`, 0.04, 0.08, 0.16,  `0.32` µs for each PHAW|
| Coupling mode | `DC coupled` | 
| Trigger position approx. | `8 µs` | 
| | |

## Remarks and comments

|          |                 |                       |
| :------- | :-------------- | :-------------------- |
| **runs** | **# waveforms** | **comment** |
| `r017-021`   | 5000/ea         | PHAW = 0.08 µs  |
| `r022-026`   | 5000/ea         | PHAW = 0.32 µs  |

