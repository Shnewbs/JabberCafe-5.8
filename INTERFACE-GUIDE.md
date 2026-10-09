# JabberCafe rev22 — Your interface, your display

## Start here

The music controls now open as a slim, bottom-right card. Press **⋯** on the
card, or **Settings → Interface → Customize panels**, to change the layout.
**Settings → Display → Interface & adaptive graphics** opens the graphics page.

## Music layouts

Choose **Slim card**, **Compact card**, **Expanded card**, or **Wide bar**.
The defaults are 280 × 264, 348 × 282, 464 × 300 and 940 × 184 logical pixels.
The selected layout determines the arrangement, not a forced physical screen size.
A smaller window may temporarily constrain the panel, with scrolling/reflow.

**×** closes the card. **−** minimizes it. Both leave a small **♫ Music** button
at the selected dock to reopen it. Neither action changes playback, volume,
muting, or the DJ's turn. Visibility/minimize preferences persist.

The two volume controls retain their roles: **Game** controls all game audio;
**Room** controls only DJ booth music. **Listen** rejoins the current room track;
**Stop** stops personal listening, not the room performance. Mute keeps the
previous slider value. Private previews and Studio are separate from Room audio.

## Independent panel sizing

The panel picker exposes Music widget, Studio, DJ Booth, My Mixes, Settings,
Rooms and Control mapping. Each keeps its own width, height, control scale,
text scale and dock/free position. A change to one is not copied to the others.

- **Follow global control size** uses Settings → Display → Interface size.
  Turn it off to use that panel's own 75–160% control scale.
- **Text size** is an additional 85–150% adjustment for that panel's text.
- **Width/height** change the container; controls reflow or scroll rather than
  stretching the whole interface. Content minimums still apply.
- **Dock** offers all four corners, center, and a free position with X/Y fields.
  Free coordinates are percentages of the available placement area.

To drag the music card, disable **Lock widget position / resize handles**, or
press **Move / resize**. Drag its title to move it, its side edges to change
width, and its bottom edge/corner to change height/both dimensions. Near a corner,
a completed move snaps to that dock. Escape cancels an active mouse drag; a
canceled touch or application focus loss also cancels without saving the move.
Relock it afterwards to prevent accidental changes. Buttons/fields provide
alternatives to dragging.

The regular windows remain resizable by their title bar and borders and remember
changes on close/reopen. **Reset this panel**, **Reset all panels**, and **Undo
reset** are available. Monitor/window changes clamp panels into the available
area without replacing preferred dimensions; enlarging the window restores them.
These settings apply to existing panels, not a new chat or furniture-card system.

## Titles and artist names

Track title and artist use separate single-line fields. A field that fits stays
still. Overflowing text pauses, scrolls to the end, pauses, and returns. Scrolling
speed is 10–80 logical pixels/second. Disable scrolling or enable **Reduced
motion** for static, truncated text with the full value available as a tooltip.

Set **Artist name for newly prepared booth tracks** in Interface settings.
The title, audio and artist are frozen when preparing a version. Existing tracks
retain their previous creator credit (including “You” from earlier revisions).
Changing the name does not rewrite finished tracks or change another DJ's turn.

## Display output versus render scale

Windowed mode draws at the actual client-window size. **Fit desktop on launch**
starts at about 86% of the current desktop's usable area. Turn it off to use the
remembered window dimensions. **Native-resolution fullscreen** uses the selected
monitor's native desktop resolution. The monitor picker and **Fit window to
current desktop** are available on desktop builds.

**Automatic display / DPI sizing** uses the platform's screen information with
bounded fallbacks for high-resolution displays. It also keeps a usable logical
area in smaller windows. Turn it off for manual, pixel-sized UI density. The
global/per-panel controls remain available either way. Automatic DPI detection
varies by OS/driver; the manual switch is intentional.

Only the 3D room's rendering resolution changes with the graphics profile.
Text and controls still render through the full-output canvas. For example,
2560 × 1440 output at a 75% 3D scale renders the room at 1920 × 1080, not the UI.
The room camera projection, furniture picking and stored panel geometry do not
change with 3D scale. The game does not change the OS desktop resolution.

## Graphics profiles

**Auto** starts at its selected maximum, then measures render timing. It warms
up, requires sustained load, changes the 3D scale in bounded 5% steps, and waits
between changes. It restores detail only after sustained headroom. Set its
minimum/maximum (50–100%) and target (30–240 FPS). The effective target respects
an existing lower frame cap and requested V-Sync refresh limit.

When GPU timing is available it is preferred to frame rate alone. Without it,
Auto permits at most two bounded frame-time probes. If reducing resolution
makes no meaningful improvement, it restores the previous scale and holds rather
than repeatedly degrading the picture. Loading, audio-render work, inactive
windows and open editing dialogs pause the policy. A single stall is ignored.
No hardware brand or “integrated GPU” label forces a low preset.

**Quality** is fixed native 100%, **Balanced** fixed 85%, **Performance** fixed
70%, and **Custom** fixes the chosen 50–100% scale. Compatibility uses bilinear
upscaling; MSAA is off below native scale, and 2× at native. The diagnostics
show adapter, output and 3D dimensions, UI density, effective target and timing
status. These are targets and measurements, not guaranteed frame rates.

Frame cap and V-Sync remain in Settings → Display. Auto does not change the
player's text size, panels, FPS cap, audio settings, or save data. A CPU-limited
workload can still require other optimizations rather than lower resolution.

## Saves and platform notes

The application/save-folder identity is unchanged. Older preferences gain new
defaults while retaining audio, avatar, room and frame settings. Nested UI and
display profiles use schema 1 with bounded values and the existing validated
save/backup path. Back up your user-data folder before updating a test build.

Right-click DJ booth → My Tracks still lists saved mixes and ready-for-booth
versions separately. Publishing, queues, private preview, one track per turn,
and Studio project editing remain the rev21 workflows. The game remains offline.
See the validation report for the exact test and platform coverage of this build.
