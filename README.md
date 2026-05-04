# Test Automation UI

This repository contains a Playwright-based functional and usability test project for Pixels Suite. It includes one automated PNG preview scenario with recorded CSV output, a second automated run using an alternate PNG file, and a completed workbook of 36 manual test cases covering the required website features.

This workspace contains Playwright-based automated checks for Pixels Suite and a completed set of manual test scenarios for the website functional/usability assessment.

## Files

- `image_preview_test.py` - automated Playwright script for PNG preview verification
- `sample.png` - default PNG input used by the first automated run
- `sample_alt.png` - alternate PNG input used by the second automated run
- `execution_results.csv` - recorded output from the automated runs
- `results/preview_pass.png` - screenshot captured by the first successful run
- `results/alt/preview_pass.png` - screenshot captured by the alternate successful run
- `Manual Test Cases for Option 2.xlsx` - 36 manual scenarios covering the required 10 features

## Prerequisites

- Python 3.14
- Playwright installed in the active Python environment
- Chromium browser binaries installed for Playwright

## Setup

Install the browser binaries if needed:

```powershell
python -m playwright install chromium
```

## Run the automated scenario

```powershell
python image_preview_test.py --url "https://www.pixelssuite.com/convert-to-png" --slow-mo-ms 2000
```

The script uploads a PNG file, checks whether the preview appears, saves a screenshot in `results/`, and appends the outcome to `execution_results.csv`. It supports a custom `--png` path, so you can repeat the same automated preview scenario with a different PNG file when needed.

## Notes

- The automation currently validates PNG preview behavior on the Pixels Suite conversion page.
- Two automated runs are recorded in `execution_results.csv`: one using `sample.png` and another using `sample_alt.png`.
- The workbook covers the 10 required features with at least 3 scenarios each: 1 positive and 2 negative scenarios per feature.
