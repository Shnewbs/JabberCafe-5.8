# Rev22 music controls

The former bottom audio strip is now a configurable card. See INTERFACE-GUIDE.md
for its layouts, independent sizing, close/reopen behavior and artist-name setup.
The saved-mix preparation and DJ workflows below are retained.

# JabberCafe — DJ Booth / rev000022

## Your mixes at the booth
Right-click the DJ booth furniture, then open **My Tracks**. Touch players can
also tap the booth; the nearby Interact action opens the same panel.

**Saved mixes** now lists your named Studio projects from the existing local
project folder. It also includes the current open session, using its latest
in-memory title and edits. Opening this list does not publish anything, switch
the open Studio project, or replace a previous finished track.

Select the mix you want, choose **Full song / arrangement** or **Selected pattern
only**, then press **Prepare selected mix**. The picker starts with that mix's
saved Pattern/Song setting. Preparation renders a fixed copy from that exact
selection, not whichever unrelated project happens to be open in Studio.

When preparation finishes, the panel switches to **Ready for booth** and selects
the new version. Press **Preview for me** to hear it privately, or **Set for line**,
then open **DJ Line** and press **Join line**. The DJ Line tab names the finished
track chosen for your next turn. Preparation does not join the line or start room
music automatically. Your avatar walks to an accessible booth tile before the
turn starts. Each track plays once and releases the turn.

Returning to the booth, switching between the two lists, or pressing Refresh
rereads the local libraries. Existing finished tracks are retained. Duplicate
project names are separate entries selected by ID. A readable previous-good
project backup is labelled in the saved list. Missing finished audio remains
visible but cannot be previewed or queued. Missing source sounds, silent mixes,
and write errors produce a status message instead of an apparently completed
track.

An imported WAV used as a Studio sound is an instrument/sample, not a finished
booth song. Put it in a mix and prepare that mix for the booth. This update does
not add arbitrary long-WAV song import. No files are uploaded.

## Listening controls
The bottom bar has separate **Game** and **Room** controls. Game affects all
audio. Room affects only booth music; it does not mute Studio or private
previews. Mute keeps the previous slider setting. **Stop listening** silences
room music for you without stopping, rewinding or removing the performance.
**Listen** returns to the current playback position. Preferences are saved.
Private previews and Studio audio duck the room music locally.

## DJ turns
The line holds players, not an interruptible public playlist. There is one slot
per player and one track per turn. Set for line can change a waiting selection
without changing its place. It cannot replace an active performance. Leave line
removes a waiting turn; End my turn ends the active local DJ's performance.
Rejoin at the back to play another track. Muting does not change your turn.

Each placed booth has its own queue state. Only one booth performs into room
music at a time. Removing a booth, leaving the room or blocking its approach
cleans up the affected local turn. The offline build has one local player;
connected visitor queues and synchronized online performances are not present.

## Local storage and limits
Studio projects: `user://offline/studio/projects/`
Current session: `user://offline/studio/project.json`
Finished versions: `user://offline/booth_tracks/`

The existing user-data directory and project/track formats are unchanged.
A prepared version is a non-looping stereo 44.1 kHz PCM16 WAV with metadata,
checksum, and source notes. Up to 32 finished versions, each up to 180 seconds,
are supported. Source edits do not change a prepared version. Preparing another
version adds a copy. Game volume and personal Room listening settings are not
baked into the finished audio. Render mode and source notes are frozen at start.

Back up your complete user-data folder before replacing a development build.
Desktop ZIPs must be extracted completely; keep JabberCafe.pck with the executable.
