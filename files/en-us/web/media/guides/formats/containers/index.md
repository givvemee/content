---
title: Media container formats (file types)
slug: Web/Media/Guides/Formats/Containers
page-type: guide
sidebar: mediasidebar
---

A **media container** is a file format that encapsulates one or more media streams (such as audio or video) along with metadata, enabling them to be stored and played back together.
The format of audio and video media files is defined by multiple components, including the audio and/or video codecs used, the media container format (or file type), and optionally other elements such as subtitle codecs or metadata.
In this guide, we'll look at the container formats used most commonly on the web, covering basics about their specifications as well as their benefits, limitations, and ideal use cases.

[WebRTC](/en-US/docs/Web/API/WebRTC_API) does not use a container at all.
Instead, it streams the encoded audio and video tracks directly from one peer to another using {{domxref("MediaStreamTrack")}} objects to represent each track.
See [Codecs used by WebRTC](/en-US/docs/Web/Media/Guides/Formats/WebRTC_codecs) for information about codecs commonly used for making WebRTC calls, as well as browser compatibility information around codec support in WebRTC.

## Common container formats

While there are a vast number of media container formats, the ones listed below are the ones you are most likely to encounter.
Some support only audio while others support both audio and video.
The MIME types and extensions for each are listed. The most commonly used containers for media on the web are probably MPEG-4 Part-14 (MP4) and Web Media File (WEBM). However, you may also encounter Ogg, WAV, AVI, MOV, and other formats.
Not all of these are broadly supported by browsers; some combinations of container and codec are sometimes given their own file extensions and MIME types as a matter of convenience, or because of their ubiquity.
For example, an Ogg file with only an Opus audio track is sometimes referred to as an Opus file, and might even have the extension `.opus`.
But it's still actually just an Ogg file.

In some cases, a particular codec becomes so ubiquitous that its usage is treated as a unique format. A prime example is the MP3 audio file, which isn't stored in a conventional container. Instead, an MP3 file is essentially a stream of MPEG-1 Audio Layer III-encoded frames, often accompanied by metadata such as ID3 tags. These files use the `audio/mpeg` MIME type and the `.mp3` extension.

### Index of media container formats (file types)

To learn more about a specific container format, find it in this list and click through to the details, which include information about what the container is typically useful for, what codecs it supports, and which browsers support it, among other specifics.

<table class="standard-table">
  <thead>
    <tr>
      <th scope="row">Codec name (short)</th>
      <th scope="col">Full codec name</th>
      <th scope="col">Browser compatibility</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row"><a href="#3gp">3GP</a></th>
      <td>Third Generation Partnership</td>
      <td>Firefox for Android</td>
    </tr>
    <tr>
      <th scope="row"><a href="#adts">ADTS</a></th>
      <td>Audio Data Transport Stream</td>
      <td>
        <p>Firefox</p>
        <p>Available only if available on the underlying operating system's media framework.
        </p>
      </td>
    </tr>
    <tr>
      <th scope="row"><a href="#flac">FLAC</a></th>
      <td>Free Lossless Audio Codec</td>
      <td>All browsers.</td>
    </tr>
    <tr>
      <th scope="row"><a href="#mpegmpeg-2">MPEG / MPEG-2</a></th>
      <td>Moving Picture Experts Group (1 and 2)</td>
      <td>—</td>
    </tr>
    <tr>
      <th scope="row"><a href="#mpeg-4_mp4">MPEG-4 (MP4)</a></th>
      <td>Moving Picture Experts Group 4</td>
      <td>All browsers.</td>
    </tr>
    <tr>
      <th scope="row"><a href="#ogg">Ogg</a></th>
      <td>Ogg</td>
      <td>All browsers.</td>
    </tr>
    <tr>
      <th scope="row"><a href="#quicktime">QuickTime (MOV)</a></th>
      <td>Apple QuickTime movie</td>
      <td>Only older versions of Safari, plus other browsers that supported Apple's QuickTime plugin</td>
    </tr>
    <tr>
      <th scope="row"><a href="#webm">WebM</a></th>
      <td>Web Media</td>
      <td>All browsers.</td>
    </tr>
  </tbody>
</table>

Unless otherwise specified, both mobile and desktop browser compatibility is implied if a browser is listed here.
Support is also implied only for the container itself, not for any specific codecs.

### 3GP

The **3GP** or **3GPP** media container is used to encapsulate audio and/or video that is specifically intended for transmission over cellular networks for consumption on mobile devices.
The format was designed for use on 3G mobile phones, but can still be used on more modern phones and networks.
However, the improved bandwidth availability and increased data caps on most networks has reduced the need for the 3GP format.
However, this format is still used for slower networks and for lower-performance phones.

This media container format is derived from the ISO Base Media File Format and MPEG-4, but is specifically streamlined for lower bandwidth scenarios.

| Audio         | Video         |
| ------------- | ------------- |
| `audio/3gpp`  | `video/3gpp`  |
| `audio/3gpp2` | `video/3gpp2` |
| `audio/3gp2`  | `video/3gp2`  |

These MIME types are the fundamental types for the 3GP media container; other types may be used depending on the specific codec or codecs in use.
In addition, you can [add the `codecs` parameter](/en-US/docs/Web/Media/Guides/Formats/codecs_parameter#iso_base_media_file_format_mp4_quicktime_and_3gp) to the MIME type string to indicate which codecs are used for the audio and/or video tracks, and to optionally provide details about the profile, level, and/or other codec configuration specifics.

<table class="standard-table">
  <caption>
    Video codecs supported by 3GP
  </caption>
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">Codec</th>
      <th colspan="4" scope="col" style="text-align: center">
        Browser support
      </th>
    </tr>
    <tr>
      <th scope="col">Chrome</th>
      <th scope="col">Edge</th>
      <th scope="col">Firefox</th>
      <th scope="col">Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">AVC (H.264)</th>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">H.263</th>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">MPEG-4 Part 2 (MP4v-es)</th>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">VP8</th>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>

<table class="standard-table">
  <caption>
    Audio codecs supported by 3GP
  </caption>
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">Codec</th>
      <th colspan="4" scope="col" style="text-align: center">
        Browser support
      </th>
    </tr>
    <tr>
      <th scope="col">Chrome</th>
      <th scope="col">Edge</th>
      <th scope="col">Firefox</th>
      <th scope="col">Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">AMR-NB</th>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">AMR-WB</th>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">AMR-WB+</th>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">AAC-LC</th>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">HE-AAC v1</th>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">HE-AAC v2</th>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">MP3</th>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>

### ADTS

**Audio Data Transport Stream** (**ADTS**) is a container format specified by MPEG-4 Part 3 for audio data, intended to be used for streamed audio, such as for Internet radio.
It is, essentially, an almost bare stream of AAC audio data, comprised of ADTS frames with a minimal header.

| Audio        |
| ------------ |
| `audio/aac`  |
| `audio/mpeg` |

The MIME type used for ADTS depends on what kind of audio frames are contained within.
If ADTS frames are used, the `audio/aac` MIME type should be used.
If the audio frames are in MPEG-1/MPEG-2 Audio Layer I, II, or III format, the MIME type should be `audio/mpeg`.

<table class="standard-table">
  <caption>
    Audio codecs supported by ADTS
  </caption>
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">Codec</th>
      <th colspan="4" scope="col" style="text-align: center">
        Browser support
      </th>
    </tr>
    <tr>
      <th scope="col">Chrome</th>
      <th scope="col">Edge</th>
      <th scope="col">Firefox</th>
      <th scope="col">Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">AAC</th>
      <td></td>
      <td></td>
      <td>Yes</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">MP3</th>
      <td></td>
      <td></td>
      <td>Yes</td>
      <td></td>
    </tr>
  </tbody>
</table>

Firefox support for AAC relies upon the operating system's media infrastructure, so it is available as long as the OS supports it.

### FLAC

The **Free Lossless Audio Codec** (**FLAC**) is a lossless audio codec; there is also an associated container format, also called FLAC, that can contain this audio.
The format is not encumbered by any patents, so its use is safe from interference.
FLAC files can only contain FLAC audio data.

| Audio                         |
| ----------------------------- |
| `audio/flac`                  |
| `audio/x-flac` (non-standard) |

<table class="standard-table">
  <caption>
    Audio codecs supported by FLAC
  </caption>
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">Codec</th>
      <th colspan="4" scope="col" style="text-align: center">
        Browser support
      </th>
    </tr>
    <tr>
      <th scope="col">Chrome</th>
      <th scope="col">Edge</th>
      <th scope="col">Firefox</th>
      <th scope="col">Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">FLAC</th>
      <td></td>
      <td></td>
      <td>Yes</td>
      <td></td>
    </tr>
  </tbody>
</table>

### MPEG/MPEG-2

The **[MPEG-1](https://en.wikipedia.org/wiki/MPEG-1)** and **[MPEG-2](https://en.wikipedia.org/wiki/MPEG-2)** file formats are essentially identical.
Created by the Moving Picture Experts Group (MPEG), these formats are widely used in physical media, including as the format of the video on DVD media.

On the internet, perhaps the most common application of the MPEG standard is for [MPEG-1 Audio Layer III](https://en.wikipedia.org/wiki/MPEG-1), commonly known as MP3, sound data. These MP3 files are wildly popular with digital music devices around the world, even though MPEG-1 and MPEG-2, as a whole, are not widely used in other web content.

The main differences between MPEG-1 and MPEG-2 take place in the media data formats rather than the container format.
MPEG-1 was introduced in 1992; MPEG-2 was introduced in 1996.

| Audio        | Video        |
| ------------ | ------------ |
| `audio/mpeg` | `video/mpeg` |

<table class="standard-table">
  <caption>
    Video codecs supported by MPEG-1 and MPEG-2
  </caption>
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">Codec</th>
      <th colspan="4" scope="col" style="text-align: center">
        Browser support
      </th>
    </tr>
    <tr>
      <th scope="col">Chrome</th>
      <th scope="col">Edge</th>
      <th scope="col">Firefox</th>
      <th scope="col">Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">MPEG-1 Part 2</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">MPEG-2 Part 2</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
  </tbody>
</table>

<table class="standard-table">
  <caption>
    Audio codecs supported by MPEG-1 and MPEG-2
  </caption>
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">Codec</th>
      <th colspan="4" scope="col" style="text-align: center">
        Browser support
      </th>
    </tr>
    <tr>
      <th scope="col">Chrome</th>
      <th scope="col">Edge</th>
      <th scope="col">Firefox</th>
      <th scope="col">Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">MPEG-1 Audio Layer I</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">MPEG-1 Audio Layer II</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">MPEG-1 Audio Layer III (MP3)</th>
      <td></td>
      <td></td>
      <td>Yes</td>
      <td></td>
    </tr>
  </tbody>
</table>

### MPEG-4 (MP4)

**[MPEG-4](https://en.wikipedia.org/wiki/MPEG-4)** (**MP4**) is the latest version of the MPEG file format.
There are two versions of the format, defined in parts 1 and 14 of the specification.
MP4 is a popular container today, as it supports several of the most-used codecs and is broadly supported.

The original MPEG-4 Part 1 file format was introduced in 1999; the version 2 format, defined in Part 14, was added in 2003.
The MP4 file format is derived from the [ISO base media file format](https://en.wikipedia.org/wiki/ISO_base_media_file_format), which is directly derived from the [QuickTime file format](https://en.wikipedia.org/wiki/QuickTime_File_Format) developed by [Apple](https://www.apple.com/).

When specifying the MPEG-4 media type (`audio/mp4` or `video/mp4`), you can [add the `codecs` parameter](/en-US/docs/Web/Media/Guides/Formats/codecs_parameter#iso_base_media_file_format_mp4_quicktime_and_3gp) to the MIME type string to indicate which codecs are used for the audio and/or video tracks, and to optionally provide details about the profile, level, and/or other codec configuration specifics.

| Audio       | Video       |
| ----------- | ----------- |
| `audio/mp4` | `video/mp4` |

These MIME types are the fundamental types for the MPEG-4 media container; other MIME types may be used depending on the specific codec or codecs in use within the container.
In addition, you can [add the `codecs` parameter](/en-US/docs/Web/Media/Guides/Formats/codecs_parameter#iso_base_media_file_format_mp4_quicktime_and_3gp) to the MIME type string to indicate which codecs are used for the audio and/or video tracks, and to optionally provide details about the profile, level, and/or other codec configuration specifics.

<table class="standard-table">
  <caption>
    Video codecs supported by MPEG-4
  </caption>
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">Codec</th>
      <th colspan="4" scope="col" style="text-align: center">
        Browser support
      </th>
    </tr>
    <tr>
      <th scope="col">Chrome</th>
      <th scope="col">Edge</th>
      <th scope="col">Firefox</th>
      <th scope="col">Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">AVC (H.264)</th>
      <td></td>
      <td></td>
      <td>
        <p>Yes</p>
        <p>
          Firefox support for H.264 relies upon the operating system's media
          infrastructure, so it is available as long as the OS supports it.
        </p>
      </td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">AV1</th>
      <td></td>
      <td></td>
      <td>
        <p>Yes</p>
        <p>Firefox support for AV1 is disabled on Windows on ARM (enable by setting the preference <code>media.av1.enabled</code> to <code>true</code>).</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">H.263</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">MPEG-4 Part 2 Visual</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">VP9</th>
      <td></td>
      <td></td>
      <td>Yes</td>
      <td></td>
    </tr>
  </tbody>
</table>

<table class="standard-table">
  <caption>
    Audio codecs supported by MPEG-4
  </caption>
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">Codec</th>
      <th colspan="4" scope="col" style="text-align: center">
        Browser support
      </th>
    </tr>
    <tr>
      <th scope="col">Chrome</th>
      <th scope="col">Edge</th>
      <th scope="col">Firefox</th>
      <th scope="col">Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">AAC</th>
      <td></td>
      <td></td>
      <td>
        <p>Yes</p>
        <p>Firefox support for H.264 relies upon the operating system's media infrastructure, so it is available as long as the OS supports it.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">FLAC</th>
      <td></td>
      <td></td>
      <td>Yes</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">MPEG-1 Audio Layer III (MP3)</th>
      <td></td>
      <td></td>
      <td>Yes</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">Opus</th>
      <td></td>
      <td></td>
      <td>Yes</td>
      <td></td>
    </tr>
  </tbody>
</table>

### Ogg

The [Ogg](https://en.wikipedia.org/wiki/Ogg) container format is a free and open format maintained by the [Xiph.org Foundation](https://www.xiph.org/).
The Ogg framework also defines patent unencumbered media data formats, such as the Theora video codec and the Vorbis and Opus audio codecs.
[Xiph.org documents about the Ogg format](https://xiph.org/ogg/) are available on their website.

While Ogg has been around for a long time, it has never gained the wide support needed to make it a good first choice for a media container.
You are typically better off using WebM, though there are times when Ogg is useful to offer, such as when you wish to support older versions of Firefox and Chrome which don't yet support WebM.
For example, Firefox 3.5 and 3.6 support Ogg, but not WebM.

You can get more information about Ogg and its codecs in the [Theora Cookbook](https://archive.flossmanuals.net/ogg-theora/).

| Audio       | Video       |
| ----------- | ----------- |
| `audio/ogg` | `video/ogg` |

The `application/ogg` MIME type can be used when you don't necessarily know whether the media contains audio or video.
If at all possible, you should use one of the specific types, but fall back to `application/ogg` if you don't know the content format or formats.

You can also [add the `codecs` parameter](/en-US/docs/Web/Media/Guides/Formats/codecs_parameter) to the MIME type string to indicate which codecs are used for the audio and/or video tracks, and to optionally further describe the track media formats.

<table class="standard-table">
  <caption>
    Video codecs supported by Ogg
  </caption>
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">Codec</th>
      <th colspan="4" scope="col" style="text-align: center">
        Browser support
      </th>
    </tr>
    <tr>
      <th scope="col">Chrome</th>
      <th scope="col">Edge</th>
      <th scope="col">Firefox</th>
      <th scope="col">Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Theora</th>
      <td></td>
      <td></td>
      <td>Yes</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">VP8</th>
      <td></td>
      <td></td>
      <td>Yes</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">VP9</th>
      <td></td>
      <td></td>
      <td>Yes</td>
      <td></td>
    </tr>
  </tbody>
</table>

<table class="standard-table">
  <caption>
    Audio codecs supported by Ogg
  </caption>
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">Codec</th>
      <th colspan="4" scope="col" style="text-align: center">
        Browser support
      </th>
    </tr>
    <tr>
      <th scope="col">Chrome</th>
      <th scope="col">Edge</th>
      <th scope="col">Firefox</th>
      <th scope="col">Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">FLAC</th>
      <td></td>
      <td></td>
      <td>Yes</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">Opus</th>
      <td>Yes</td>
      <td>Yes</td>
      <td>Yes</td>
      <td>Yes</td>
    </tr>
    <tr>
      <th scope="row">Vorbis</th>
      <td></td>
      <td></td>
      <td>Yes</td>
      <td>Yes</td>
    </tr>
  </tbody>
</table>

> [!WARNING]
> Ogg Opus audio files longer than 12h 35m 39s are truncated and exhibit seeking issues when played on Firefox Linux 64 bit ([Firefox bug 1810378](https://bugzil.la/1810378)).

> [!NOTE]
> Safari 18.4+ (on macOS 15.4+, iOS 18.4+, iPadOS 18.4+, and visionOS 2.4+) added support for Opus and Vorbis codecs in Ogg containers.

### QuickTime

The **QuickTime** file format (**QTFF**, **QT**, or **MOV**) was created by Apple for use by its media framework of the same name.
The extension for these files, `.mov`, comes from the fact that the format was initially used for movies and was usually called the "QuickTime movie" format.
While QTFF served as the basis for the MPEG-4 file format, there are differences and the two are not quite interchangeable.

QuickTime files support any sort of time-based data, including audio and video media, text tracks, and so forth.
QuickTime files are primarily supported by macOS, but for a number of years, QuickTime for Windows was available to access them on Windows.
However, QuickTime for Windows is no longer supported by Apple as of early 2016, and _should not be used_, as there are known security concerns.
However, Windows Media Player now has integrated support for QuickTime version 2.0 and earlier files; support for later versions of QuickTime requires third-party additions.

On Mac OS, the QuickTime framework not only supported QuickTime format movie files and codecs, but supported a vast array of popular and specialty audio and video codecs, as well as still image formats.
Through QuickTime, Mac applications (including web browsers, through the QuickTime plugin or direct QuickTime integration) were able to read and write audio formats including AAC, AIFF, MP3, PCM, and Qualcomm PureVoice; and video formats including AVI, DV, Pixlet, ProRes, FLAC, Cinepak, 3GP, H.261 through H.265, MJPEG, MPEG-1 and MPEG-4 Part 2, Sorenson, and many more.

In addition, a number of third-party components are available for QuickTime, some of which add support for additional codecs.

Because QuickTime support is, for all intents and purposes, primarily available on Apple devices, it is no longer widely used on the internet.
Apple itself generally now uses MP4 for video.
In addition, the QuickTime framework has been deprecated on the Mac for some time, and is no longer available at all starting in macOS 10.15 Catalina.

| Video             |
| ----------------- |
| `video/quicktime` |

The `video/quicktime` MIME type is the fundamental type for the QuickTime media container.
It's worth noting that QuickTime (the media framework on Mac operating systems) supports a wide variety of containers and codecs, so it actually supports many other MIME types.

You can [add the `codecs` parameter](/en-US/docs/Web/Media/Guides/Formats/codecs_parameter#iso_base_media_file_format_mp4_quicktime_and_3gp) to the MIME type string to indicate which codecs are used for the audio and/or video tracks, and to optionally provide details about the profile, level, and/or other codec configuration specifics.

<table class="standard-table">
  <caption>
    Video codecs supported by QuickTime
  </caption>
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">Codec</th>
      <th colspan="4" scope="col" style="text-align: center">
        Browser support
      </th>
    </tr>
    <tr>
      <th scope="col">Chrome</th>
      <th scope="col">Edge</th>
      <th scope="col">Firefox</th>
      <th scope="col">Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">AVC (H.264)</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">Cinepak</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">Component Video</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">DV</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">H.261</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">H.263</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">MPEG-2</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">MPEG-4 Part 2 Visual</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">Motion JPEG</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">Sorenson Video 2</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">Sorenson Video 3</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
  </tbody>
</table>

<table class="standard-table">
  <caption>
    Audio codecs supported by QuickTime
  </caption>
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">Codec</th>
      <th colspan="4" scope="col" style="text-align: center">
        Browser support
      </th>
    </tr>
    <tr>
      <th scope="col">Chrome</th>
      <th scope="col">Edge</th>
      <th scope="col">Firefox</th>
      <th scope="col">Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">AAC</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">ALaw 2:1</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">Apple Lossless (ALAC)</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">HE-AAC</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">MPEG-1 Audio Layer III (MP3)</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">Microsoft ADPCM</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">µ-Law 2:1 (u-Law)</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
  </tbody>
</table>

### WAVE (WAV)

The **Waveform Audio File Format** (**WAVE**), usually referred to as WAV due to its filename extension being `.wav`, is a format developed by Microsoft and IBM to store audio bitstream data.

It is derived from the Resource Interchange File Format (RIFF), and as such is similar to other formats such as Apple's AIFF.
The WAV codec registry can be found at {{RFC(2361)}}; however, because nearly all WAV files use linear PCM, support for the other codecs is sparse.

The WAVE format was first released in 1991.

| Audio            |
| ---------------- |
| `audio/wave`     |
| `audio/wav`      |
| `audio/x-wav`    |
| `audio/x-pn-wav` |

The `audio/wave` MIME type is the standard type, and is preferred; however, the others have been used by various products over the years and may be used as well in some environments.

<table class="standard-table">
  <caption>
    Audio codecs supported by WAVE
  </caption>
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">Codec</th>
      <th colspan="4" scope="col" style="text-align: center">
        Browser support
      </th>
    </tr>
    <tr>
      <th scope="col">Chrome</th>
      <th scope="col">Edge</th>
      <th scope="col">Firefox</th>
      <th scope="col">Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">ADPCM (Adaptive Differential Pulse Code Modulation)</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">GSM 06.10</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">LPCM (Linear Pulse Code Modulation)</th>
      <td></td>
      <td></td>
      <td>Yes</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">MPEG-1 Audio Layer III (MP3)</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">µ-Law (u-Law)</th>
      <td></td>
      <td></td>
      <td>No</td>
      <td></td>
    </tr>
  </tbody>
</table>

### WebM

**[WebM](https://en.wikipedia.org/wiki/WebM)** (**Web Media**) is a format based on [Matroska](https://en.wikipedia.org/wiki/Matroska) which is designed specifically for use in modern web environments.
It's based entirely on free and open technologies and primarily uses codecs that are in turn free and open, although some products support other codecs in WebM containers as well.

WebM was first introduced in 2010 and is now widely supported.
Compliant implementations of WebM are required to support the VP8 and VP9 video codecs and the Vorbis and Opus audio codecs.
The WebM container format and its required codecs are all available under open licenses.
Any other codecs may require a license to use.

| Audio        | Video        |
| ------------ | ------------ |
| `audio/webm` | `video/webm` |

<table class="standard-table">
  <caption>
    Video codecs supported by WebM
  </caption>
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">Codec</th>
      <th colspan="4" scope="col" style="text-align: center">
        Browser support
      </th>
    </tr>
    <tr>
      <th scope="col">Chrome</th>
      <th scope="col">Edge</th>
      <th scope="col">Firefox</th>
      <th scope="col">Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">AV1</th>
      <td>Yes</td>
      <td>Yes</td>
      <td>
        <p>Yes</p>
        <p>Firefox support for AV1 was added to macOS in Firefox 66; for Windows in Firefox 67; and Firefox 68 on Linux.
          Firefox for Android does not yet support AV1; the implementation in Firefox is designed to use a secure process, which is not supported yet in Android.
        </p>
      </td>
      <td>Yes</td>
    </tr>
    <tr>
      <th scope="row">VP8</th>
      <td>Yes</td>
      <td>Yes</td>
      <td>Yes</td>
      <td>Yes</td>
    </tr>
    <tr>
      <th scope="row">VP9</th>
      <td>Yes</td>
      <td>Yes</td>
      <td>Yes</td>
      <td>Yes</td>
    </tr>
  </tbody>
</table>

<table class="standard-table">
  <caption>
    Audio codecs supported by WebM
  </caption>
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">Codec</th>
      <th colspan="4" scope="col" style="text-align: center">
        Browser support
      </th>
    </tr>
    <tr>
      <th scope="col">Chrome</th>
      <th scope="col">Edge</th>
      <th scope="col">Firefox</th>
      <th scope="col">Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Opus</th>
      <td>Yes</td>
      <td>Yes</td>
      <td>Yes</td>
      <td>Yes</td>
    </tr>
    <tr>
      <th scope="row">Vorbis</th>
      <td>Yes</td>
      <td>Yes</td>
      <td>Yes</td>
      <td>Yes</td>
    </tr>
  </tbody>
</table>

## Choosing the right container

There are a few factors to consider when selecting the best container or containers to use for your media.
The relative importance of each will depend on your needs, your license requirements, and the compatibility requirements of your target audience.

### Guidelines

When selecting the appropriate media format, your decision should depend on your intended usage. Playing back media is different from recording or editing it. For manipulation, uncompressed formats can improve performance, while lossless compression prevents the accumulation of noise from repeated recompression.

- If your target audience is likely to include users on mobile, especially on lower-end devices or on slow networks, consider providing a version of your media in a 3GP container with appropriate compression.
- If you have any specific encoding requirements, make sure the container you choose supports the appropriate codecs.
- If you want your media to be in a non-proprietary, open format, consider using one of the open container formats such as FLAC (for audio) or WebM (for video).
- If for any reason you are only able to provide media in a single format, choose a format that's available on the broadest selection of devices and browsers, such as MP3 (for audio) or MP4 (for video and/or audio).
- If your media is audio-only, choosing an audio-only format likely makes sense. See below for a comparison of the various audio-only formats.

### Container selection advice

The tables below offer suggested containers to use in various scenarios.
These are just suggestions.
Be sure to consider the needs of your application and your organization before selecting a container format.

#### Audio-only files

<table>
  <thead>
    <tr>
      <th>Need</th>
      <th>Format</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Compressed files for general-purpose playback</strong></td>
      <td><strong>MP3 (MPEG-1 Audio Layer III)</strong></td>
      <td>Widely compatible and recognized; uses lossy compression to provide a good balance between file size and audio quality.</td>
    </tr>
    <tr>
      <td rowspan="2"><strong>Lossless compression</strong></td>
      <td><strong>FLAC (Free Lossless Audio Codec)</strong></td>
      <td>Offers lossless compression, ensuring that the original audio remains intact while reducing file size.</td>
    </tr>
    <tr>
      <td><strong>ALAC (Apple Lossless Audio Codec)</strong></td>
      <td>Similar to FLAC but designed for Apple devices; it's a great fallback when working within the Apple ecosystem.</td>
    </tr>
    <tr>
      <td rowspan="2"><strong>Uncompressed files</strong></td>
      <td><strong>WAV (Waveform Audio File Format)</strong></td>
      <td>Contains uncompressed PCM audio, delivering the highest fidelity at the cost of larger file sizes.</td>
    </tr>
    <tr>
      <td><strong>AIFF (Audio Interchange File Format)</strong></td>
      <td>Comparable to WAV in terms of quality and file size, though it's often favored on Apple platforms.</td>
    </tr>
  </tbody>
</table>

Now that MP3's patents have all expired, the choice of audio file format has become much easier to make.
It's no longer necessary to choose between MP3's broad compatibility and the need to pay royalties when using it.

Unfortunately, neither of the relatively major lossless compression formats (FLAC and ALAC) are universally supported.
FLAC is the more broadly supported of the two, but is not supported by macOS without additional software installed, and is not supported at all on iOS.
If you need to offer lossless audio, you may need to provide both FLAC and ALAC to get close to universal compatibility.

#### Video files

<table>
  <thead>
    <tr>
      <th>Need</th>
      <th>Format</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>General purpose video (preferably open format)</strong></td>
      <td><strong>WebM</strong></td>
      <td>
        Designed for modern web usage, WebM is an open, royalty-free container that offers efficient compression and native support in most browsers.
      </td>
    </tr>
    <tr>
      <td><strong>General purpose video</strong></td>
      <td><strong>MP4</strong></td>
      <td>
        MP4 is the industry standard for video content, widely supported across devices and browsers.
      </td>
    </tr>
    <tr>
      <td><strong>High compression for slow connections</strong></td>
      <td><strong>3GP</strong></td>
      <td>
        Optimized for mobile devices and low-bandwidth environments, 3GP delivers acceptable video quality under constrained conditions.
      </td>
    </tr>
    <tr>
      <td><strong>Compatibility with older devices/browsers</strong></td>
      <td><strong>QuickTime</strong></td>
      <td>
        QuickTime is a legacy container originally popular on Apple platforms. It is still commonly produced by macOS video recording software.
      </td>
    </tr>
  </tbody>
</table>

These suggestions make a number of assumptions.
You should carefully consider the options before making a final decision, especially if you have a lot of media that will need to be encoded.
Very often, you would want to provide multiple fallback options for these formats—for example, MP4 fallback for WebM or 3GP, or AVI for QuickTime.

## Maximizing compatibility with multiple containers

To optimize compatibility, it's worth considering providing more than one version of media files, using the {{HTMLElement("source")}} element to specify each source within the {{HTMLElement("audio")}} or {{HTMLElement("video")}} element.
For example, you can offer an Ogg or WebM video as the first choice, with a fallback in MP4 format.
You could even choose to offer a retro-like QuickTime or AVI fallback for good measure.

To do this, you create a `<video>` (or `<audio>`) element with no [`src`](/en-US/docs/Web/HTML/Reference/Elements/video#src) attribute.
Then add child {{HTMLElement("source")}} elements within the `<video>` element, one for each version of the video you offer.
This can be used to offer various versions of a video that can be selected depending on bandwidth availability, but in our case, we'll use it to offer format options.

In the example shown here, a video is offered to the browser in two formats: WebM and MP4.

{{InteractiveExample("HTML Demo: &lt;source&gt;", "tabbed-standard")}}

```html interactive-example
<video controls width="250" height="200" muted>
  <source src="/shared-assets/videos/flower.webm" type="video/webm" />
  <source src="/shared-assets/videos/flower.mp4" type="video/mp4" />
  Download the
  <a href="/shared-assets/videos/flower.webm">WEBM</a>
  or
  <a href="/shared-assets/videos/flower.mp4">MP4</a>
  video.
</video>
```

The video is offered first in WebM format (with the [`type`](/en-US/docs/Web/HTML/Reference/Elements/source#type) attribute set to `video/webm`).
If the {{Glossary("user agent")}} can't play that, it moves on to the next option, whose `type` is specified as `video/mp4`.
If neither of those can be played, the text "This browser does not support the HTML video element." is presented.

## Specifications

| Specification                                                                                                                                                | Comment                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------- |
| [ETSI 3GPP](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=1441)                                            | Defines the 3GP container format                                                                                |
| [ISO/IEC 14496-3](https://www.iso.org/standard/53943.html) (MPEG-4 Part 3 Audio)                                                                             | Defines MP4 audio including ADTS                                                                                |
| [FLAC Format](https://xiph.org/flac/format.html)                                                                                                             | The FLAC format specification                                                                                   |
| [ISO/IEC 11172-1](https://www.iso.org/standard/19180.html) (MPEG-1 Part 1 Systems)                                                                           | Defines the MPEG-1 container format                                                                             |
| [ISO/IEC 13818-1](https://www.iso.org/standard/74427.html) (MPEG-2 Part 1 Systems)                                                                           | Defines the MPEG-2 container format                                                                             |
| [ISO/IEC 14496-14](https://www.iso.org/standard/75929.html) (MPEG-4 Part 14: MP4 file format)                                                                | Defines the MPEG-4 (MP4) version 2 container format                                                             |
| [ISO/IEC 14496-1](https://www.iso.org/standard/55688.html) (MPEG-4 Part 1 Systems)                                                                           | Defines the original MPEG-4 (MP4) container format                                                              |
| {{RFC(3533)}}                                                                                                                                                | Defines the Ogg container format                                                                                |
| {{RFC(5334)}}                                                                                                                                                | Defines the Ogg media types and file extensions                                                                 |
| [QuickTime File Format Specification](https://developer.apple.com/documentation/quicktime-file-format)                                                       | Defines the QuickTime movie (MOV) format                                                                        |
| [Multimedia Programming Interface and Data Specifications 1.0](https://web.archive.org/web/20090417165828/http://www.kk.iij4u.or.jp/~kondo/wave/mpidata.txt) | The closest thing to an official WAVE specification                                                             |
| [Resource Interchange File Format](https://learn.microsoft.com/en-us/windows/win32/xaudio2/resource-interchange-file-format--riff-) (used by WAV)            | Defines the RIFF format; WAVE files are a form of RIFF                                                          |
| [WebM Container Guidelines](https://www.webmproject.org/docs/container/)                                                                                     | Guide for adapting Matroska for WebM                                                                            |
| [Matroska Specifications](https://www.matroska.org/index.html)                                                                                               | The specification for the Matroska container format upon which WebM is based                                    |
| [WebM Byte Stream Format](https://w3c.github.io/media-source/webm-byte-stream-format.html)                                                                   | WebM byte stream format for use with [Media Source Extensions](/en-US/docs/Web/API/Media_Source_Extensions_API) |

## Browser compatibility

<table class="standard-table">
  <thead>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: bottom">
        Container format name
      </th>
      <th
        colspan="3"
        scope="col"
        style="text-align: center; border-right: 2px solid #d4dde4"
      >
        Audio
      </th>
      <th colspan="3" scope="col" style="text-align: center">Video</th>
    </tr>
    <tr>
      <th scope="col" style="vertical-align: bottom">MIME type</th>
      <th scope="col" style="vertical-align: bottom">Extension(s)</th>
      <th
        scope="col"
        style="vertical-align: bottom; border-right: 2px solid #d4dde4"
      >
        Browser support
      </th>
      <th scope="col" style="vertical-align: bottom">MIME type</th>
      <th scope="col" style="vertical-align: bottom">Extension(s)</th>
      <th
        scope="col"
        style="vertical-align: bottom; border-right: 2px solid #d4dde4"
      >
        Browser support
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row" style="vertical-align: bottom">3GP</th>
      <td style="vertical-align: top"><code>audio/3gpp</code></td>
      <td style="vertical-align: top"><code>.3gp</code></td>
      <td style="vertical-align: top; border-right: 2px solid #d4dde4">
        Firefox
      </td>
      <td style="vertical-align: top"><code>video/3gpp</code></td>
      <td style="vertical-align: top"><code>.3gp</code></td>
      <td style="vertical-align: top">Firefox</td>
    </tr>
    <tr>
      <th scope="row" style="vertical-align: top">
        ADTS (Audio Data Transport Stream)
      </th>
      <td style="vertical-align: top"><code>audio/aac</code></td>
      <td style="vertical-align: top"><code>.aac</code></td>
      <td style="vertical-align: top; border-right: 2px solid #d4dde4">
        Firefox
      </td>
      <td style="vertical-align: top">—</td>
      <td style="vertical-align: top">—</td>
      <td style="vertical-align: top">—</td>
    </tr>
    <tr>
      <th scope="row" style="vertical-align: top">FLAC</th>
      <td style="vertical-align: top"><code>audio/flac</code></td>
      <td style="vertical-align: top"><code>.flac</code></td>
      <td style="vertical-align: top; border-right: 2px solid #d4dde4">
        Firefox
      </td>
      <td style="vertical-align: top">—</td>
      <td style="vertical-align: top">—</td>
      <td style="vertical-align: top">—</td>
    </tr>
    <tr>
      <th rowspan="2" scope="row" style="vertical-align: top">
        MPEG-1 / MPEG-2 (MPG or MPEG)
      </th>
      <td style="vertical-align: top"><code>audio/mpeg</code></td>
      <td style="vertical-align: top">
        <code>.mpg</code><br /><code>.mpeg</code>
      </td>
      <td style="vertical-align: top; border-right: 2px solid #d4dde4">
        Firefox
      </td>
      <td rowspan="2" style="vertical-align: top"><code>video/mpeg</code></td>
      <td rowspan="2" style="vertical-align: top">
        <code>.mpg</code><br /><code>.mpeg</code>
      </td>
      <td rowspan="2" style="vertical-align: top">Firefox</td>
    </tr>
    <tr>
      <td style="vertical-align: top"><code>audio/mp3</code></td>
      <td style="vertical-align: top"><code>.mp3</code></td>
      <td style="vertical-align: top; border-right: 2px solid #d4dde4">
        Firefox
      </td>
    </tr>
    <tr>
      <th scope="row" style="vertical-align: top">MPEG-4 (MP4)</th>
      <td style="vertical-align: top"><code>audio/mp4</code></td>
      <td style="vertical-align: top">
        <code>.mp4</code><br /><code>.m4a</code>
      </td>
      <td style="vertical-align: top; border-right: 2px solid #d4dde4">
        Firefox
      </td>
      <td style="vertical-align: top"><code>video/mp4</code></td>
      <td style="vertical-align: top">
        <code>.mp4</code><br /><code>.m4v</code><br /><code>.m4p</code>
      </td>
      <td style="vertical-align: top">Firefox</td>
    </tr>
    <tr>
      <th scope="row" style="vertical-align: top">Ogg</th>
      <td style="vertical-align: top"><code>audio/ogg</code></td>
      <td style="vertical-align: top">
        <code>.oga</code><br /><code>.ogg</code>
      </td>
      <td style="vertical-align: top; border-right: 2px solid #d4dde4">
        Firefox, Safari
      </td>
      <td style="vertical-align: top"><code>video/ogg</code></td>
      <td style="vertical-align: top">
        <code>.ogv</code><br /><code>.ogg</code>
      </td>
      <td style="vertical-align: top">Firefox</td>
    </tr>
    <tr>
      <th scope="row" style="vertical-align: top">QuickTime Movie (MOV)</th>
      <td style="vertical-align: top">—</td>
      <td style="vertical-align: top">—</td>
      <td style="vertical-align: top; border-right: 2px solid #d4dde4">—</td>
      <td style="vertical-align: top"><code>video/quicktime</code></td>
      <td style="vertical-align: top"><code>.mov</code></td>
      <td style="vertical-align: top">Safari</td>
    </tr>
    <tr>
      <th scope="row" style="vertical-align: top">WAV (Waveform Audio File)</th>
      <td style="vertical-align: top"><code>audio/wav</code></td>
      <td style="vertical-align: top"><code>.wav</code></td>
      <td style="vertical-align: top; border-right: 2px solid #d4dde4">
        Firefox
      </td>
      <td style="vertical-align: top">—</td>
      <td style="vertical-align: top">—</td>
      <td style="vertical-align: top">—</td>
    </tr>
    <tr>
      <th scope="row" style="vertical-align: top">WebM</th>
      <td style="vertical-align: top"><code>audio/webm</code></td>
      <td style="vertical-align: top"><code>.webm</code></td>
      <td style="vertical-align: top; border-right: 2px solid #d4dde4">
        Firefox
      </td>
      <td style="vertical-align: top"><code>video/webm</code></td>
      <td style="vertical-align: top"><code>.webm</code></td>
      <td style="vertical-align: top">Firefox</td>
    </tr>
  </tbody>
</table>

## See also

- [WebRTC API](/en-US/docs/Web/API/WebRTC_API)
- [MediaStream Recording API](/en-US/docs/Web/API/MediaStream_Recording_API)
- {{HTMLElement("audio")}} and {{HTMLElement("video")}} elements
