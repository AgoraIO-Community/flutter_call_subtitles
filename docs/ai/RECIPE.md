# Flutter Call Subtitles

## Overview

Add live subtitles to a Flutter RTC call by pairing Agora audio with a caption display workflow.

Repository: [AgoraIO-Community/flutter_call_subtitles](https://github.com/AgoraIO-Community/flutter_call_subtitles)

## Prerequisites and Setup

1. Read `docs/SUBTITLES.md` and use Flutter with a Dart SDK compatible with `pubspec.yaml` (Dart >=3.4.0 <4.0.0).
2. Configure a compatible transcription backend; the tutorial links an example server. It must use the same Agora App ID and implement the start/stop routes called by `lib/call.dart`.
3. The completed `lib/call.dart` imports `lib/consts.dart`, which is absent from this checkout. Create that local configuration with the `appId` and `serverUrl` constants used by the source, using `starter-app/lib/consts.dart` as a naming reference.
4. Platform runner directories are also absent. Integrate the sample into a Flutter Android/iOS app, supply the required platform permissions, and then run `flutter pub get` and `flutter run`. The landing screen joins channel `test`.

## What To Check

- Verify two clients join `test` and the backend starts one transcription task per channel.
- Check decoded stream messages produce subtitles and the transcription bot is excluded from the displayed user list.
- End the call and confirm the backend task stops and RTC resources release.

## Integration Notes

This repository is tutorial source, not a complete runnable Flutter project. Its RTC join uses an empty token, and the backend routing/authorization must match the actual source. Add an authenticated token flow and coordinate transcription task ownership for production.

Keep App Certificates, customer secrets and privileged token generation on a trusted backend for production. Use only your own test credentials while configuring historical demos; do not commit them. Preserve the sample's existing dependency versions and lifecycle until a separate migration is tested.

## Source References

- [docs/SUBTITLES.md](../../docs/SUBTITLES.md)
- [lib/call.dart](../../lib/call.dart)
- [lib/main.dart](../../lib/main.dart)
- [pubspec.yaml](../../pubspec.yaml)
- [starter-app/lib/consts.dart](../../starter-app/lib/consts.dart)

## Validation Status

This recipe was checked against the repository's source and setup documents. The platform build and live service/device flow have not been run as part of this documentation change. Complete the checks above in an environment with the required SDKs, hardware and service access before treating it as a validated deployment.

## Implementation Prompt

```text
You are working in AgoraIO-Community/flutter_call_subtitles. Use docs/ai/RECIPE.md and its linked source files to adapt the Flutter Call Subtitles reference to this project.

Start by inspecting the actual sample directory and configuration described above. Resolve its listed missing prerequisites before claiming it is runnable. Preserve the existing architecture and compatible dependency versions. Implement the recipe's feature-specific flow, permissions and resource cleanup. Use a trusted backend for privileged credentials and tokens in production.

Run the repository-specific build or launch flow, then perform each What To Check item. Report the commands run, the observed results and anything blocked by service access, hardware or incomplete sample code. Do not claim live validation from a documentation or catalog build alone.
```
