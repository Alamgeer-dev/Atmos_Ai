# ATMOS AI — Color & Weather Intelligence

Browser-based multi-output image analysis using TensorFlow.js and a MobileNetV2-based model.

## Contents
- `index.html` — responsive front-end with photo upload and live camera controls.
- `tfjs_model/model.json` — TensorFlow.js LayersModel configuration.
- `tfjs_model/group1-shard1of3.bin` through `group1-shard3of3.bin` — model weights.
- `tfjs_model/classes.json` — output label metadata.
- `assets/ATMOS_AI_Project_Report.pdf` and `.docx` — project report.
- `assets/ATMOS_AI_Presentation.pptx` — presentation.
- `assets/ATMOS_AI_Voiceover_Script.txt` — narration script.

## Model details verified from the supplied model files
- Input: `[batch, 224, 224, 3]`
- Backbone: MobileNetV2 feature extractor
- Shared dense representation: 256 units, ReLU
- Output heads: `color_pct` (11), `brightness` (3), `temperature` (3), `weather` (6)
- Inference: client-side TensorFlow.js

## Important documentation gaps
The provided files do not establish the exact dataset URL/license, image counts, training/validation/test split, or measured held-out evaluation metrics. Add these from the original training source before submission. Do not report unverified accuracy.

## Local test
Serve this folder using a local HTTP server (do not open `index.html` directly as a `file://` URL because browser model fetches may be blocked):
```bash
python -m http.server 8000
```
Then open `http://localhost:8000`.

## Deploy to Vercel (static site)
1. Push the contents of this folder to the root of a public GitHub repository.
2. In Vercel, import that repository.
3. Choose Framework Preset: **Other**.
4. For a plain static site, leave Build Command empty and set Output Directory to `.` if prompted.
5. Deploy and verify that the homepage, `tfjs_model/model.json`, every shard, report, and presentation open correctly.
6. Add the real Vercel URL and dataset URL to the site/README after confirming them.

## Links to fill before final submission
- Dataset: PENDING — insert the verified URL for the exact dataset used to train this ATMOS AI model.
- GitHub: https://github.com/Alamgeer-dev/Atmos_Ai
- Vercel: PENDING — insert the deployed Vercel URL.
- YouTube: https://youtu.be/zhpYIWBYa1U — ATMOS AI promotional video on the GAG Tech channel.
- LinkedIn: PENDING — insert the LinkedIn post URL.

## Evaluation
Test the deployed model from a clean browser session. Confirm all model assets return successfully and run sample inputs. Quantitative metrics must be calculated on a held-out test set using the actual labels. The current package intentionally does not invent evaluation numbers.
