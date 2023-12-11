# mpegh-test-content

A repository with MPEG-H Audio test bitstreams, primarily aimed to be used for:
- testing [MPEG-H decoding][mpeghdecoder] and [MPEG-H UI manager][mpeghdecoder]
- testing [IEC61937-13][iec] encoding and decoding
- testing of transport layer implementations that handle MPEG-H Audio

> **NOTE: this repository is configured to use the [Git Large File Storage (LFS)][gitlfs] extension.**
> 
> Git LFS extension needs to be installed to work with this repository. Please follow the install instructions [here][gitlfsinstall].

## Overview

The following test files are part of this repository:

- TRI_Fileset_17_514H_D1_D2_D3_O1_24bit1080p50.mp4
  - 3D audio mix (music) with three additional mono commentaries in a switch group and one dynamic object. Three presets with interactivity.
  - audio track
    - codec: mhm1 / MPEG-H Audio
    - channel bed: 5.1+4
    - 3 mono objects
    - 1 dynamic object
  - video track
    - codec: hevc / H265
    - resolution: 1920x1080
    - frame rate: 50.00
- TRI_Fileset_17_514H_D1_D2_D3_O1_24bit2160p50.audio.mp4
  - audio only version of the item above
- [transport layer test content](./transport_layer_test_content) folder
  - collection of test items for verification of a transport layer implementation (see respective [readme](./transport_layer_test_content/readme.md))

## Links

- [www.mpegh.com](https://mpegh.com/)
- [Fraunhofer IIS MPEG-H Audio](https://www.iis.fraunhofer.de/en/ff/amm/broadcast-streaming/mpegh.html)

## License

Please see the [LICENSE.txt](./LICENSE.txt) file for the terms of use that apply to the content in this repository.

[mpeghdecoder]: https://github.com/Fraunhofer-IIS/mpeghdec
[iec]: https://github.com/Fraunhofer-IIS/iec61937-13
[gitlfs]: https://git-lfs.com
[gitlfsinstall]: https://docs.github.com/en/repositories/working-with-files/managing-large-files/installing-git-large-file-storage

