# OtoMAD Studio

**Create. Remix. Make It MAD.**

OtoMAD Studio is a Japanese-first, browser-based editor for 音MAD workflows. It is built with HTML, CSS, JavaScript, and the Web Audio API, and is hosted with GitHub Pages.

## Current features

- Multi-track audio import and mix preview.
- Audio extraction from supported video files where the browser can decode the file.
- Waveform display, track positioning, trimming, pitch, volume, pan, mute/solo, fades, and track effects.
- Timeline editing, beat-grid snapping, transient-based alignment, BPM estimation, and timing nudges.
- Local audio metrics, quiet-region/transient candidates, and rule-based editing suggestions.
- Image assets can be imported as visual reference material. They are not yet composited into a video export.
- Save and reload project settings as JSON. The JSON stores editing settings, not the source media.
- Export the mix as stereo 16-bit PCM WAV at 44.1 kHz or 48 kHz.
- Optional peak reduction to -1 dBFS during export.
- Chunked WAV encoding and peak processing with progress feedback to help keep the interface responsive.
- Undo/redo for supported editing operations.
- Japanese-first responsive interface, keyboard shortcuts, and status messages.

## Important limitations

- The current analysis and editing suggestions are based on local signal measurements and rules. They should not be described as generative-AI understanding of the audio.
- Image assets are reference-only; full video timeline compositing and video export are not implemented yet.
- Video import depends on the browser's media decoder and currently supports audio extraction for the audio workflow.
- Project JSON does not include audio or video files. Reload the source media separately before restoring project settings.
- Export is WAV-only. MP3 and video export are not currently available.
- Processing runs in the browser; long or complex projects can still require substantial memory. The current renderer limits the mix to five minutes.

## Getting started

1. Open the hosted OtoMAD Studio page in a supported desktop browser.
2. Import audio or a supported video file.
3. Arrange and edit tracks, then preview the mix.
4. Use the analysis panel as a guide, and verify edits by listening.
5. Export the completed mix as WAV.
6. Optionally save project settings as JSON; keep the original media files separately.

## Technology

- HTML, CSS, JavaScript
- Web Audio API and OfflineAudioContext
- GitHub Pages

The project aims to keep development costs low and avoid paid processing APIs where possible.

## Copyright and responsible use

You are responsible for confirming that you have the rights or permission to use any audio, video, image, or other source material you import, publish, or distribute. Follow applicable copyright rules and the terms of the services where you share your work.

---

## 日本語

OtoMAD Studioは、音MAD制作を支援するブラウザ型の音声編集ツールです。複数トラックの編集、タイムライン操作、BPM推定、拍合わせ、素材の簡易解析、WAV書き出しなどを備えています。

**現在の注意点**
- 素材解析と編集案は、音量などの信号情報に基づくルールベースの機能です。音声の意味を理解する生成AI機能とは異なります。
- 画像は参照素材として読み込めますが、動画への合成や動画ファイルの書き出しには未対応です。
- 書き出し形式はWAVのみです。
- プロジェクト設定JSONには素材本体が含まれないため、再読み込み時には元の素材ファイルも必要です。
- 長いプロジェクトはメモリを多く使用する可能性があります。現行のミックス処理は5分以内に制限されています。

無料の開発環境と標準的なWeb技術を優先し、段階的に機能を拡張します。
