Perfeito 🚀 — aqui está um **manual em README.MD** para as funções do **LionsMapperAI AirDrums** conforme você pediu:

---

# 📖 LionsMapperAI AirDrums – Manual de Funções

This document explains the **functions and usage** of the `LionsMapperAI AirDrums` library.
It covers glove/foot calibration, drum axis mapping, WAV assignment, and the methods for playing and detecting drum interactions.

---

## 🎛️ Setup Functions

### 1. `set_dataglove(side='LEFT', rgb='255,255,255')`

Defines the **DataGlove** color calibration.

* **LEFT glove (default)**: `rgb='255,255,255'`
* **RIGHT glove**: `rgb='0,0,0'`

```python
set_dataglove(side='LEFT', rgb='255,255,255')
set_dataglove(side='RIGHT', rgb='0,0,0')
```

---

### 2. `set_foot_glove(side='LEFT', rgb='110,110,110')`

Defines the **FootGlove (shoe sensor)** color calibration.

* **LEFT shoe**: `rgb='110,110,110'`
* **RIGHT shoe**: `rgb='80,80,80'`

```python
set_foot_glove(side='LEFT', rgb='110,110,110')
set_foot_glove(side='RIGHT', rgb='80,80,80')
```

---

## 🥁 Drum Mapping Functions

### 3. `set_drums_axis(_hihats, _crash_cymbal, _ride_cymbal, _snare_drum, _high_tom, _mid_tom, _floor_tom, _bass_drum)`

Defines the **coordinates (x,y)** for each drum element in the AirDrums environment.
Typically values are initialized at `0` or `0.0` until calibrated.

```python
set_drums_axis(
    _hihats=(0,0),
    _crash_cymbal=(0,0),
    _ride_cymbal=(0,0),
    _snare_drum=(0,0),
    _high_tom=(0,0),
    _mid_tom=(0,0),
    _floor_tom=(0,0),
    _bass_drum=(0,0)
)
```

---

### 4. `set_drums_wav(...)`

Defines the **audio WAV files** for each drum piece.

```python
set_drums_wav(
    wav_hihats="hihats.wav",
    wav_crash_cymbal="crash_cymbal.wav",
    wav_ride_cymbal="ride_cymbal.wav",
    wav_snare_drum="snare_drum.wav",
    wav_high_tom="high_tom.wav",
    wav_mid_tom="mid_tom.wav",
    wav_floor_tom="floor_tom.wav",
    wav_bass_drum="bass_drum.wav"
)
```

---

## 🎵 Playback & Collision Detection

### 5. `play_drums(index, lenght_time)`

* Detects collisions between **DataGloves / FootGloves** and the drum boxes.
* Plays the drum sound accordingly.

```python
play_drums(index=1, lenght_time=5)
```

---

### 6. `get_play(step_time=2)`

* Defines the **step time** for checking collisions and playing sounds.
* Calls `get_play_box()` internally.

```python
get_play(step_time=2)
```

---

### 7. `get_play_box(_data_axis, type)`

* Plays the `.wav` drum sound according to the **detected drum box**.
* `_data_axis`: coordinates of the glove/foot detection.
* `type`: drum element type (e.g., `"snare_drum"`, `"hihats"`, etc.).

```python
get_play_box(_data_axis=(0,0), type="snare_drum")
```

---

## ✅ Summary

| Function           | Description                                  |
| ------------------ | -------------------------------------------- |
| `set_dataglove()`  | Defines RGB calibration for gloves           |
| `set_foot_glove()` | Defines RGB calibration for shoes            |
| `set_drums_axis()` | Defines drum coordinates                     |
| `set_drums_wav()`  | Assigns WAV files to drum pieces             |
| `play_drums()`     | Detects collisions and triggers sound        |
| `get_play()`       | Manages timed play cycles                    |
| `get_play_box()`   | Plays specific drum sound based on collision |

---

Would you like me to also **add a “usage flow” diagram (in ASCII or SVG)** showing how the functions connect (glove → axis → wav → play)? That could make the manual more visual and easy to understand for GitHub readers.
