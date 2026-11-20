# Aeri updates

Signed system images for the Aeri ARM64 QEMU desktop are published here. Open **System Settings → Software Update** in Aeri, choose **Check for updates**, then **Download**. You choose when to restart.

- [Latest signed manifest](https://github.com/FBukovina/aeri-updates/releases/latest/download/release.json)
- [Release history and boot images](https://github.com/FBukovina/aeri-updates/releases)
- [Aeri publisher public key](aeri-ota-public.pem)

Aeri checks the manifest signature against the publisher key bundled with its launcher. The SHA-256 fingerprint of the DER-encoded P-256 public key is `7749d78ba430243df41070bfc369fba15d84ac89e35efa69ecf328e6c2d10ae8`. You can compare your trusted copy with the following command.

```sh
openssl pkey -pubin -in aeri-ota-public.pem -outform DER | openssl dgst -sha256
```

Each release contains a signed `release.json` and its full 128 MiB boot image. The launcher verifies the image digest before installation. Your profile and notes live on separate disks and persist across updates.
