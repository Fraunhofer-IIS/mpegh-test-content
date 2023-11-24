# MPEG-H transport layer test content

This directory contains test content for the verification of a transport layer implementation handled the MPEG-H related parts.

> The files are very short and even though they are playable, they are not meant for playback.

The package contains encodings of several CICPs as indicated by the subfolder name as well as 1 item showcasing an MPEG-H configuration change.
Each folder contains transport stream and mp4 files with different encoding configurations as indicated by the filenames as well as the folder structure. For example,

`CICP_01/mp4/baseline/32kbps/mpegh_cicp_01_baseline_32kbps.mp4`

contains CICP 1 encoded using the MPEG-H Baseline Profile at 32kbps per signal. The folder also contains a fragmented version of each mp4. These files are marked using the `_fragmented` suffix.

Next to the mp4 files, files named `<mp4_file_name>.printmp4.txt` can be found. These files contain a dump of the mp4 box structure of the corresponding mp4 file.

Similarly, an example for a transport stream files could look like this:

`CICP_13/ts/multi/baseline/32kbps/mpegh_cicp_13_baseline_32kbps_multi_5.ts`

This file contains a CICP 13 encoding with MPEG-H Baseline profile at 32kbps per signal packaged s.t. (at most) 5 MPEG-H access units are contained in each PES packet.

## Detailed folder structure
On the top level this folder contains the following subfolders:

* `CICP_XY`: Contains MPEG-H encodings of CICP XY.
* `ConfigChange`: Contains MPEG-H encodings with configuration changes. The configuration changes from CICP 2 to 13 to 6.

Each of the folders listed above contains the following substructure:
* `mp4`: Contains MP4 files in various different flavors (see subfolders)
  * `baseline` / `lc_baseline_compatible`: Determines which MPEG-H Profile was used to encode the content.
    * `32kbps` : Indicates, that the content was encoded with 32kbps per signal.
      * `<filename>.mp4`: Contains the MPEG-H bitstream in a plain MP4 file.
      * `<filename>_fragmented.mp4`: Contains the same bitstream as `<filename>.mp4`, but as a fragmented MP4 file.
      * `<filename>.printmp4.txt`: Contains a dump of the MP4 box structure of the corresponding MP4 file.
* `ts`: Contains TS files in various different flavors (see subfolders)
  * `single` / `multi` / `cont` : Determines how MPEG-H access units are packaged into TS PES packets.<br>
  `single` means that exactly 1 access unit is put into each PES packet.<br>
  `multi` means that an integer number of access units are packaged into each PES packet. The number of access units packaged into each PES packet can be found in the filename, e.g. TS files ending with `_multi_5.ts` contain (at most) 5 access units per PES packet.<br>
  `cont` means, that a fixed number of bytes is packaged into each PES packet. This typically results in a non-integer number of access units in a PES packet. The number of bytes per each PES packet can be found in the filename, e.g. TS files ending with `_cont_2000.ts` contain (at most) 2000 bytes per PES packet.
    * `baseline` / `lc_baseline_compatible`: Determines which MPEG-H Profile was used to encode the content.
      * `32kbps` : Indicates, that the content was encoded with 32kbps per signal.
        * `<filename>.ts`: Contains the MPEG-H bitstream in a transport stream file.