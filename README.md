# Picovoice PSoC 6 Demo (Multiple languages)

This package contains a demo project for the CY8CKIT-062S2-43012 kit using Picovoice platform.

## Supported Languages

1. English
2. French
3. German
4. Spanish

## Requirements

- [ModusToolbox&trade; software](https://www.cypress.com/products/modustoolbox-software-environment) v2.2 or later (tested with v2.3)
- Board support package (BSP) minimum required version: 2.0.0
- Programming language: C
- Associated parts: All [PSoC&trade; 6 MCU](https://www.cypress.com/PSoC6) parts

## Supported toolchains (make variable 'TOOLCHAIN')

- GNU Arm&reg; embedded compiler v9.3.1 (`GCC_ARM`) - Default value of `TOOLCHAIN`
- Arm&reg; compiler v6.13 (`ARM`)
- IAR C/C++ compiler v8.42.2 (`IAR`)

## Supported kits (make variable 'TARGET')

- [PSoC&trade; 62S2 Wi-Fi Bluetooth&reg; pioneer kit](https://www.cypress.com/CY8CKIT-062S2-43012) (`CY8CKIT-062S2-43012`)

## Installation

For this demo, you need to:
1. Download and install [ModusToolBox](https://www.cypress.com/products/modustoolbox).
1. Install a serial port monitor on your system to be able to communicate with the board. [Arduino environment's built-in serial monitor](https://www.arduino.cc/en/software) and [Coolterm](https://freeware.the-meiers.org/) are two free options available on all platforms (Windows, Linux, and macOS).

## AccessKey

Picovoice requires a valid `AccessKey` at initialization. `AccessKey`s act as your credentials when using Picovoice SDKs.
You can create your `AccessKey` for free. Make sure to keep your `AccessKey` secret.

To obtain your `AccessKey`:
1. Login or Signup for a free account on the [Picovoice Console](https://picovoice.ai/console/).
2. Once logged in, go to the [`AccessKey` tab](https://console.picovoice.ai/access_key) to create one or use an existing `AccessKey`.

## Usage

In order to compile and run the demo project on a CY8CKIT-062S2-43012 board, perform the following steps:

Create the project and open it using one of the following:

<details><summary><b>In Eclipse IDE for ModusToolbox</b></summary>

1. Click the **New Application** link in the **Quick Panel** (or, use **File** > **New** > **ModusToolbox Application**). This launches the [Project Creator](http://www.cypress.com/ModusToolboxProjectCreator) tool.

2. Pick a kit supported by the code example from the list shown in the **Project Creator - Choose Board Support Package (BSP)** dialog.

   When you select a supported kit, the example is reconfigured automatically to work with the kit. To work with a different supported kit later, use the [Library Manager](https://www.cypress.com/ModusToolboxLibraryManager) to choose the BSP for the supported kit. You can use the Library Manager to select or update the BSP and firmware libraries used in this application. To access the Library Manager, click the link from the **Quick Panel**.

   You can also just start the application creation process again and select a different kit.

   If you want to use the application for a kit not listed here, you may need to update the source files. If the kit does not have the required resources, the application may not work.

3. In the **Project Creator - Select Application** dialog, choose the example by enabling the checkbox.

4. Optionally, change the suggested **New Application Name**.

5. Enter the local path in the **Application(s) Root Path** field to indicate where the application needs to be created.

   Applications that can share libraries can be placed in the same root path.

6. Click **Create** to complete the application creation process.

For more details, see the [Eclipse IDE for ModusToolbox User Guide](https://www.cypress.com/MTBEclipseIDEUserGuide) (locally available at *{ModusToolbox install directory}/ide_{version}/docs/mt_ide_user_guide.pdf*).

</details>

<details><summary><b>In Command-line Interface (CLI)</b></summary>

ModusToolbox provides the Project Creator as both a GUI tool and a command line tool to easily create one or more ModusToolbox applications. See the "Project Creator Tools" section of the [ModusToolbox User Guide](https://www.cypress.com/ModusToolboxUserGuide) for more details.

Alternatively, you can manually create the application using the following steps:

1. Download and unzip this repository onto your local machine, or clone the repository.

2. Open a CLI terminal and navigate to the application folder.

   On Linux and macOS, you can use any terminal application. On Windows, open the **modus-shell** app from the Start menu.

   **Note:** The cloned application contains a default BSP file (*TARGET_xxx.mtb*) in the *deps* folder. Use the [Library Manager](https://www.cypress.com/ModusToolboxLibraryManager) (`make modlibs` command) to select and download a different BSP file, if required. If the selected kit does not have the required resources or is not [supported](#supported-kits-make-variable-target), the application may not work.

3. Import the required libraries by executing the `make getlibs` command.

Various CLI tools include a `-h` option that prints help information to the terminal screen about that tool. For more details, see the [ModusToolbox User Guide](https://www.cypress.com/ModusToolboxUserGuide) (locally available at *{ModusToolbox install directory}/docs_{version}/mtb_user_guide.pdf*).

</details>

<details><summary><b>In Third-party IDEs</b></summary>

1. Follow the instructions from the **In Command-line Interface (CLI)** section to create the application, and import the libraries using the `make getlibs` command.

2. Export the application to a supported IDE using the `make <ide>` command.

   For a list of supported IDEs and more details, see the "Exporting to IDEs" section of the [ModusToolbox User Guide](https://www.cypress.com/ModusToolboxUserGuide) (locally available at *{ModusToolbox install directory}/docs_{version}/mtb_user_guide.pdf*.

3. Follow the instructions displayed in the terminal to create or import the application as an IDE project.

</details>

## Operation

1. Connect the board to your PC using the provided USB cable through the USB connector.

2. Replace `ACCESS_KEY` in [`main.c`](main.c) with your AccessKey obtained from [Picovoice Console](https://picovoice.ai/console/).

3. **Optional**: The default langauge is English (`PICOVOICE_EN`). Select a different language by replacing the `COMPONENTS=` make variable in the [`Makefile`](Makefile) with your selected language. ie. `COMPONENTS=PICOVOICE_DE` for German language support.

4. Program the board using one of the following:

   <details><summary><b>Using Eclipse IDE for ModusToolbox</b></summary>

      1. Select the application project in the Project Explorer.

      2. In the **Quick Panel**, scroll down, and click **\<Application Name> Program (KitProg3_MiniProg4)**.
      </details>

   <details><summary><b>Using CLI</b></summary>

     From the terminal, execute the `make program` command to build and program the application using the default toolchain to the default target. You can specify a target and toolchain manually:
      ```
      make program TARGET=<BSP> TOOLCHAIN=<toolchain>
      ```

      Example:
      ```
      make program TARGET=CY8CKIT-062S2-43012 TOOLCHAIN=GCC_ARM
      ```
</details>

For these demos, the default wake words and the context are:

| Language | Wake word        | Context                 |
|----------|------------------|-------------------------|
| English  | Picovoice        | Smart lighting          |
| French   | Salut ordinateur | éclairage intelligent   |
| German   | Hey computer     | Beleuchtung             |
| Spanish  | Hola computadora | Iluminación inteligente |

In case of English version, after uploading the firmware to the microcontroller, the engine can recognize commands such as:

> Picovoice, turn off the lights.

or

> Picovoice, set the lights in the bedroom to blue.

See below for the full contexts:

### English context

```yaml
context:
  expressions:
    changeColor:
      - "[turn, make] (all, the) lights $color:color"
      - "[change, set, switch] (all, the) lights to $color:color"
      - "[turn, make] (the) $location:location (color, light, lights) $color:color"
      - "[change, set, switch] (the) $location:location (color, light, lights) to $color:color"
      - "[turn, make] (the) [color, light, lights] [at, in] (the) $location:location $color:color"
      - "[change, set, switch] (the) [color, light, lights] [at, in] (the) $location:location to $color:color"
      - "[turn, make] (the) [color, light, lights] $color:color [at, in] (the) $location:location"
      - "[change, set, switch] (the) [color, light, lights] to $color:color [at, in] (the) $location:location"
    changeLightState:
      - "[switch, turn] $state:state (all, the) lights"
      - "[switch, turn] (all, the) lights $state:state"
      - "[switch, turn] $state:state (the) $location:location (light, lights)"
      - "[switch, turn] (the) $location:location [light, lights] $state:state"
      - "[switch, turn] $state:state (the) [light, lights] [at, in] (the) $location:location"
      - "[switch, turn] (the) [light, lights] [in, at] the $location:location $state:state"
    changeLightStateOff:
      - "shut off (all, the) lights"
      - "shut (all, the) lights off"
      - "shut off (the) $location:location (light, lights)"
      - "shut (the) $location:location (light, lights) off"
      - "shut off (the) [light, lights] [at, in] (the) $location:location"
      - "shut (the) [light, lights] off [at, in] (the) $location:location"
      - "shut (the) [light, lights] [at, in] (the) $location:location off"
  slots:
    color:
      - "blue"
      - "green"
      - "orange"
      - "pink"
      - "purple"
      - "red"
      - "white"
      - "yellow"
    state:
      - "off"
      - "on"
    location:
      - "bathroom"
      - "bedroom"
      - "closet"
      - "hallway"
      - "kitchen"
      - "living room"
      - "pantry"
```

### French context

```yaml
context:
  expressions:
    changeColor:
      - "[Mets, Mettez, Allume, Allumez, Change, Changez] [les, la] [lumières, lumière] (en) $color:color"
      - "[Mets, Mettez, Allume, Allumez, Change, Changez] [les, la] [lumières, lumière] [du, de la, dans la, dans le] $location:location (en) $color:color"
    changeLightStateOff:
      - "[Éteins, Éteignez] [les, la] [lumières, lumière]"
      - "[Éteins, Éteignez] [les, la] [lumières, lumière] [du, de la] $location:location"
      - "[Éteins, Éteignez] [les, la] [lumières, lumière] [dans la, dans le] $location:location"
    changeLightStateOn:
      - "[Allume, Allumez] [les, la] [lumières, lumière]"
      - "[Allume, Allumez] [les, la] [lumières, lumière] [du, de la] $location:location"
      - "[Allume, Allumez] [les, la] [lumières, lumière] [dans la, dans le, dans l'] $location:location"
  slots:
    color:
      - bleu
      - vert
      - orange
      - rose
      - violet
      - rouge
      - blanc
      - jaune
    location:
      - salle de bain
      - toilettes
      - chambre
      - chambre à coucher
      - penderie
      - placard
      - couloir
      - cuisine
      - salle de séjour
      - salon
      - garde manger
```

### German context

```yaml
context:
  expressions:
    changeColor:
      - "[färbe, ändere, mache] (alle, die, das) [Licht, Lichter] (zu, in)
        $color:color"
      - "[färbe, ändere, mache] (alle, die, das) (Licht, Lichter) (im)
        $location:location (Licht, Lichter) (zu, in) $color:color"
    changeState:
      - (Mache) (alle, die, das) [Licht, Lichter] $state:state
      - (Mache) (alle, die, das) $location:location [Licht, Lichter] $state:state
      - (Mache) (alle, die, das) [Licht, Lichter] im $location:location
        $state:state
  slots:
    color:
      - blau
      - grün
      - orange
      - pink
      - lila
      - rot
      - weiß
      - gelb
    state:
      - an
      - aus
    location:
      - Badezimmer
      - Schlafzimmer
      - Kinderzimmer
      - Flur
      - Küche
      - Wohnzimmer
      - Speisekammer
```

### Spanish context

```yaml
context:
  expressions:
    changeColor:
      - haz que las luces sean $color:color
      - cambia las luces a $color:color
      - haz que [la, las] [luz, luces] [del, de la, en el, en la]
        $location:location [sea, sean] $color:color
      - cambia [la, las] [luz, luces] [del, de la, en el, en la]
        $location:location a $color:color
      - haz que [sea, sean] $color:color [la, las] [luz, luces] [del, de la, en
        el, en la] $location:location
      - cambia a $color:color [la, las] [luz, luces] [del, de la, en el, en la]
        $location:location
    changeLightState:
      - $action:action (todas) las luces
      - $action:action (la, las) [luz, luces] [del, de la, en el, en la]
        $location:location
  slots:
    color:
      - azul
      - verde
      - rosado
      - morado
      - rojo
      - blanco
      - amarillo
    location:
      - baño
      - armario
      - cocina
      - sala
      - despensa
      - dormitorio
      - habitación
      - pasillo
    action:
      - encienda
      - apaga
```

## Create Custom Models

1. Copy the UUID of the board printed at the beginning of the session to the serial port monitor.
1. Go to [Picovoice Console](https://console.picovoice.ai/) to create models for [Porcupine wake word engine](https://picovoice.ai/docs/quick-start/console-porcupine/) and [Rhino Speech-to-Intent engine](https://picovoice.ai/docs/quick-start/console-rhino/).
1. Select `Arm Cortex-M` as the platform when training the model.
1. Select `PSOC6` as the board type and provide the UUID of the chipset on the board.

The model is now being trained. You will be able to download it within a few hours.

## Import the Custom Models

1. Download your custom voice model(s) from [Picovoice Console](https://console.picovoice.ai/).
2. Decompress the zip file. The model file is either `.ppn` for Porcupine wake word or `.rhn` for Rhino Speech-to-Intent. Both zip archives also contain a `.h` header file containing the `C` array version of the binary model.
3. Copy the contents of the arrays inside the `.h` header files and update the `KEYWORD_ARRAY` (Porcupine) and `CONTEXT_ARRAY` (Rhino) values in [/include/pv_params.h](./include/pv_params.h).
