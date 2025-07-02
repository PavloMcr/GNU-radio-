# Hopping JAMMER
Smart jammer based on SDR with frequency hopping

## ⚠️ WARNING ⚠️

Jamming is illegal !


## Prerequisites

- SDR devices that is enabled to transmit signal (HackRF, USRP, LimeSDR, BladeRF, etc.)
- GNURadio 3.8 / 3.10 (maint-3.10 branch)

### Manual jamming 

If you have an SDR device with uhd drivers, you can run the code as follows:

```sh
$ python3 jam.py
```

also you can edit the GNURadio block schema ,  ``sources/jam.grc``:

```sh
$ gnuradio-companion sources/jam.grc
```

The central frequency can be configured with the QT GUI to target a frequency. But this tool has also a feature to do it automatically.

### Automatic cleverjamming

To automate jammer , write list of frequencies that save a JSON file . This JSON file looks as follows:

```sh
$ cat jam.json  
{
    "Name1": {
        "Bandwidth": "10MHz", 
        "Freq": 924e5
    },
    "Name2": {
        "Bandwidth": "20MHz", 
        "Freq": 10e5
    }    
}
```


Start jamming
```sh
$ python3 clever.py --file jam.json -d jump_time_in_sec
```

jam hopping between each frequencies can be set with an arguments '-d' (see -h).

![Jamming]((https://github.com/PavloMcr/GNU-radio-/blob/main/Git_Jammer/CleverJAM/sources/jam.png))
![Jamming]([Git_Jammer/CleverJAM/sources/jamd.jpg](https://github.com/PavloMcr/GNU-radio-/blob/main/Git_Jammer/CleverJAM/sources/jamd.jpg))
