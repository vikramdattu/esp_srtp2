# esp_srtp2

[libsrtp2](https://github.com/cisco/libsrtp) (Cisco) port for ESP-IDF using the mbedtls crypto backend with AES-GCM.

Used for SRTP/SRTCP packet protection in WebRTC and other RTP-based protocols on ESP32-series chips.

## Features

- libsrtp 2.6.x (pinned at commit `9fd71ba`)
- mbedtls crypto backend (AES-CM, AES-GCM, HMAC-SHA1) — leverages on-chip crypto where available
- AEAD profiles: `AEAD_AES_128_GCM`, `AEAD_AES_256_GCM`
- SRTP profiles: `AES_CM_128_HMAC_SHA1_80`, `AES_CM_128_HMAC_SHA1_32`

## Add to a project

```bash
idf.py add-dependency "vikramdattu/esp_srtp2^1.0.0"
```

Or in your project's `main/idf_component.yml`:

```yaml
dependencies:
  vikramdattu/esp_srtp2: "^1.0.0"
```

## Supported targets

esp32, esp32s2, esp32s3, esp32c3, esp32c5, esp32c6, esp32p4. Requires ESP-IDF >= 5.4.

## Source

This wrapper bundles [cisco/libsrtp](https://github.com/cisco/libsrtp) as a submodule. All SRTP cryptographic implementation is upstream; this repo adds only the ESP-IDF build glue (`CMakeLists.txt`, `port/config.h`) and a small build-time patch (`patches/srtp.patch`).

## License

BSD-3-Clause (see `LICENSE`), matching upstream libsrtp.
