# PORTED import, step 2: TOTP and recovery codes

Released by the specification team (owner side), 2026-11-04. This folder is an **input** for the implementation team. Integrate it, then delete the folder in the same PR.

## What is here

| File (`.go.txt` = Go source) | sha256 | Origin (owner's AGPL fork, commit `f4455a0`) |
|---|---|---|
| `totp.go.txt` | `3a5ebd09a3d807a7ee8848e19cc85db832ee363e3096bbb2a1649f562a8d5efd` | `Hub/internal/services/auth/totp.go`, whole file |
| `totp_test.go.txt` | `085c1002daf9a4c90b09fb392140e4ac10d6014a83098ff6a405c6ea1eb7f4ac` | `Hub/internal/services/auth/totp_test.go`, whole file |
| `recovery_excerpt.go.txt` | `9a3766e856f0fec40c18999d1f3ed908af7adc1fd73a8e0ab5929dbe0e118c30` | `Hub/internal/services/auth/mfa.go`, verbatim excerpt of the recovery-code helpers only |

Only the cryptographic core is released. The old project's enrolment, lockout and session flows are not: this repository already has its own (§6.3, Q15–Q20).

## Provenance and rights

The files were written after the fork, are the owner's own work, and are licensed by the owner to this repository under its proprietary licence. Use this repository's header.

§14.14 check against HoneyWire v2.1.0 and HEAD:

| File | line% | fp% | fpN% | Shared literals |
|---|---|---|---|---|
| `totp.go` | 4.9 | 0.0 | 3.2 | none |
| `totp_test.go` | 0.0 | 0.0 | 0.5 | none |
| `recovery_excerpt.go` | 8.6 | 0.0 | 0.7 | none |

All are at the noise floor. Standard library only; no new dependency.

## Integration notes (against `ported.TOTP`)

1. **`GenerateSecret(accountName, issuer)`.** Combine `newTOTPSecret()` (160-bit random, base32 without padding) and `totpURI(secret, issuer, account)`.
2. **`Verify(secret, code, lastStep, now)`.**
   - Use `verifyTOTP(secret, code, now, lastStep)`: note the argument order.
   - It checks all three windows (±1 step) without returning early and accepts only a step greater than `lastStep`.
   - Keep the Hub's own compare-and-swap on the step (Q20 notes); the two are complementary.
3. **`GenerateRecoveryCodes(n)`.**
   - Use the generation loop from `newRecoveryCodes`: 10 base32 characters (50 bits) shown as `xxxxx-xxxxx`, stored as `hashRecovery(code)`.
   - Return `plain` and `hashed` instead of writing to a store.
   - The hash domain prefix in `hashRecovery` reads `truesignal-recovery:`. Keep it stable once codes are issued.
4. **`ConsumeRecoveryCode(hashed, code)`.**
   - Use the matching part of `consumeRecoveryLocked`: `normalizeCode`, the length-10 check, and a constant-time comparison against each hash. Return the remaining slice.
   - Drop the `s.store`, `s.recoveryHashes()` and `log` lines; they are the old project's storage glue.
   - Persisting the remaining hashes and auditing a recovery-code use is the Hub's job.
5. **Acceptance.**
   - Re-run §14 #2 and #3 with the real module in place of the stub.
   - Keep the RFC 6238 test vectors in `totp_test.go`.
   - `TS_REQUIRE_MFA=true` must now start.
   - Add a `PROVENANCE.md` entry naming this folder.
6. **Delete `ported-inbox/step-2/`** in the integration PR.
