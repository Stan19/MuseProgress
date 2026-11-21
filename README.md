# MuseProgress

**MuseProgress** is free interactive Windows application for beginner pianists designed to practice sight-reading skills. The application displays sheet music on the computer screen in high definition and provides visual feedback as the student plays on a digital piano (synthesizer or MIDI keyboard) connected to the PC via a **USB-MIDI** cable. 

The archive with **the application** is availalbe on release page: https://github.com/Stan19/MuseProgress/releases.

The source code of the application is not included.

<img width="1876" height="732" alt="image1" src="https://github.com/user-attachments/assets/6546dcc1-c2e2-40b7-abf4-05ee8ed3b947" />

Correctly played notes are highlighted in green, a half-step error is marked in yellow, and a deviation of a full step or more is marked in red. Unplayed notes remain standard black. If multiple keys are pressed instead of a single correct note, the note turns blue. 

During practice, players cannot go back to replay incorrect notes. Just like in real music performance, the requirement is to keep playing "only forward". 

The application is provided to music students free of charge as a **MuseProgress.zip** archive. Students can unpack the archive anywhere on their computer's hard drive. The source code of the application is not included.
* _**Please note:** Since the application does not have a standalone installer, the system paths to the software synthesizer and score fonts are created during the initial launch. Therefore, after opening the program for the first time, try to open any sheet music from the music_library folder. The system paths will be generated at this moment, but the application will be unable to use them immediately and will crash. Upon the next launch, the application will function as intended._
## 

### Installation from GitHub

The application is written in Python and JavaScript, compiled using PyInstaller in `onedir` mode, and packaged into a ZIP archive.
It is recommended to extract the archive on your PC to a MuseProgress subfolder inside your Documents directory, or create this subfolder in the root directory of drive C: (or any other drive). Extracting the archive to Program Files is not recommended, as you will have to manually grant permissions for each file during extraction.

#### Package Contents:

* **MuseProgress.exe** — The main executable file of the application.
* **index.html** — Core interface file.
* **settings.ini** — Configuration file.
* **README** — Documentation files ( _EN and _RU versions).

*Included subfolders:*

* `_internal` — Contains Python modules required for the application to function.
* `metronome_midi` — Contains `.mid` files for the metronomes and count-in countdowns.
* `music_library` — Contains the built-in library of sheet music and pieces.
* `soundfonts` — Contains the sound font library for audio playback.
* `static_js` — Contains JavaScript files for the Verovio rendering engine. 

## 
### Key Features

* **Fully Offline Operation:** The application runs completely offline via local installation on your computer. No internet connection or registration is required.
* **Wide Range of Supported Formats:** The app opens sheet music in the following formats: `.mei`, `.xml`, `.musicxml`, and `.mxl` (compressed `.xml`).
* **Built-in Music Library:** Since practicing sight-reading requires a vast variety of sheet music, the application includes a **music_library** folder containing a large collection of classical pieces and exercises. To load a piece from the library, click the **[Open File]** button and select the desired file. You can freely add new files in the supported formats or customize the subfolders inside **music_library**.
* **Integrated Synthesizer:** The app features a built-in **fluidsynth** synthesizer. Using a compact sound library, it can play back sheet music on the student's computer with audio quality sufficient for practice.
* **Multi-Instrument Support:** In addition to piano pieces, the application can play multi-voice instrumental pieces. This allows students who play other **USB-MIDI** compatible instruments to practice their sight-reading skills as well.
* **Hotkeys:** Keyboard shortcuts are fully implemented for all main buttons in the application.

## 

### Playback

* **Listening to Pieces:** To simply listen to the loaded file, click the [**Play**] button. During playback, the played notes turn green, and a green cursor moves above them.
* **Pausing and Resuming:** The [**Pause/Resume**] button allows you to pause and resume the playback of the piece at any time.

<img width="1155" height="216" alt="image2" src="https://github.com/user-attachments/assets/9c9005c3-b03c-43df-b958-d28c3afc1b2e" />

- **Loudness:** Slider **Main Volume** allows to adjust the volume of playback.

<img width="267" height="40" alt="image14" src="https://github.com/user-attachments/assets/6ccaaae4-58b8-487a-9cec-502964bd24a8" />

* **Part (voice) selector for playback:**  The part selector allows you to choose specific parts in a piece for separate listening. In piano pieces, the **Both hands** option is selected by default, while in polyphonic pieces, the **ALL VOICES** option is selected by default. Technically, you can switch between parts during playback, but this may cause long notes to "hang" or stick. Therefore, it is best to select the part first and only then press the [**Play**] button.

<img width="150" height="225" alt="image13" src="https://github.com/user-attachments/assets/2abe2748-9733-48e2-9132-2b9538e53ea4" />

  ## 

### Connecting a Digital Piano

The application automatically detects digital pianos, synthesizers, and MIDI keyboards connected via a **USB-MIDI** cable.
By default, if a digital piano or synthesizer is connected, the app will use the sound generator of your connected instrument instead of the built-in Fluidsynth. 

<img width="571" height="45" alt="image3" src="https://github.com/user-attachments/assets/f8dc3506-8971-43e6-bb53-73b1c3625115" />

You can switch the audio source using the [**Synth:Keyboard / Synth:Fluidsynth**] button. For example, if you connect a basic MIDI keyboard without a built-in sound generator, you should switch to [**Synth:Fluidsynth**] so that the sound is produced by the computer's internal software. 

**Audio Latency:** Please note that when using the computer's built-in synthesizer, you may experience a slight audio latency. For simple educational pieces, this delay is perfectly acceptable.

## 

## Sight-Reading Practice

The application offers two practice modes to train sight-reading skills. By default, both modes expect the student to practice using both hands simultaneously. However, student can select only the Right hand, Left hand, or a specific voice if the piece features multiple musical parts.

<img width="158" height="154" alt="image4" src="https://github.com/user-attachments/assets/b87a6ce9-5aad-4adb-ac0a-b4c2124edf54" />

A wide, bright "sunny" cursor starts on the far left, highlighting the note the student needs to play next. It also illuminates approximately one upcoming measure (bar) of music. This "sunny" cursor advances to the next notes only after the student presses the keys on the piano to play the leftmost note (or chord).

<img width="772" height="217" alt="image12" src="https://github.com/user-attachments/assets/1c2dd640-8ff2-45fa-a16e-9d7dd26fda14" />

#### 1. [Practice: Hit right notes]

This mode is enabled by default upon launching the app. It is a simplified training mode that does not require you to play perfectly in time. In this mode, beginner pianists can play at their own pace, gradually learning how notes on the sheet music correspond to the piano keys.

#### 2. [Practice: Play with accompaniment]

This mode is designed for advanced students who are already capable of playing at a steady tempo alongside a metronome. In this mode:

* **Tempo:** You do not have to play at the original tempo of the piece. You can reduce the speed down to 20% of the original tempo using the **Tempo** slider.
* **Accompaniment:** If the student chooses to play the Right-hand part, the application will automatically play the Left-hand part, and vice versa. Automatically played notes are visually marked in **gray**. 
* **Starting Practice:** To begin practicing, click the \[**Play**\] button. If the student stops pressing the piano keys after practice starts, the automatic playback will continue until the end of the piece or until the \[**Stop**\] button is pressed. 
* **Vocal practice:** For pieces that include both a vocal part and a piano part, students can select the vocal part to practice sight-singing with their own voice to the automatic accompaniment.

#### Resetting Progress

The \[**Restart practice**\] button allows you to return to the beginning of the piece (or to the start of the selected measures). This will reset the color-coded feedback of all played notes back to their original state. This feature applies to both practice modes.

## 

### Count-In

The count-in feature is enabled via the \[**Count_In**\] button. It gives the student enough time to move their hands from the computer to the piano keys and prepare to play. During the count-in, a yellow cursor flashes on the screen. 

<img width="381" height="292" alt="image5" src="https://github.com/user-attachments/assets/3be9460f-c025-4f0c-811e-46e55224446e" />

The application allows you to select either one or two measures (bars) for the countdown duration.

<img width="228" height="46" alt="image6" src="https://github.com/user-attachments/assets/faffd30b-8c4f-4934-9936-c9bc99aa62a5" />


## 

### Two options for Metronome

The application features two different metronome options:

* \[**Score metronome**\]: This is essentially a drum track attached to the sheet music. It automatically accounts for all time signature and tempo changes within the piece, which is crucial for complex classical music (such as pieces by Chopin). If a digital piano is connected, the application will play this drum track on Channel 10 using the instrument's built-in sound generator.
* \[**Simple metronome**\]: This is a basic metronome played through the built-in **fluidsynth** synthesizer. It determines the time signature and tempo based solely on the very beginning of the piece. This option is useful if your digital piano does not support the *Score metronome* drum track, or if you want to practice at a steady pace while in **Practice: Hit right notes** mode.

For both metronomes, you can adjust the volume and tempo using the **Metro Vol** and **Tempo** sliders. The values of these sliders apply to both metronomes simultaneously.

<img width="586" height="38" alt="image7" src="https://github.com/user-attachments/assets/57ba97b5-9be9-49ba-acbf-96f4d447fd65" />


The value on the **Tempo** slider represents the initial **BPM** specified in the music file, which is set as 100%. Any tempo adjustments are reflected as a percentage (ranging from 20% to 150%).

## 

### Selecting Measures (Looping)

The application allows students to select a specific range of measures within a piece to listen to or practice that specific section. To do this, hover the mouse over a starting measure, press and hold the left mouse button, drag across the desired measures, and then release the button.

<img width="1177" height="237" alt="image8" src="https://github.com/user-attachments/assets/834159bf-19c9-4642-a68a-d67c69033d1c" />


Alternatively, you can enter the starting and ending measure numbers into the "**from:**" and "**to:**" fields and click the \[**Select measures**\] button.

<img width="560" height="42" alt="image9" src="https://github.com/user-attachments/assets/9b2143b5-d936-47ad-941a-6f2f9b6bdbd6" />


* If you specify a value only in the "**to:**" field, the app will select everything from the first measure up to the specified one.
* If you specify a value only in the "**from:**" field, the app will select everything from the specified measure to the very end of the piece.

To clear the selection, click the same button, which will now display \[**Reset selection**\]. 

*Note: The **Count_In** countdown feature will always play for exactly one measure when applied to a selected range of measures.*

## 

### Looping Playback

Both full-piece playback (or practice) and selected measure ranges can be looped continuously using the \[**Loop**\] button.

## 

### Score Font Size

The size of the notes on the screen can be adjusted using the **Font size** slider (ranging from 20 to 80) to perfectly fit the student's monitor.

<img width="273" height="41" alt="image10" src="https://github.com/user-attachments/assets/279d9a92-f23e-4c4d-a0fe-63a475b060e9" />


## 

### Keyboard Shortcuts

Since it is not always convenient to use a mouse while sitting at the piano, keyboard shortcuts are implemented for all main buttons in the application:

| Button                                                            | Hotkey         |
|:----------------------------------------------------------------- |:-------------- |
| **Open File**                                                     | `Ctrl + F`     |
| **Restart practice**                                              | `Ctrl + Space` |
| **Practice: Hit right notes / Practice: Play with accompaniment** | `Ctrl + P`     |
| **Count In: ON / Count In: OFF**                                  | `Ctrl + C`     |
| **Score Metronome: ON / Score Metronome: OFF**                    | `Ctrl + M`     |
| **Simple Metronome: ON / Simple Metronome: OFF**                  | `Alt + M`      |
| **Play / Stop**                                                   | `Space`        |
| **Pause / Resume**                                                | `Alt + P`      |
| **Loop: ON / Loop: OFF**                                          | `Ctrl + L`     |
| **Select measures / Reset selection**                             | `Ctrl + S`     |
| **Synth: Keyboard / Synth: Fluidsynth**                           | `Ctrl + K`     |

## 

### Settings

The **settings.ini** file automatically saves the last opened file along with the states of all buttons and sliders at the moment the application is closed. This ensures that your next session starts with the exact same configuration. You can open this file using a standard text editor (like Notepad) and manually adjust the parameters if needed.


<img width="866" height="461" alt="image15" src="https://github.com/user-attachments/assets/4b629e52-dff7-4b96-88aa-8da0bb0fb979" />


***The first four parameters in the settings file are not displayed in the application's user interface and can only be modified directly within the file:***

* **`minimal_velocity = 5`**: This parameter filters out accidental key presses. Any digital piano keys pressed with a velocity lower than this value will be ignored. You can customize this threshold to fit your playing style.
* **`fluidsynth_sample_rate = 48000.0`** and **`fluidsynth_sample_format = 16bits`**: You may need to edit these parameters to match your computer's audio setup. Otherwise, the built-in Fluidsynth synthesizer might generate sound that is 3/4 of a tone higher or lower than the standard pitch. To find the correct values, check your Windows settings under **Start / System / Sound / Properties (Speakers) / Output settings / Format**, and set these parameters to match your system. Note that the **`fluidsynth_sample_rate`** parameter must strictly be a **float** value (e.g., `48000.0` or `44100.0`).  
* **open_last_file_on_start** : Default value is **false**. Set it **true** to open same file when next session starts.
## 


##### USB-MIDI Device Nuances

Digital pianos and synthesizers may vary slightly in how they function within this application:

* **Full GM Standard Support:** If your digital piano fully supports the General MIDI (GM) standard, everything will sound correct out of the box. This includes your primary piano sound, the metronome drum track on Channel 10, and any other musical instruments when playing multi-instrument scores.
* **Advanced Synthesizers:** If you connect a complex synthesizer, it usually supports the full GM standard as well. However, you may need to configure a specific Studio Set (or Combination) on your instrument. Ensure that Channel 1 features your best piano sound, Channel 10 is set to a standard drum kit, and the remaining channels are mapped to GM piano sounds. This ensures that the standard GM instrument set triggers correctly when playing multi-instrument pieces.
* **No GM Support:** If your digital piano does not support the GM standard and lacks standard drum sounds, you will only hear the sound of the main piano. The *Score metronome* will be silent, and multi-instrument scores will not play back properly. In this case, use the **Simple metronome** button to play the metronome sound directly from your computer instead.

## 

##### Converting Other Sheet Music Formats to .mei

The MuseProgress application does not support sheet music in `.mscz`, `.mid`, or `.gpt` formats. If you have files in these formats that you would like to use, we highly recommend using the free desktop application **MuseScore 4**, which is capable of ***exporting*** these formats into the supported **`.mei`** format.

## 

### Acknowledgments

This application would not have been possible without these excellent free and open-source components:

* **[Verovio](https://www.verovio.org/index.xhtml)** — A music notation engraving library.
* **[FluidSynth](https://www.fluidsynth.org/)** — A real-time software synthesizer based on the SoundFont 2 specifications.
* **[Mido](https://mido.readthedocs.io/en/stable/)** — MIDI Objects for Python, a library for working with MIDI 1.0 ports, messages, and files.
* **[RtMidi](https://mido.readthedocs.io/en/stable/backends/rtmidi.html)** — A backend that provides the interface between Mido and the operating system level MIDI stack.
* **[pretty-midi](https://pypi.org/project/pretty-midi/)** — Functions and classes for handling and modifying MIDI data.
* **[PySide6](https://pypi.org/project/PySide6/)** — Python bindings for the Qt cross-platform application and UI framework.
* **[music21](https://music21.org/music21docs/)** — A toolkit for computer-aided musical analysis and computational musicology.

Additionally, it is worth noting that solutions and code structures proposed by **Google Gemini AI** were utilized during the development of this application. 

##
# Disclaimer
MuseProgress is a free, independent project built to help musicians. It is not connected to MuseGroup, MuseScore, or any other commercial brands. The project gives musicians access to features that commercial brands usually keep behind a paywall.
