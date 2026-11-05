# PORTED import, steps 3–10 (one bundle)

Released by the specification team (owner side), 2026-11-05, on the owner's instruction to proceed with the fastest path. This folder is an **input** for the implementation team, the same way the specification is.

- Integrate one step per PR, in order: 3 → 10.
- Delete each `step-N-*` folder in its integration PR.
- The steps 1 and 2 rules apply throughout:
  - replace headers with this repository's header;
  - add a `PROVENANCE.md` entry per step naming its folder;
  - run all tests.

## Provenance and screening

- **Origin.** Every file is the owner's own post-fork work from the owner's earlier project (commit `f4455a0`), at the same relative path under each `step-N-*/` folder.
- **Screening.** Every source and Markdown file was screened against HoneyWire v2.1.0 and HEAD with the §14.14 tool.
  - Thresholds: line% ≤ 15, fp% ≤ 2, fpN% ≤ 8.
  - Files over a threshold were **not released**. The same applies by policy to every decoy `main.go` and the insights projection wiring, which are wired to the old SDK/Hub.
  - Those are specified below as functional descriptions for you to implement clean.
- **File naming.** Go/TS/Python/shell files carry a `.txt` suffix so CI skips them.

**Owner decision recorded:** these modules are relicensed by the owner, as copyright holder, under this repository's proprietary licence.

## Files

Scores are line% / fp% / fpN% against HoneyWire.

| Step | File | Score | sha256 |
|---|---|---|---|
| step-3-enrichment | `Docs/siem/attack-mapping.md` | 0.0/0/0 | `89a01438df04d24d…` |
| step-3-enrichment | `Hub/internal/assets/assets.go` | 5.2/0.0/0.0 | `df10d33106cda1bc…` |
| step-3-enrichment | `Hub/internal/assets/assets_test.go` | 0.0/0.0/4.2 | `742dd0f28defd9e5…` |
| step-3-enrichment | `Hub/internal/attack/attack.go` | 3.6/0.0/3.0 | `8e82ae48f6bdbf30…` |
| step-3-enrichment | `Hub/internal/attack/attack_test.go` | 0.0/0.0/2.2 | `a28690515f1aa8da…` |
| step-3-enrichment | `Hub/internal/geo/geo.go` | 9.4/0.0/0.7 | `2bdeec4e9b7d55cb…` |
| step-3-enrichment | `Hub/internal/geo/geo_test.go` | 6.9/0.6/1.3 | `c142ba0862d93d12…` |
| step-3-enrichment | `Hub/internal/geo/testdata/dbip-city-test.mmdb` | data | `8e4224dc7f45fe76…` |
| step-3-enrichment | `Hub/internal/geo/testdata/dbip-country-test.mmdb` | data | `1f40c5a211747b04…` |
| step-3-enrichment | `Hub/internal/geo/testdata/gen/main.go` | 2.9/0.0/0.0 | `52ca7be2d47f80d3…` |
| step-3-enrichment | `Hub/internal/geo/update.go` | 10.7/0.0/0.0 | `c31d8f848bd88177…` |
| step-4-siem-ecs | `Hub/internal/services/siem/ecs.go` | 2.8/0.0/0.3 | `f3ccbc978e3e33c7…` |
| step-4-siem-ecs | `Hub/internal/services/siem/ecs_test.go` | 11.9/0.1/2.9 | `a48bfa8e61e296ee…` |
| step-4-siem-ecs | `Hub/internal/services/siem/http.go` | 9.4/0.0/2.1 | `af33243b20cd3cd8…` |
| step-5-honeytokens-lures | `Docs/siem/honeytoken-detection.md` | 2.8/0/0 | `967b502030d19610…` |
| step-5-honeytokens-lures | `Hub/internal/services/honeytoken/service.go` | 12.1/0.0/1.9 | `c429f3a58ee7e816…` |
| step-5-honeytokens-lures | `Hub/internal/services/honeytoken/service_test.go` | 5.8/0.0/0.0 | `7eb479b161a184b2…` |
| step-5-honeytokens-lures | `Sensors/official/FileCanary/lure.go` | 3.8/0.0/1.8 | `15c3b5f217917eb5…` |
| step-5-honeytokens-lures | `Sensors/official/FileCanary/lure_test.go` | 0.0/0.0/0.0 | `c19367273fb0f56a…` |
| step-6-web-skins | `Docs/sensors/web-skins.md` | 0.0/0/0 | `e3a2f64f83ba131e…` |
| step-6-web-skins | `Sensors/official/WebRouterDecoy/skin.go` | 6.8/0.0/1.1 | `6a2905fa32d41bc3…` |
| step-6-web-skins | `Sensors/official/WebRouterDecoy/skin_test.go` | 3.1/0.0/0.9 | `4b1244497610a894…` |
| step-7-beacons-token-receiver | `Hub/internal/services/beacon/service.go` | 8.6/0.0/1.8 | `6b9feb1962c82632…` |
| step-7-beacons-token-receiver | `Hub/internal/services/beacon/service_test.go` | 5.8/0.0/1.0 | `7a002669e1d41061…` |
| step-7-beacons-token-receiver | `Hub/internal/services/beacon/token_test.go` | 2.9/0.0/0.0 | `e04ce714e527b2f1…` |
| step-7-beacons-token-receiver | `Sensors/official/TokenReceiver/dns.go` | 1.9/0.0/0.6 | `c196e5cca2e79f7c…` |
| step-7-beacons-token-receiver | `Sensors/official/TokenReceiver/http.go` | 6.0/0.0/1.5 | `ea4272b20797345e…` |
| step-7-beacons-token-receiver | `Sensors/official/TokenReceiver/limit.go` | 4.7/0.0/0.0 | `6a3d43fea6c3eaa5…` |
| step-7-beacons-token-receiver | `Sensors/official/TokenReceiver/main_test.go` | 2.6/0.0/1.1 | `86dfa1763b4003b0…` |
| step-7-beacons-token-receiver | `Sensors/official/TokenReceiver/token.go` | 8.6/0.0/0.0 | `8ad183d360c06ab8…` |
| step-7-beacons-token-receiver | ~~`Sensors/official/TokenReceiver/main.go`~~ | **not released**: policy: wiring to the old SDK/Hub; rewrite clean | |
| step-8-decoys | `SDKs/go-truesignal/decoy/decoy.go` | 4.8/0.0/1.0 | `1678e0319cdf6cfc…` |
| step-8-decoys | `SDKs/go-truesignal/decoy/decoy_test.go` | 1.1/0.0/0.0 | `d40c1eda20d7e7cc…` |
| step-8-decoys | `Sensors/official/DatabaseDecoy/main_test.go` | 3.8/0.0/0.0 | `6ddace93212284eb…` |
| step-8-decoys | `Sensors/official/DatabaseDecoy/mssql.go` | 0.7/0.0/0.0 | `2f4c0f704e5d2d26…` |
| step-8-decoys | `Sensors/official/DatabaseDecoy/mysql.go` | 1.3/0.0/0.0 | `b73eab4e72e2a161…` |
| step-8-decoys | `Sensors/official/DatabaseDecoy/postgres.go` | 0.0/0.0/0.0 | `dd3b4ac9ed2c8395…` |
| step-8-decoys | `Sensors/official/IdentityDecoy/credcapture.go` | 6.1/0.0/0.0 | `22d0a21939e86fc3…` |
| step-8-decoys | `Sensors/official/IdentityDecoy/credssp.go` | 0.0/0.0/0.0 | `bac6b2ca5a29cbe1…` |
| step-8-decoys | `Sensors/official/IdentityDecoy/ldap.go` | 4.1/0.0/0.0 | `a0ccd35b68d1c9fa…` |
| step-8-decoys | `Sensors/official/IdentityDecoy/ldapntlm.go` | 5.4/0.0/0.0 | `6469c60310c10045…` |
| step-8-decoys | `Sensors/official/IdentityDecoy/ldapntlm_test.go` | 5.6/0.0/0.1 | `9030e52bf8e7c070…` |
| step-8-decoys | `Sensors/official/IdentityDecoy/main_test.go` | 1.5/0.0/0.2 | `6b2c382387ce3d25…` |
| step-8-decoys | `Sensors/official/IdentityDecoy/nla_test.go` | 0.6/0.0/0.0 | `0e5afbdabac22508…` |
| step-8-decoys | `Sensors/official/IdentityDecoy/ntlm.go` | 1.8/0.0/1.1 | `03132b8ed97bb5d4…` |
| step-8-decoys | `Sensors/official/IdentityDecoy/rdp.go` | 2.9/0.0/0.2 | `3a626c2497a339d2…` |
| step-8-decoys | `Sensors/official/IdentityDecoy/tlsgen.go` | 3.4/0.0/0.0 | `89e6a9f105b57dd1…` |
| step-8-decoys | `Sensors/official/NetworkServiceDecoy/dns.go` | 2.1/0.0/0.0 | `1e19a367838b97b2…` |
| step-8-decoys | `Sensors/official/NetworkServiceDecoy/main_test.go` | 1.6/0.0/0.1 | `efb2f1e7c4f38667…` |
| step-8-decoys | `Sensors/official/NetworkServiceDecoy/snmp.go` | 1.6/0.0/0.0 | `0b783f3b38d705cc…` |
| step-8-decoys | `Sensors/official/RemoteAccessDecoy/ssh.go` | 6.2/0.0/0.0 | `ab7e50601bff847d…` |
| step-8-decoys | `Sensors/official/RemoteAccessDecoy/text.go` | 5.9/0.0/0.0 | `b40f61d380286a97…` |
| step-8-decoys | ~~`Sensors/official/DatabaseDecoy/main.go`~~ | **not released**: policy: wiring to the old SDK/Hub; rewrite clean | |
| step-8-decoys | ~~`Sensors/official/IdentityDecoy/main.go`~~ | **not released**: policy: wiring to the old SDK/Hub; rewrite clean | |
| step-8-decoys | ~~`Sensors/official/NetworkServiceDecoy/main.go`~~ | **not released**: policy: wiring to the old SDK/Hub; rewrite clean | |
| step-8-decoys | ~~`Sensors/official/RemoteAccessDecoy/main.go`~~ | **not released**: policy: wiring to the old SDK/Hub; rewrite clean | |
| step-9-projections | `Hub/internal/projections/attackmap/attackmap_test.go` | 4.7/0.0/4.3 | `f6cc8ca70fef23b5…` |
| step-9-projections | `Hub/internal/projections/geomap/geomap.go` | 4.2/0.0/0.8 | `b83a030993ae6919…` |
| step-9-projections | `Hub/internal/projections/geomap/geomap_test.go` | 4.0/0.0/3.7 | `d943a3f60baa63ef…` |
| step-9-projections | `Hub/internal/projections/insights/dto.go` | 8.7/0.0/7.7 | `0bb43372a1b780b8…` |
| step-9-projections | `Hub/internal/projections/path/path.go` | 7.0/0.0/0.0 | `012198545ddd0079…` |
| step-9-projections | `Hub/internal/projections/path/path_test.go` | 2.9/0.0/0.0 | `a7c33482e6cd2c9d…` |
| step-9-projections | `Hub/internal/projections/report/report.go` | 15.0/0.0/0.2 | `93cf47f8af3a3667…` |
| step-9-projections | `Hub/internal/projections/report/report_test.go` | 4.3/0.0/4.6 | `1f2e1fa7885967ed…` |
| step-9-projections | `Hub/internal/projections/sources/sources.go` | 3.1/0.0/1.2 | `0e37755481b4b92b…` |
| step-9-projections | `Hub/internal/projections/sources/sources_test.go` | 5.4/0.0/0.0 | `b713d4b6bfd936c1…` |
| step-9-projections | `Hub/ui/src/utils/worldMap.ts` | 0.0/0.0/0.0 | `c7ea907edb9a4b46…` |
| step-9-projections | ~~`Hub/internal/projections/attackmap/attackmap.go`~~ | **not released**: over threshold {'line%': 8.3, 'fp%': 2.8, 'fpN%': 6.4, 'lit': 1} | |
| step-9-projections | ~~`Hub/internal/projections/insights/calculator.go`~~ | **not released**: over threshold {'line%': 7.6, 'fp%': 2.7, 'fpN%': 5.0, 'lit': 2} | |
| step-9-projections | ~~`Hub/internal/projections/insights/calculator_test.go`~~ | **not released**: over threshold {'line%': 3.6, 'fp%': 0.0, 'fpN%': 8.7, 'lit': 2} | |
| step-9-projections | ~~`Hub/internal/projections/insights/projection.go`~~ | **not released**: policy: wiring to the old SDK/Hub; rewrite clean | |
| step-10-siem-rules | `Docs/siem/detection-rules.md` | 0.0/0/0 | `559404cf201a2cab…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-beacon-internal-source.json` | data | `5606b2cb5a0f0c86…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-beacon-triggered.json` | data | `f6498491e4e1d578…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-beacon-unexpected-country.json` | data | `78e10a355ca2d607…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-beacon-unknown-token.json` | data | `d25772d27787bea7…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-critical-asset-source.json` | data | `58557ff73255bc30…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-decoy-interaction.json` | data | `ba6759f3867d4822…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-decoy-login.json` | data | `c32b2cd06bbf3b96…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-honeytoken-authentication.json` | data | `6ad87af226fc822c…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-honeytoken-used.json` | data | `ab3bd77dafe055a0…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-hub-defense-change.json` | data | `72c8af8a6edc1760…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-hub-login-bruteforce.json` | data | `dbf88dedbfda826c…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-hub-mfa-reset.json` | data | `aaa0bc2792addcba…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-lateral-movement.json` | data | `19ad7cf1dd6692d9…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-receiver-saturated-sustained.json` | data | `fb6050e2627475e6…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-scan-then-touch.json` | data | `1605c8e693fa7c2b…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-sensor-dark.json` | data | `965168265940d917…` |
| step-10-siem-rules | `Docs/siem/elastic/truesignal-sensor-heartbeat-lost.json` | data | `1387ef27d559f198…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-beacon-internal-source.logscale` | data | `e144bf1b85f35d86…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-beacon-triggered.logscale` | data | `ee3107174bf8be2f…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-beacon-unexpected-country.logscale` | data | `f4c9d94683d518dd…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-beacon-unknown-token.logscale` | data | `a0e60c18852a06c0…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-critical-asset-source.logscale` | data | `35ef70c89110d09a…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-decoy-interaction.logscale` | data | `a5bb70c590bcc586…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-decoy-login.logscale` | data | `f2b4b8d4d843bd03…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-honeytoken-used.logscale` | data | `87189bf42e514d2c…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-hub-defense-change.logscale` | data | `8047361650779f43…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-hub-login-bruteforce.logscale` | data | `ff18686b637b22fb…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-hub-mfa-reset.logscale` | data | `c6d49c4c93ab1484…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-lateral-movement.logscale` | data | `78612d91d1cfcdb5…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-receiver-saturated-sustained.logscale` | data | `5e0ceaf76dba5460…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-scan-then-touch.logscale` | data | `a0d279722b78aa43…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-sensor-dark.logscale` | data | `ecf202c559eb5c53…` |
| step-10-siem-rules | `Docs/siem/logscale/truesignal-sensor-heartbeat-lost.logscale` | data | `e4d9d617584220aa…` |
| step-10-siem-rules | `scripts/siem-rules/expected-elastic.json` | data | `b8a6bdfb85508568…` |
| step-10-siem-rules | `scripts/siem-rules/run-elastic.py` | 0.6/0.0/0.0 | `933b5cd65a602633…` |
| step-10-siem-rules | `scripts/siem-rules/run-elastic.sh` | 4.7/0.0/0.0 | `172c62f8a4ad7cdf…` |

## Step notes

### Step 3: enrichment (ATT&CK, assets, GeoIP)

- **Seams.** `ported.AttackMapper`, `ported.AssetInventory`, `ported.GeoLocator`. Adapt the event type to `domain.Event`/`domain.Record`.
- **ATT&CK.** `attack.For(trigger)` maps directly.
  - `NavigatorLayer(events)` is not in this module: the old project built the layer in the attack-map projection, which is withheld (step 9).
  - Implement the ATT&CK Navigator layer v4.5 from the mapping yourself: one technique entry per primary technique, score = event count, tactic from the mapping.
- **Assets.** `Validate` and `Index`/`Lookup` map directly. The stored form is the JSON array.
- **GeoIP.**
  - Config: `TS_GEOIP_DB`, `TS_GEOIP_AUTO_UPDATE` (monthly DB-IP City Lite download, off by default).
  - Only public addresses are located. A DNS beacon's `details.client_subnet` takes precedence (`basis: client_subnet`).
  - Never overwrite the memory-mapped file in place: the module opens a private copy.
  - The `testdata/*.mmdb` files are generated test fixtures (`testdata/gen`); keep the generator.
  - The UI must show "IP Geolocation by DB-IP" wherever locations appear (already done).
- **`attack-mapping.md`** becomes `docs/attack-mapping.md`. Keep the test that compares it with the code.

### Step 4: ECS renderer and HTTP SIEM transports

- **Seams.** `ported.ECSRenderer.Render(domain.Record)` and `ported.HTTPSIEMTransport.Send`.
- **Inputs.** The renderer currently takes the old project's event, audit and honeytoken types. Feed it `domain.Record` and keep its output field contract unchanged; the SIEM rules in step 10 depend on it.
- **New in this repository:**
  - render the Hub heartbeat (`event.dataset: truesignal.hub`, `event.action: hub_heartbeat`, the §6.6 counters under `truesignal.hub.*`);
  - render `node_apply_failed` like the other Hub-raised events;
  - audit records carry the **semantic action** in `event.action` (`docs/audit-actions.md`), with method + route in `http.request.method` / `url.original` and the concrete path in `url.path`.
- **Transports.** `http.go` already enforces https-only, no redirects, and transient vs terminal outcomes. Re-run §14 #10 with the real transports, including "redirect not followed".
- **Docs.** `docs/siem-integration.md` gets the ECS field table. You write it from the renderer's actual output.

### Step 5: honeytokens and lures

- **Seams.** `ported.HoneytokenService` (Ensure/Match/RecordUse/List/Inventory) over `HoneytokenStore`, and `CaptureKeyFunc`. The capture key is `TS_CAPTURE_KEY`, where the old code says `TS_CAPTURE_HASH_KEY`.
- **Honeytoken shape.** Usernames are `svc_<word><4 hex>`.
  - Matching is by username (`DOMAIN\user`, `user@realm` and DN CN/UID reduced to the bare name) or by password HMAC under the reporting node's capture key.
  - The secret never leaves the Hub.
- **Lures.** `lure.go` provides `content(path, honeytoken) → (bytes, category)`. It replaces `stubLures` in `sensors/file-canary`. Q49 answer: lures take the parent directory's owner and group, mode 0640 for credential lures and 0644 otherwise.
- **`honeytoken-detection.md`** becomes `docs/siem/honeytoken-detection.md`. Update the field names after step 4.

### Step 6: web skins

`skin.go` implements `Skins`/`Skin` for `sensors/web-router-decoy`.
- **Config.** `TS_SKIN` (`router|nas|vpn|webmail|admin|basic`) and `TS_SKIN_JSON` (a custom skin). Add both to the web decoy's v3 manifest.
- **Docs.** `web-skins.md` becomes `docs/sensors/web-skins.md`.

### Step 7: beacons and Token Receiver

- **Beacon service.** Implements `ported.BeaconService` over `BeaconStore` and the beacon master key. Types are `dns`, `web_bug` and `kubeconfig`; the UI free-text type (Q58) can become a select.
- **Token Receiver.** `dns.go`, `http.go`, `limit.go` and `token.go` are released; `main.go` is not. Write `main.go` against `sdk/go` with this behaviour:
  - **Config:** see the table below. The beacon key arrives as `TS_BEACON_KEY` (Hub-reserved).
  - **Startup:** start the DNS listener(s) (UDP + TCP) and the HTTP listener per `TS_SERVICES`.
    - Answer authoritatively only for `TS_BEACON_DOMAIN` (SOA/NS from `TS_BEACON_NS`, A records from `TS_ANSWER_IPV4`); refuse everything else; never recurse.
    - Serve the fixed 1×1 GIF over HTTP.
  - **Events:**
    - each HMAC-valid token seen (`token.go`) is reported as `beacon_triggered`, critical, with details `token`, `channel` (`dns`|`http`) plus the channel fields from `dns.go`/`http.go`;
    - at most one report per token+channel per `TS_ALERT_COOLDOWN`, counting repeats as `repeats_since_last`;
    - invalid tokens are dropped silently;
    - `limit.go` applies per-source and total TCP caps and emits `receiver_saturated` (medium, at most 1 per 5 minutes per listener).
  - **Test mode / fire drill:** a synthetic `beacon_triggered` with token `firedrill`, channel `dns`.
  - **Runtime:** UID 0 + `NET_BIND_SERVICE` (Q47), host network, on its own internet-facing node.

### Step 8: decoy helper and four decoys

- **Decoy helper.** `decoy.go` (`TS_SERVICES` parsing, capture policy, per-source limiter) consumes `sensor.Reporter` (`ReportSeverity`, `Setting`). Adapt it to that interface.
- **Decoys.** Protocol files are released. Each decoy's `main.go` is **not**: write it against `sdk/go` and the decoy helper. Each `main.go`:
  - reads its config (tables below);
  - starts one listener per `TS_SERVICES` entry;
  - hands each connection to the released protocol handler;
  - reports through the helper.
- **Event conventions:**
  - `<proto>_connection` is low, reported on connect, rate-limited per source;
  - `<proto>_login` is critical, with the captured identity;
  - Identity Decoy also reports `<proto>_query` (medium);
  - the Network Service Decoy reports `snmp_query` (medium; SET high) and `dns_query` (medium; AXFR high).
- **Test mode / fire drill:** a synthetic login event per decoy.
- **Tests.** `main_test.go` files are released where they passed screening. They call functions of the withheld `main.go`; keep the behaviours they assert and adapt them to your `main.go`.
- **Manifests.** Write v3 manifests from the tables. Use `TS_CAPTURE_KEY` for the capture key.

### Step 9: projections

- **Released:** `sources`, `path`, `geomap`, `report` (+ tests), the insights `dto.go` (output contract), and `worldMap.ts` (Natural Earth 1:110m outlines via world-atlas, ISC; record in `THIRD_PARTY.md`). Mount each as a `ported.Projection` under the Q56 names: `sources`, `attack_path`, `geo_map`, `report`.
- **Not released; implement clean:**
  - **`attack_matrix`:** for each ATT&CK tactic, its techniques with event counts and first/last seen, from step 3's mapping. Also the Navigator layer (step 3 note).
  - **`insights`:** per the released `dto.go`. These are summary findings over a time window: top sources, triggers by count, new sources versus the previous window, sensors without events (quiet decoys), and honeytoken/beacon uses. Liveness events (`sensor_*`) are excluded from counts.

### Step 10: SIEM rules and tests

The 16 Elastic rules, their LogScale twins, the catalogue `detection-rules.md` and the Kibana harness, released as-is. They target the old field names, so update them after step 4:

| Old | New |
|---|---|
| audit `event.action: "POST /api/v2/auth/mfa/disable"` | `mfa.disable` |
| `url.path: "cli:mfa-reset"` | `event.action: mfa.reset_cli` |
| `"PATCH /api/v2/config"` | `config.update`, plus `siem.update`, `webhook.update`, `system.arm` |
| `"DELETE /api/v2/events"` | `events.delete_all` |
| `"POST /api/v2/system/reset"` | `system.factory_reset` |
| `".../silence"` | `sensor.silence` |
| `"DELETE /api/v2/nodes/{nodeId}"` | `node.delete` |
| `"DELETE .../sensors/{sensorId}"` | `sensor.delete` |
| `"PATCH /api/v2/events/archive-all"` | `events.archive_all` |
| `"DELETE /api/v2/beacons/{beaconId}"` | `beacon.delete` |
| `"PUT /api/v2/assets"` | `assets.replace` |
| `"POST /api/v2/auth/mfa/recovery-codes"` | `mfa.recovery_codes_regenerate` |
| `"PATCH /api/v2/system/password"` | `system.password_change` |
| `"POST /login"` | `session.login` |

**Other changes:**
- `truesignal-sensor-heartbeat-lost` / `-dark`: also cover `node_apply_failed`.
- Add a rule for a missing Hub heartbeat (no `hub_heartbeat` for 15 minutes); this was the old project's documented gap.
- Exclude the test triggers `siem_test` / `webhook_test` (Q39).

**Testing.** The sample corpus (`detection-samples.ndjson`) is not released: it was generated from the old Hub. Write a new generator that drives this Hub's pipeline into the step-4 renderer, regenerate the corpus, update `expected-elastic.json`, and keep the Kibana CI job.

## Configuration of the decoys whose `main.go` you write

Functional description from the old manifests. `TS_CAPTURE_HASH_KEY` becomes `TS_CAPTURE_KEY`; the Hub endpoint, key, sensor id and test mode follow §4/§5.

#### Identity Decoy (AD Services Trap) (`ts-sensor-identity-decoy`)

Emulates Windows identity services (LDAP, LDAPS, RDP) so intruders enumerating or authenticating against them are detected and their usernames and credentials recorded.

Runtime: user `0:0`, network `host`, capabilities `NET_BIND_SERVICE`; listen-port keys `TS_SERVICES`.

| Key | Default | Description |
|---|---|---|
| `TS_SEVERITY` | `high` | Fallback alert severity (the sensor sets critical for logins, low for bare connections, medium for queries). |
| `TS_SERVICES` | `ldap:389,ldaps:636,rdp:3389` | Comma-separated services to run, as proto:port (proto is ldap, ldaps or rdp). Standard ports keep the decoy believable. |
| `TS_PERSONA_HOSTNAME` | `DC01` | Hostname the decoy claims (e.g. the fake DC name). |
| `TS_PERSONA_DOMAIN` | `corp.local` | Active Directory domain the decoy claims. |
| `TS_CAPTURE_PASSWORDS` | `hash` | How captured passwords are recorded: hash (keyed HMAC-SHA256 + length, default), plain (cleartext; avoid in PCI scope), none. |
| `TS_CAPTURE_NTLM` | `identity` | NTLM capture for RDP NLA and LDAP/LDAPS NTLM binds (Sicily and SASL GSS-SPNEGO): identity (default, record DOMAIN\\user + workstation), hash (also record the crackable NetNTLMv2; for threat intel, avoid in PCI scope), off (RDP mstshash cookie only; LDAP refuse |
| `TS_CAPTURE_HASH_KEY` | `` | Set by the Hub: this node's capture key (derived from the Hub's master key), so password HMACs can be matched against planted honeytokens. Any value set here is ignored. |

#### Database Decoy (MySQL / PostgreSQL / MSSQL) (`ts-sensor-database-decoy`)

Emulates MySQL, PostgreSQL and Microsoft SQL Server logins so anyone who tries a database, often with credentials taken from a config file, is detected and the account recorded.

Runtime: user `65532:65532`, network `host`, capabilities `none`; listen-port keys `TS_SERVICES`.

| Key | Default | Description |
|---|---|---|
| `TS_SEVERITY` | `high` | Fallback alert severity (the sensor sets critical for logins, low for bare connections, medium for queries). |
| `TS_SERVICES` | `mysql:3306,postgres:5432,mssql:1433` | Comma-separated services to run, as proto:port (proto is mysql, postgres or mssql). Do not reuse a port a real database on this host already uses. |
| `TS_PERSONA_HOSTNAME` | `DB01` | Server name the decoy reports (SQL Server error messages). |
| `TS_CAPTURE_PASSWORDS` | `hash` | How captured passwords are recorded: hash (default, keyed HMAC), plain (cleartext; keep out of PCI scope) or none (only that one was sent). |
| `TS_CAPTURE_HASH_KEY` | `` | Set by the Hub: this node's capture key (derived from the Hub's master key), so password HMACs can be matched against planted honeytokens. Any value set here is ignored. |

#### Remote Access Decoy (SSH / Telnet / FTP) (`ts-sensor-remote-access-decoy`)

Emulates SSH, Telnet and FTP logins so password spraying, default-credential sweeps and stolen-key use are detected and the credentials recorded.

Runtime: user `0:0`, network `host`, capabilities `NET_BIND_SERVICE`; listen-port keys `TS_SERVICES`.

| Key | Default | Description |
|---|---|---|
| `TS_SEVERITY` | `high` | Fallback alert severity (the sensor sets critical for logins, low for bare connections, medium for queries). |
| `TS_SERVICES` | `ssh:2222,telnet:23,ftp:21` | Comma-separated services to run, as proto:port (proto is ssh, telnet or ftp). Port 22 usually belongs to the host's real sshd; use it only on hosts without one. |
| `TS_PERSONA_HOSTNAME` | `srv01` | Hostname shown in the telnet prompt. |
| `TS_PERSONA_OS` | `Ubuntu 22.04.4 LTS` | Operating system line shown before the telnet login prompt. |
| `TS_SSH_VERSION` | `SSH-2.0-OpenSSH_8.9p1 Ubuntu-3ubuntu0.10` | SSH identification string. |
| `TS_CAPTURE_PASSWORDS` | `hash` | How captured passwords are recorded: hash (default, keyed HMAC), plain (cleartext; keep out of PCI scope) or none (only that one was sent). |
| `TS_CAPTURE_HASH_KEY` | `` | Set by the Hub: this node's capture key (derived from the Hub's master key), so password HMACs can be matched against planted honeytokens. Any value set here is ignored. |

#### Network Service Decoy (SNMP / DNS) (`ts-sensor-network-service-decoy`)

Emulates SNMP and a log-only DNS server so device fingerprinting, community-string guessing and DNS reconnaissance are detected.

Runtime: user `0:0`, network `host`, capabilities `NET_BIND_SERVICE`; listen-port keys `TS_SERVICES`.

| Key | Default | Description |
|---|---|---|
| `TS_SEVERITY` | `high` | Fallback alert severity (the sensor sets critical for logins, low for bare connections, medium for queries). |
| `TS_SERVICES` | `snmp:161,dns:53` | Comma-separated UDP services to run, as proto:port (proto is snmp or dns). Do not reuse a port a real resolver or agent on this host uses. |
| `TS_PERSONA_HOSTNAME` | `sw-core-01` | sysName the SNMP decoy reports. |
| `TS_SNMP_SYSDESCR` | `Cisco IOS Software, C2960X Software (C2960X-UNIVERSALK9-M), Version 15` | sysDescr the SNMP decoy reports. |
| `TS_SNMP_COMMUNITY` | `public` | The one community string the decoy answers (others get silence). Captured strings are HMAC'd either way. |
| `TS_CAPTURE_PASSWORDS` | `hash` | How captured community strings are recorded: hash (default), plain or none. |
| `TS_CAPTURE_HASH_KEY` | `` | Set by the Hub: this node's capture key (derived from the Hub's master key), so password HMACs can be matched against planted honeytokens. Any value set here is ignored. |

#### Token Receiver (beacons) (`ts-sensor-token-receiver`)

Callback endpoint for beacons (DNS tokens, web bugs, kubeconfig files) created on the Hub's Beacons page. Deploy it on its own internet-facing node; the Hub stays internal.

Runtime: user `0:0`, network `host`, capabilities `NET_BIND_SERVICE`; listen-port keys `TS_SERVICES`.

| Key | Default | Description |
|---|---|---|
| `TS_SEVERITY` | `critical` | Unused: beacon events are always critical; the Hub lowers unknown tokens to medium. |
| `TS_BEACON_DOMAIN` | `` | The zone delegated to this receiver, e.g. t.example.com. Beacons created on the Hub point into it. |
| `TS_BEACON_NS` | `` | Comma-separated name servers of the zone, as in the parent's NS records. Default ns1.<zone>. |
| `TS_ANSWER_IPV4` | `` | This receiver's public IPv4 address. A queries for the zone are answered with it, so web bugs reach the HTTP listener. Empty: A queries get NODATA (DNS beacons still fire). |
| `TS_SERVICES` | `dns:53,http:80` | Comma-separated listeners as proto:port (dns serves UDP and TCP). |
| `TS_ALERT_COOLDOWN` | `60s` | Minimum time between two events for the same token and channel (one lookup is several queries). |
| `TS_TRUSTED_PROXIES` | `` | IPs/CIDRs of a TLS front end whose X-Forwarded-For is believed. Empty: the TCP peer is the source. |
| `TS_BEACON_KEY` | `` | Set by the Hub: the receiver key that verifies beacon tokens. Any value set here is ignored. |
