# ffmpeg Install Package
Ease-of-use binary executable installers for Windows 7 and up (64bit/x64).

## About
`ffmpeg` is an open source command line multimedia framework to encode, decode, transcode, convert etc. a wide array of video formats. [Learn more here.](https://ffmpeg.org/about.html) For use refer to the [official documentation.](https://ffmpeg.org/documentation.html).

The build contained in this installer is obtained from [gyan.](https://www.gyan.dev/ffmpeg/builds/) No tampering or modification has occured. Simply packaged into an installer. Rather than compile my own ffmpeg build I opted to use one that is already available.

> [!NOTE]
> Windows 8 and later has a "SmartScreen" feature that blocks software that it doesn't trust. Naturally since it has never seen this software, it may warn you. The installer is safe as is the contained ffmpeg build. If you are unsure, you may cross check the ffmpeg binary with gyans archives (`get-filehash`) or upload to virus total. You may need to click "Run anyway" when the warning appears.

gyan makes a few notes regarding these builds:

> [gyan] hosts packages containing binaries of ffmpeg, ffprobe and ffplay. These are compatible with Windows 7 and above. They may work on Windows Vista but that hasn't been tested. If you're downloading ffmpeg to support features in a program such as Krita or Blender, get the release essentials build. All builds are 64-bit.

Because ffmpeg is built for 64-bit only, this installer is 64-bit only. Attempting to run it on 32-bit will fail.

Builds from gyan are as follows:

- _git full_ - built from master branch with a large set of libraries
- _git essentials_ - built from master branch with commonly-used libraries
- _release full_ - built from latest release branch with a large set of libraries
- _release essentials_ - built from latest release branch with commonly-used libraries

This repo houses installers for *release full* and *release essentials*. I make an effort to keep it updated by checking every 30 days. If there is no updated build, there is no update here. Updates can be as needed (security, critical bugs).

Why use an installer?

- Installs and uninstalls cleanly. Just like manually upacking, this leaves no traces.
- Automatically adds `ffmpeg` to PATH. No need to add this yourself.
- Fast and simple GUI for those not 100% comfortable with command line.
- Can be used for mass deployment to streamline software installation via scripting.
  - From an elevated script `> ffmpeg.msi /qr`

Installer versioning is in format: MAJOR.MINOR.BUILD.YearMonthDay (EX: 4.4.0.20210101).

## Alternative Sources
If you need more frequent updating, please use gyan's git `.7z` archives direct from the website. These are nightly builds. Gyan also publishes the release build to `winget` and the Chocolately community publishes their own build if you prefer command line installation from archives.

## Hardware Support
gyan builds are compiled with hardware acceleration enabled. Supporting the following libraries:

- AMD Advanced Media Framework
  - `--enable-amf`
- Nvidia CUDA, CUVID, NVDEC, & NVENC
  - `--enable-cuda-llvm --enable-cuvid --enable-ffnvcodec --enable-nvdec --enable-nvenc`
- Intel Quick Sync Video
  - `--enable-libmfx`
- D3D11VA
  - `--enable-d3d11va`
- DXVA2
  - `--enable-dxva2`

Refer to the `README.txt` file for more information.

## Issue Reporting
Issues regarding ffmpeg should be directed elsewhere. Issues are open *only* for install and uninstall process.
