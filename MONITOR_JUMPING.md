# DWM Monitor Jumping Enhancement

## Summary
Added functionality to jump directly to specific monitors (monitor 1, 2, 3, 4, 5) instead of just cycling through them with Left/Right arrows.

## Changes Made

### 1. New Functions in dwm.c

#### focusmonbynum(const Arg *arg)
- Focuses on a specific monitor by number (0-based indexing)
- Takes monitor number as argument (0 = first monitor, 1 = second monitor, etc.)
- If the specified monitor doesn't exist, the function returns without action

#### tagmonbynum(const Arg *arg) 
- Moves the current window to a specific monitor by number (0-based indexing)
- Similar to focusmonbynum but for moving windows instead of just focusing

### 2. New Keybindings in config.h

#### Focus Monitor by Number:
- `MODKEY + Alt + 1` → Focus monitor 0 (first monitor)
- `MODKEY + Alt + 2` → Focus monitor 1 (second monitor) 
- `MODKEY + Alt + 3` → Focus monitor 2 (third monitor)
- `MODKEY + Alt + 4` → Focus monitor 3 (fourth monitor)
- `MODKEY + Alt + 5` → Focus monitor 4 (fifth monitor)

#### Move Window to Monitor by Number:
- `MODKEY + Alt + Shift + 1` → Move current window to monitor 0
- `MODKEY + Alt + Shift + 2` → Move current window to monitor 1
- `MODKEY + Alt + Shift + 3` → Move current window to monitor 2
- `MODKEY + Alt + Shift + 4` → Move current window to monitor 3
- `MODKEY + Alt + Shift + 5` → Move current window to monitor 4

## Usage

The existing Left/Right arrow key functionality remains unchanged:
- `MODKEY + Left` → Focus previous monitor (cyclical)
- `MODKEY + Right` → Focus next monitor (cyclical)
- `MODKEY + Shift + Left` → Move window to previous monitor
- `MODKEY + Shift + Right` → Move window to next monitor

The new functionality adds direct access:
- Use `MODKEY + Alt + [1-5]` to jump directly to a specific monitor  
- Use `MODKEY + Alt + Shift + [1-5]` to move the current window to a specific monitor

## Notes
- Monitor numbering is 0-based internally but the keybindings use 1-5 for user convenience
- If you try to focus/move to a monitor that doesn't exist, nothing happens
- The functions safely handle cases where there are fewer monitors than requested
- This enhancement is backward compatible - existing functionality remains unchanged
