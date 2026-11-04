# Micromouse Simulator Setup

**Course:** ENCS4380 — 2026/27-S1  
**Prepared by:** Raneem 
**Date:** 2026-11-04

## Purpose

Document the Windows setup and successful execution of the starter kit's left-hand wall-following example in the mms simulator.

## Required files and software

- mms simulator (extracted from `windows.zip`).
- Extracted `micromouse-student-kit.zip`.
- A working C compiler. This setup uses the compiler already installed with OMNeT++.

The `mms-c-master` example is not required for this setup. The example used here is `student/example_wallfollow.c` from the course starter kit.

## Configure the mouse

In mms, click **+** beside **Mouse** and enter:

| Field | Value |
| --- | --- |
| Name | `Raneem_WallFollow` |
| Directory | `C:\Users\ranee\Desktop\micromousestudentkit\student` |
| Run Command | `C:\Users\ranee\Desktop\micromousestudentkit\student\example.exe` |

**Build Command:**

```text
"C:\omnetpp-6.4.0-windows-x86_64\omnetpp-6.4.0\tools\win32.x86_64\clang64\bin\gcc.exe" -O2 -std=c99 -o example.exe main_sim.c hal_sim.c mm_common.c example_wallfollow.c
```

These paths are specific to the tested computer. Other team members must replace them with their own compiler and extracted `student` directory paths. Wrap paths containing spaces in double quotes.

## Build and run

1. Save the mouse configuration using **OK**.
2. Click **Build**. A green **COMPLETE** status indicates successful compilation.
3. Click the folder icon beside **Maze**.
4. Select `student\mazes\practice8_1.txt`.
5. Click **Run** and observe the mouse moving through the maze.
6. Adjust the speed slider toward the rabbit if necessary.

## Observed result

- Build completed successfully with the green **COMPLETE** status.
- The simulator reported an 8×8 maze and the central goal region `(3,3)-(4,4)`.
- Mouse movement was confirmed by Raneem.

Run Output included:

```text
mm: HAL ENCS4380-2026/27-S1, team EXAMPLE, sim, maze 8x8, goal (3,3)-(4,4)
left-hand wall follower: this will not find the goal
```

`EXAMPLE` is the identifier printed by the supplied example. The wall-following message is an informational warning: this example demonstrates HAL use and movement; it is not the team's final maze solver and does not guarantee reaching the goal.

## Problems encountered and solutions

### Build could not start

Message:

```text
Process failed to start: The system cannot find the file specified.
```

Running `gcc --version` in Command Prompt returned that `gcc` was not recognized. The compiler was found in the OMNeT++ installation. Replacing `gcc` in the Build Command with its full quoted path allowed the build to complete.

### Run could not start

The Run Command was changed from `example.exe` to the full path of `student\example.exe`. A later run produced the HAL messages and mouse movement was confirmed.

### Maze differed from the reference

The initial view showed an empty maze; a later view used the smaller 4×4 practice maze. Loading `practice8_1.txt` selects an 8×8 practice maze. Maze size and layout depend on the selected file.

## Evidence and scope

The setup session includes a successful-build screenshot and a screen recording. Add a screenshot showing the loaded maze and moving mouse to the repository if evidence is required by the course.

This document records Raneem's setup only. Each other team member must verify the simulator on their own computer; this run does not establish that every member has completed setup.
