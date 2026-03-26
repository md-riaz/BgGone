# BgGone

Fully offline browser-based photo background remover using U²-Net deep learning model.

## Features

- **High Accuracy**: Uses U²-Net ONNX model for superior background removal accuracy
- **Privacy First**: 100% client-side processing - your images never leave your device
- **WASM Powered**: Runs via ONNX Runtime Web with WebAssembly for fast inference
- **Universal Support**: Works with various subjects, not just portraits
- **Adjustable Settings**: Fine-tune mask threshold and edge smoothing
- **Multiple Export Options**: Download with transparent, colored, or blurred backgrounds

## Technology

- **Model**: U²-Net (U-Square Network) for salient object detection
- **Runtime**: ONNX Runtime Web with WASM backend
- **Architecture**: Single-file web application (no build tools required)
- **Styling**: Tailwind CSS

## Usage

Simply open `index.html` in a modern web browser.

By default, BgGone now tries to load model files from the repository first (in this order):

- `./models/isnet-general-use.onnx` (dynamic input supported; preferred for input sizes larger than 320x320)
- `./models/u2net.onnx` (fixed 320x320 input fallback)

If local files are not present, it falls back to remote HuggingFace URLs.

1. Upload an image (JPG, PNG, or WebP)
2. Click "Remove Background"
3. Adjust settings as needed
4. Download the result

## Quality Modes

- **Fast**: 512px processing resolution
- **Balanced**: 1024px processing resolution (default)
- **Best**: 2048px processing resolution

Higher quality modes provide better accuracy but take longer to process.

- For **fixed-input models** (for example classic U²-Net), the app uses the model's required input size.
- For **dynamic-input models**, quality presets directly control the model input size (Fast/Balanced/Best), so inputs can be larger than fixed 320.
