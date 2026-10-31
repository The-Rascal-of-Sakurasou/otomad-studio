# OtoMAD Studio

**Create. Remix. Make It MAD.**

OtoMAD Studio is a Japanese-first, browser-based editor for 音MAD workflows. It is built with HTML, CSS, JavaScript, and the Web Audio API, and is hosted with GitHub Pages.

## Current features

- Multi-track audio import and mix preview.
- Audio extraction from supported video files where the browser can decode the file.
- Waveform display, track positioning, trimming, pitch, volume, pan, mute/solo, fades, and track effects.
- Timeline editing, beat-grid snapping, transient-based alignment, BPM estimation, and timing nudges.
- AI speech transcription with selectable Whisper models, language options, timestamped segments, and sequential processing of tracks longer than three minutes. Model download progress is shown; model files are fetched from a CDN and inference runs in the browser.
- Local audio metrics, quiet-region/transient candidates, and rule-based editing suggestions.
- Image assets can be imported as visual reference material. They are not yet composited into a video export.
- Save and reload project settings as JSON. Imported image assets are embedded in the JSON; source audio and video files are not embedded and must be re-imported separately.
- Export the mix as stereo 16-bit PCM WAV at 44.1 kHz or 48 kHz.
- Optional compressed audio export using a browser-supported MediaRecorder codec (typically WebM/Opus; other supported containers may be selected by the browser). This records in real time and can take about as long as the mix duration.
- Optional peak reduction to -1 dBFS during export.
- Chunked WAV encoding and peak processing with progress feedback to help keep the interface responsive.
- Undo/redo for supported editing operations.
- Japanese-first responsive interface, keyboard shortcuts, and status messages.

## Important limitations

- AI speech transcription uses a speech-recognition model; other analysis and editing suggestions are based on local signal measurements and rules, not generative-AI understanding of the audio.
- Image assets are reference-only; full video timeline compositing and video export are not implemented yet.
- Video import depends on the browser's media decoder and currently supports audio extraction for the audio workflow.
- Project JSON can embed imported image assets, which can increase its file size. It does not include source audio or video files; re-import those files separately before restoring track settings.
- WAV is the lossless-oriented export option. Compressed audio export depends on browser MediaRecorder codec support and runs in real time; MP3 and video export are not currently available.
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
- AI文字起こしはWhisper系モデルを利用し、タイムスタンプ付きのセリフ候補を抽出します。その他の素材解析と編集案は、音量などの信号情報に基づくルールベースの機能です。
- 画像は参照素材として読み込めますが、動画への合成や動画ファイルの書き出しには未対応です。
- WAV書き出しに加え、対応ブラウザではWebM/Opusなどの圧縮音声書き出しも利用できます。圧縮音声はリアルタイム録音方式のため、ミックスの再生時間と同程度の時間がかかる場合があります。MP3と動画の書き出しは未対応です。
- プロジェクト設定JSONには読み込んだ画像素材が埋め込まれます。ただし、音声・動画の本体は含まれないため、再読み込み時には元の音声・動画ファイルも必要です。画像が多い場合、JSONファイルのサイズが大きくなります。
- 長いプロジェクトはメモリを多く使用する可能性があります。現行のミックス処理は5分以内に制限されています。

無料の開発環境と標準的なWeb技術を優先し、段階的に機能を拡張します。
