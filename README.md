# OtoMAD Studio

**Create. Remix. Make It MAD.**

OtoMAD Studio is a Japanese-first, browser-based audio editor for 音MAD workflows. It is built with HTML, CSS, JavaScript, and the Web Audio API, and is hosted on GitHub Pages.

## Features

- Multi-track audio import, waveform display, mix preview, positioning, trimming, pitch, volume, pan, mute/solo, fades, and track effects.
- Audio extraction from video files supported by the browser's media decoder.
- Timeline editing, beat-grid snapping, transient-based alignment, BPM estimation, and timing nudges.
- In-browser speech transcription using selectable Whisper models, language options, timestamped segments, and sequential processing of long tracks. Model download progress is shown.
- Local audio metrics, quiet-region/transient candidates, and rule-based editing suggestions.
- Image assets can be imported and used as backgrounds in the video composition tool.
- Basic video composition: use an optional video or image background, choose crop-to-fill or contain-with-letterboxing, set the video source range, and overlay timed text.
- Caption queue: add, edit, and delete up to 20 captions with individual start/end times. Up to three active captions are drawn at once.
- WebM video export combining the current audio mix with the selected background and text. The video background loops over its selected range when needed.
- Project JSON save/load for track settings, video composition settings, caption timings, and imported image assets.
- Stereo 16-bit PCM WAV export at 44.1 kHz or 48 kHz, plus optional compressed audio export using a browser-supported MediaRecorder codec.
- Optional peak reduction to -1 dBFS, chunked WAV processing with progress feedback, undo/redo for supported operations, responsive Japanese UI, and keyboard shortcuts.

## Important limitations

- This is a browser-based editor; media decoding, codecs, memory use, and export support depend on the browser and device.
- Video composition is a basic export utility, not a full non-linear video editor. There is no multi-clip video timeline, transitions, multiple image layers, or advanced text animation.
- Video export uses MediaRecorder and runs in real time. Keep the tab in the foreground while exporting. WebM export is available only in browsers that support the required APIs and codecs.
- The current audio renderer is limited to five minutes.
- Project JSON embeds imported image files and can become large. It saves video composition settings and caption timings, but does not embed source audio or video files. Re-import those media files separately before restoring track settings or exporting.
- Speech transcription uses a speech-recognition model. Other audio analysis and editing suggestions are based on local signal measurements and rules, not generative-AI understanding of the audio.
- MP3 export is not currently available.

## Getting started

1. Open OtoMAD Studio in a supported desktop browser.
2. Import audio, or import a supported video file to extract its audio.
3. Arrange and edit tracks, then preview the mix.
4. Optionally set a video or image background and configure timed captions.
5. Export the completed mix as WAV, or export audio and visuals together as WebM if supported.
6. Save project settings as JSON when needed; keep the original audio and video files separately.

## Technology

- HTML, CSS, JavaScript
- Web Audio API and OfflineAudioContext
- MediaRecorder and Canvas API
- GitHub Pages

The project aims to keep development costs low and avoid paid processing APIs where possible.

## Copyright and responsible use

You are responsible for confirming that you have the rights or permission to use any audio, video, image, or other source material you import, publish, or distribute. Follow applicable copyright rules and the terms of the services where you share your work.

---

## 日本語

OtoMAD Studioは、音MAD制作を支援するブラウザ型の音声編集ツールです。複数トラックの編集、タイムライン操作、BPM推定、拍合わせ、素材の簡易解析、WAV書き出しなどに対応しています。

### 映像プレビュー・動画書き出し

- 動画または画像を背景に設定し、音声ミックスと合成したWebM動画を書き出せます。
- 背景動画は開始・終了位置を秒単位で指定できます。指定範囲が音声より短い場合は、範囲内を繰り返します。
- テロップは複数登録でき、各テロップの表示開始・終了時刻を指定できます。最大20件を登録でき、同時に表示されるテロップは最大3件です。
- プロジェクトJSONには映像設定・テロップの時刻・画像素材が保存されます。音声・動画ファイル本体は保存されないため、再読み込み時には元ファイルも必要です。
- 動画書き出しはリアルタイム処理で、対応ブラウザが必要です。フル機能の映像タイムライン、複数映像クリップの編集、トランジション、複数画像レイヤー、複雑な文字アニメーションには未対応です。

### 注意点

- AI文字起こしはWhisper系モデルを利用します。その他の素材解析や編集案は、音量などの信号情報に基づくルールベースの機能です。
- WAVと対応ブラウザでの圧縮音声・WebM書き出しに対応しています。MP3書き出しは未対応です。
- 現行のミックス処理は5分以内に制限されています。長いプロジェクトではメモリを多く使用する可能性があります。
- 画像素材を多く保存すると、プロジェクトJSONのサイズが大きくなります。

無料の開発環境と標準的なWeb技術を優先し、段階的に機能を拡張しています。
