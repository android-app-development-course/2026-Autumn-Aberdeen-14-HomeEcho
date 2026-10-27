# HomeEcho

**Make invisible household work easier to describe—and easier to discuss.**

HomeEcho is a native Android prototype that helps turn everyday accounts of household work into specific, editable tasks. It explores a simple conversation flow: write down what happened, choose what to share, leave room for different perspectives, and agree on what to try next.

Built with **Kotlin, Jetpack Compose, and Room**, HomeEcho is a runnable application developed locally—not a slide deck, web wrapper, or collection of mockups.

> **Repository status:** this is the initial, README-only publication. The **business plan** and **Android project source code** will be uploaded separately. Screenshots, build instructions, and supporting documents will be linked when their files are available. There is currently no APK download or buildable Android project in this repository.
>
> **Prototype scope:** a single-device, two-role demonstration using fictional examples. There are **no real accounts, cross-device synchronization, or live AI requests**. Switching roles is not authentication or a security boundary. Please do not enter sensitive personal or household information.
>
> **App language:** the current interface is Simplified Chinese. This README is in English; an English app localization is not implemented.

## Project information

| Item | Details |
| --- | --- |
| Project | HomeEcho |
| Repository | `2026-Autumn-Aberdeen-14-HomeEcho` |
| Platform | Native Android |
| Current product stage | Locally implemented demonstration prototype |
| Publication stage | Project overview first; business plan and source code to follow |

## Why HomeEcho?

“Making dinner” can involve more than cooking: checking ingredients, choosing a menu, asking about preferences, shopping, and remembering what still needs to happen. Some of that work is easy to overlook or difficult to explain.

HomeEcho is designed around voluntary communication between two consenting adult partners. Rather than asking who has done more, it helps make a specific piece of household work easier to describe and discuss.

It is **not** a relationship judge, a measure of who works harder, or a substitute for professional support. This prototype does not claim to reduce conflict or improve relationships.

## The core experience

```text
Write an account
      ↓
Review and edit specific tasks
      ↓
Save a private record
      ↓
Preview and voluntarily share a snapshot
      ↓
Review from the other demonstration role
      ↓
Draft and confirm a next-step agreement
```

A disagreement does not invalidate the original record or prevent the two roles from discussing what to do next.

## Implemented in the local prototype

The following describes the application already implemented locally. Its source code is not included in this initial repository publication.

- **Write first, organize optionally.** Save the original text on its own, or add, edit, and remove tasks. Category labels are optional.
- **Editable preset suggestions.** The bundled dinner example provides four clearly labeled, predefined suggestions. Other input can be organized manually or saved as plain text.
- **Private by default within the demo.** A record is not shared automatically. Preview its contents before explicitly creating a shared snapshot.
- **Optional personal effort.** Duration, frequency, and subjective mental effort can all be skipped. Missing values are not treated as zero, and effort is excluded from sharing by default.
- **Voluntary review.** The other demonstration role can acknowledge a description, suggest a change, retain a disagreement, defer a response, or simply not respond. Notes are optional.
- **Version-aware sharing.** Editing a private entry does not silently update its shared snapshot. Sharing again creates a new revision and clears the previous review state.
- **Agreements without forced consensus.** Both roles must confirm the same agreement version; editing its content resets both confirmations. Agreement drafting does not require resolving a disagreement about an earlier record.
- **Local persistence and data controls.** Records survive app restarts. The demo supports revoking sharing, deleting one's own records, leaving the shared space, and explicitly resetting fictional examples.

The five product labels are **execution, planning, preparation, coordination, and wrap-up**. They are interaction aids, not a standardized scientific taxonomy. There are no weighted totals, leaderboards, or rankings of either person.

## An example—not live AI

The bundled Chinese sentence describes checking the fridge, planning the menu, asking what everyone wants to eat, and buying groceries. Its preset maps to:

| Stated action | Suggested label |
| --- | --- |
| Check the fridge | Preparation |
| Plan the menu | Planning |
| Ask about food preferences | Coordination |
| Buy groceries | Execution |

There is no wrap-up task because the sentence does not mention one. The preset matches a specific Chinese example; it is not a general-purpose text parser or an English-language AI feature. The app does not infer missing facts, motives, duration, or mental effort.

## Technical overview

| Component | Technology |
| --- | --- |
| Language | Kotlin 2.1.20 |
| Interface | Jetpack Compose and Material 3 |
| UI state | ViewModel and StateFlow |
| Local persistence | Room 2.7.1 |
| Business rules | Pure Kotlin state transitions and version checks |
| Build tools | Gradle 8.11.1 and Android Gradle Plugin 8.9.2 |
| Development JDK | 17 |
| Compile / target Android API | 35 |
| Declared minimum Android version | Android 8.0 / API 26 |

Private records, optional effort, shared snapshots, review responses, and agreements are modeled separately. Changes are applied through local database transactions. This small offline prototype is not a production architecture for multiple synchronized clients or large datasets.

**Build and installation instructions will accompany the source-code upload.** No commands are provided here that depend on files not yet published.

## Local validation to date

| Check | Recorded result |
| --- | --- |
| JVM domain tests | 58 passed; no failures, errors, or skipped tests |
| Android instrumented tests | 14 passed: 13 Room/SQLite tests and 1 end-to-end Compose journey |
| Android Lint | 0 errors; 13 dependency-update warnings |
| Runtime platform | Android 15 / API 35 / x86_64 emulator |
| Debug APK signature verification | Passed |
| Force-stop and cold-start persistence check | Passed |

These are **recorded local validation results**, not a GitHub Actions status or a claim that the published repository can already reproduce them. Test sources and supporting documentation will accompany the project upload. Physical phones, API 26 devices, and a full accessibility/device matrix have not been verified.

## Privacy and participation

- **Local demonstration, not secure multi-user access.** Anyone with access to the device can switch between roles. “Private” describes the demo's visibility flow, not protection from the device holder.
- **No online processing.** The current application makes no live model requests and has no account service or collaboration backend. It does not request network access.
- **No approval of personal feelings.** A review does not determine whether someone's effort was real or whether their subjective experience is valid.
- **Revocation has limits.** Revoking a snapshot removes its in-app demo access, not screenshots or copies obtained elsewhere.
- **Deletion and reset are distinct.** Removing one role's data does not delete the other role's private entries. Shared agreement text is retained while the departing or deleting role's confirmation is withdrawn.
- **Participation is voluntary.** Leaving pauses collaboration for both roles while keeping private recording available. Rejoining does not automatically restore withdrawn shares or confirmations.

## Publication roadmap

- [x] Publish the English project README.
- [ ] Upload the business plan.
- [ ] Upload the Android project, tests, and build instructions.
- [ ] Add demonstration screenshots and supporting documentation.
- [ ] Publish an installable demonstration APK, if appropriate.

Real AI, account authentication, cross-device synchronization, voice input, and weekly dashboards are **not implemented**. Any future online version would require explicit data-processing disclosures, access controls, conflict handling, deletion policies, and cost limits before real household use.

## License

No open-source license has been selected for this project. Do not assume an MIT or Apache-2.0 license. Third-party dependencies remain subject to their respective licenses.
