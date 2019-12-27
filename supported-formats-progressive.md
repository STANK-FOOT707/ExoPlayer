Streams in the following container formats can be played directly by ExoPlayer.
The contained audio and video sample formats must also be supported (see the
[sample formats](supported-formats.html#sample-formats) section for details).

| Container format | Supported    | Comment              |
|------------------|:------------:|:---------------------|
| MP4 | YES ||
| M4A | YES ||
| FMP4 | YES ||
| WebM| YES ||
| Matroska| YES ||
| MP3 | YES | Some streams only seekable using constant bitrate seeking** |
| Ogg | YES | Containing Vorbis, Opus and Flac |
| WAV | YES ||
| MPEG-TS | YES ||
| MPEG-PS | YES ||
| FLV | YES | Not seekable* |
| ADTS (AAC) | YES | Only seekable using constant bitrate seeking** |
| Flac | YES | Using the [Flac extension][] only |
| AMR | YES | Only seekable using constant bitrate seeking** |

\* Seeking is unsupported because the container does not provide metadata (e.g.,
a sample index) to allow a media player to perform a seek in an efficient way.
If seeking is required, we suggest using a more appropriate container format.

\*\* These extractors have `FLAG_ENABLE_CONSTANT_BITRATE_SEEKING` flags for
enabling approximate seeking using a constant bitrate assumption. This
functionality is not enabled by default. The simplest way to enable this
functionality for all extractors that support it is to use
`DefaultExtractorsFactory.setConstantBitrateSeekingEnabled`, as described
[here](progressive.html#enabling-constant-bitrate-seeking).

[Flac extension]: {{ site.release_v2 }}/extensions/flac