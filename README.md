# Expo Camera Barcode Scanning Issue

This repository demonstrates a bug in Expo's Camera API where barcode scanning intermittently stops working after multiple scans. The `onBarCodeScanned` callback function ceases to be called, despite the camera preview remaining active.

## Bug Description

The barcode scanner functions correctly for a few scans. However, after a variable number of scans, it stops detecting barcodes.  The callback provided to `onBarCodeScanned` is no longer invoked, even though the camera feed continues to show the preview.

## Reproduction Steps

1. Clone this repository.
2. Run `npm install`.
3. Run `expo start`.
4. Scan multiple barcodes.  Observe that the scanning eventually stops working.

## Solution

A solution is provided in `bugSolution.js`.  The issue is resolved by ensuring that the camera is properly restarted after a set amount of scans (preventing memory leaks/exhaustion).