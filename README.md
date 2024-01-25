# Codesign and Notarize

A Github Action to codesign and notarize macOS applications.

This action only runs on macOS.

## Inputs

| Name | Description | Example Value                         | Required |
| ---- | ----------- |---------------------------------------| -------- |
| certificate | The certificate for signing | `${{ secrets.CERTIFICATE }}`          | Yes |
| certificate-password | The password for the certificate | `${{ secrets.CERTIFICATE_PASSWORD }}` | Yes |
| username | The Apple ID username to use for notarization | `${{ secrets.APPLE_ID_USERNAME }}`    | Yes |
| password | The Apple ID password to use for notarization | `${{ secrets.APPLE_ID_PASSWORD }}`    | Yes |
| apple-team-id | The Apple Team ID to use for signing and notarization | `33DS2ZRDST`                          | Yes |
| app-path | The path to the application to sign and notarize | `build/my_app`                        | Yes |
| entitlements-path | The path to the entitlements file to use for signing | `src/entitlements.plist`              | No |

## Usage

```yaml
- name: Sign and notarize the release build
  uses: toitlang/action-macos-sign-notarize@v1.1.0
  with:
    certificate: ${{ secrets.CERTIFICATE }}
    certificate-password: ${{ secrets.CERTIFICATE_PASSWORD }}
    username: ${{ secrets.APPLE_ID_USERNAME }}
    password: ${{ secrets.APPLE_ID_PASSWORD }}
    apple-team-id: 33DS2ZRDST
    app-path: build/my_app
```
