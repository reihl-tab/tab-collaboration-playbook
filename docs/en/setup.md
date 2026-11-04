# End-to-end setup

Checked: 2026-11-04. Read [sources](../sources.md) before starting.
This is an operator checklist, not a claim of tested automatic enrollment.

## 0. Inputs, authority and private checklist

1. Establish the owner's instruction to set up collaboration. Record permitted
   recipients, purpose, allowed disclosures and whether consent to provider terms
   is already covered. A setup request is not unlimited permission to send email,
   make calls, spend money or publish personal data.
2. Keep these inputs in a private operator record, never this repository:
   `OWNER`, `TAB_ACCOUNT`, `INSTINCT_MAILBOX`, `TAB_MAILBOX`, authorized recipient
   set, timezone, budget (default zero), project/repository scope and approval
   rules. These uppercase labels are placeholders, not real addresses.
3. Use the account's supported secure secret store. Never request persistent
   passwords, certificate passwords, private keys or backup codes in ordinary
   chat, email, source control, screenshots or task reports. Use the provider's
   secure entry flow when secret input is needed.
4. Create a private checklist with states `not_started`, `blocked`, `verified`.
   Record stage, timestamp, non-secret evidence reference and next action. Do not
   store signed-mail bodies or certificate material in public issues.

Expected: authorized scope and known account owner. If identity, authority or
terms consent is missing, pause only the affected action. Research can continue.

## 1. Open Tab (provider UI; partly owner-dependent)

1. Visit https://tab.bot/ and read the current signup form and the Terms and
   Privacy Policy linked there. Recheck current availability and price. Do not
   assume private beta means free or immediate access.
2. The observed homepage asks for name and mobile number, a country selector,
   text-message consent and **Sign up**. Use the owner's intended identity and
   number, not an invented or assistant-owned substitute. Confirm the country
   code is applied once, as the page says it adds the code.
3. If the owner must open Tab personally, ask only for that step, then continue
   setup yourself when access exists. If existing authority and provider controls
   allow agent-led signup, fill the form, inspect the final terms/consent state
   and submit only within that authority. Do not subscribe someone else to texts.
4. Follow the site's actual next instruction. The homepage says to send one text
   to get started; use only the destination shown by the live provider. Do not
   invent a phone number, activation URL or API endpoint.
5. Confirm an actual reply in the intended Tab conversation and that it belongs
   to the intended owner. A form confirmation or waitlist entry alone is not an
   active account. Record the outcome as active, waitlisted or blocked.

Failure: wrong account, unavailable country, payment request or challenge means
stop that step and report the exact limitation. No paid upgrade or verification
bypass. Waitlisted access cannot proceed to a verified email channel.

## 2. Establish the two mailboxes (capability gate)

1. Use the maintainer account's (e.g. Instinct's) supported email capability
   and the owner's agreed sending identity. Provision a dedicated mailbox only
   through an authorized provider flow; this guide supplies no proprietary
   provisioning commands.
2. Ask Tab in its owner-confirmed conversation whether this account can send and
   receive email from a stable mailbox, receive a mailbox-validation link and
   sign/verify S/MIME or use a compatible mail client. Ask it to report capability
   status and blockers, not credentials. Do not treat an unsupported claim as a
   completed test.
3. Bind `TAB_MAILBOX` to Tab through that trusted conversation and
   `INSTINCT_MAILBOX` through the owner-approved account context. A display name,
   incoming message or self-asserted signature cannot establish this binding.
4. Confirm access to each inbox. Do not assume the mail path keeps signed
   content intact: many services re-encode inline bodies. Test it instead by
   sending a harmless signed attachment pair (section 4, step 3) in each
   direction and confirming that it verifies on arrival. Use a mail client's
   normal compose/import flow or a documented authorized mail API. No universal
   Tab email endpoint was verified.
5. Agree before sending any test: sender, exact recipient, harmless test text
   and purpose. No automatic CC, forwards, contact uploads or address-book sync.

Expected: both verified mailbox bindings and compatible email capabilities.
If one cannot sign and verify S/MIME, mark this route blocked. Do not claim
secure setup or silently downgrade to unsigned mail. The owner should not be
asked to perform routine configuration the agent can do; only a real
provider/account barrier is escalated.

## 3. Enroll each mailbox with Actalis (provider UI)

This is **S/MIME for email**, not an SSL/TLS certificate for a website. Mailbox
validation proves control of a mailbox, not a person's legal identity or authority.
The method below is generic public guidance, not an account's internal setup.

1. Open https://guide.actalis.com/smime/features and
   https://guide.actalis.com/faq/S-MIME/S-MIME . Recheck eligibility and terms.
   Actalis currently describes free MV as **Free once only**, without support.
   A certificate is tied to one address. Do not assume repeated free issuance or
   that two mailboxes automatically qualify; stop if a charge is required.
2. Open https://extrassl.actalis.it/portal/uapub/doProcess?lang=en . The observed
   public page is **Free Email Certificate**, **Step 1 - Validity check of the
   Email**. Verify the hostname and current offering before entering anything.
3. For the first mailbox, enter its real authorized address privately. Use a
   separate enrollment for the other mailbox where eligible. The FAQ requires
   ASCII email addresses. No invented legal details, shared private keys or
   broad organization validation to get around eligibility limits.
4. Open only the expected validation message in that mailbox. Inspect its sender,
   destination and link against the active enrollment before following it.
   Do not forward validation links to the other side. Follow the live enrollment
   prompts and accept terms only within the owner's grant. After the public
   first page, exact form fields are **not freshly end-to-end tested** here.
5. Actalis says a mailbox-validation link expires after 24 hours, resends are
   made up to eight times and the request is cancelled after eight days without
   completion. Check current status before requesting another certificate;
   do not create duplicates or automate repeated enrollment attempts.
6. Download the issued PKCS#12/PFX only through the legitimate issuance flow.
   Actalis says its free service generates the private key and delivers it in
   PKCS#12. Store the package and its password securely, separately from public
   records. Never print, attach to an issue or email the private package.
7. Import the certificate using the compatible client's certificate manager;
   associate it with the exact sending account, then enable signing/encryption.
   Actalis describes this generic process for common mail clients. The precise
   UI varies. Probe the actual client first; no specific Tab import UI is
   verified by this guide. Keep recoverable secure backups for decryption.

Expected: each client has its own usable certificate and protected private key,
matching mailbox, current validity and a trusted chain. Check expiry and
revocation before use. If a chain, mailbox, key or eligibility check fails,
resolve it through the provider. Never switch off certificate verification.

## 4. Bind and test the channel

1. Use the approved harmless introduction from [templates](../templates.md).
   Send a signed introduction in each direction to exchange public certificates.
   A public certificate may travel in signed mail; a private key or PFX must not.
2. At each receiver inspect the email client's S/MIME details: signature valid,
   exact sender mailbox matches the certificate, trusted chain, current validity
   and no revocation failure. A mail icon alone is not enough. Independently
   confirm that mailbox is the previously agreed actor, not merely a mailbox
   controlled by an unknown sender. Headers and display names alone are weaker.
3. **Signed-message format and verification.** Many mail services re-encode
   inline bodies (line endings, transfer encoding), which breaks an inline
   S/MIME signature even when nothing meaningful changed. So the authoritative
   text travels as an attachment `message.txt`, with a detached DER signature
   over its exact bytes in `message.txt.p7s`. The inline body only points to the
   pair and is **never authoritative**; act only on `message.txt` after it
   verifies.

   Before relying on mail, each side records the other's signing-certificate
   SHA-256 fingerprint through a trusted out-of-band channel (the pin). Verify
   each pair, for example:

   ```sh
   openssl cms -verify -binary -inform DER -in message.txt.p7s -content message.txt \
     -noverify -signer signer.pem -out /dev/null
   openssl x509 -in signer.pem -noout -fingerprint -sha256
   ```

   Expected: the first command exits zero with `CMS Verification successful`;
   the second prints `sha256 Fingerprint=<PINNED_SHA256_FINGERPRINT>`, and that
   value must equal the pinned one exactly. Any change to the bytes of
   `message.txt`, even one byte or its line endings, fails with
   `content verify error` and a non-zero exit. `-noverify` only skips building a
   CA chain: it is acceptable **only** together with this comparison against the
   pinned fingerprint. Never use it on its own or to make a failure disappear.
   A fingerprint mismatch is a failure, and a certificate change needs a new
   out-of-band confirmation before its mail is trusted. Check the certificate's
   mailbox, validity and revocation separately. Filenames and the fingerprint are
   placeholders; the commands were run against a synthetic self-signed
   certificate with OpenSSL 3.0, not real enrollment material. A valid signature
   proves integrity and mailbox control, not authorization; scope still comes
   from the signed GO ([tasking messages](workflow.md#tasking-messages)).
4. **Sign-only challenge.** After the certificates are pinned, send a second
   harmless challenge as a signed pair. The receiving side verifies it as in
   step 3 and returns the exact challenge in its own signed pair. Repeat in the
   reverse direction. Signing is required; encryption is not used for routine
   tasking today, so content, subject lines and metadata are readable in
   transit. Keep subjects generic and keep secrets and personal data out of mail.
5. Save only private pass/fail references, timestamps, mailbox bindings and
   renewal reminders. Report success only when both directions pass. An SMTP
   send result, unread message, screenshot or a sender's own claim is not proof
   of receipt, decryption or verification.

Failure: pause affected work on unknown sender, certificate change/expiry,
revocation, invalid signature, a fingerprint that does not match the pin or a
missing key. Confirm a new binding and pin through the trusted owner/Tab
conversation. Use secure key backup and the provider's revocation/reissue
process. Signed mail is not encrypted: never send sensitive content in it, and
never fall back silently to unsigned mail.

## 5. Start work and close setup

1. Agree the [role split](workflow.md) and fill one instruction template with a
   synthetic docs task, allowed repository and no external effects.
2. Require an acknowledgment naming owner, scope, expected output, blockers and
   next update. Silence is not acceptance. No shared credentials are required
   for public fork/PR work.
3. Run a harmless first issue and PR. Verify exact-head independent review and
   green CI, then a squash merge pinned to the reviewed SHA by the designated
   maintainer. Keep deployment, money, live data changes, calls and new outbound
   wording outside this test.
4. Agree the timezone, the [daily sync](workflow.md#daily-sync) times and the
   owner's [contact options](workflow.md#owner-contact-options); record them in
   the private checklist. Do not create reminders or recurring messages beyond
   what was agreed.
5. Close the private checklist only when the account, mailbox bindings,
   certificates, two-way verification and first task are verified. Otherwise
   report the completed stages and the precise remaining blocker.
