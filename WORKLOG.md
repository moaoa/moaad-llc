# Moaad LLC — Site and Meta Verification Worklog

Last updated: 2026-11-26

## Objective

- Replace the Libyan phone number on `https://moaad.ly/` with `+1 307 296 2107`.
- Fix the missing favicon and confirm the site still passes basic checks.
- Complete the main Meta business portfolio security/verification gaps.
- Keep a clear record of what is done and what remains.

## Completed

### Landing page

- Audited the live site and found the old phone number in two places.
- Confirmed the correct source repo is `/home/moaad/Developer/moaad-llc`, branch `main`, remote `https://github.com/moaoa/moaad-llc.git`.
- Confirmed `/home/moaad/dev/moaad-landing` is a stale/different site and was not used.
- Updated `index.html`:
  - Both phone links now use `tel:+13072962107` and display `+1 307 296 2107`.
  - Added an inline SVG favicon.
- Committed and pushed as `2ac5b0e` — `Update public phone and add favicon`.
- Verified live after GitHub Pages propagation:
  - Title: `Moaad LLC — Software Product Studio`
  - Both `tel:` links are `tel:+13072962107`
  - Old phone `+218 92 806 2788` is absent
  - Favicon is present
  - `/privacy.html` and `/terms.html` return `200`
  - Meta domain verification tag is still present

### Twilio / Meta phone verification

- Twilio number `+13072962107` is the active public/business number.
- Studio flow `Forward Meta OTP` (`FW302011456619509d39edb6cf09380ef0`) was patched and published with `caller_id` set to `+13072962107`.
- Meta voice verification calls were received; the user answered and supplied the OTP.
- Meta ad-account phone verification completed; Meta showed the phone as associated with the account.

### Meta business portfolio security

- Business phone updated from the old Libyan number to `+13072962107`.
- Meta Business Suite Security Center now shows:
  - Two-factor authentication requirement: `Everyone`
  - `0 out of 1 people` need to turn on two-factor authentication
- Account-level 2FA was enabled and verified in Accounts Center:
  - `Two-factor authentication is on`
  - Method: SMS/WhatsApp to the phone ending in `90`
- Business portfolio ID: `1712909340130967`.
- Verification use case remains: `App requires access to permissions on Meta for Developers`.

### Meta business verification — started

- Started `Verify Moaad LLC`.
- Submitted country: `United States`.
- Submitted business type: `Private Company` (LLC).
- Submitted EIN, legal name `Moaad LLC`, address `30 N Gould St Ste N, Sheridan, WY 82801`, phone `+13072962107`, and website `https://moaad.ly/`.
- Solved the Meta reCAPTCHA prompt.
- Uploaded `MoaadLLC_form-a-company_wyoming.pdf` as `Certificate/Articles of Incorporation`.
- This document confirms the legal name and address but not the new phone number, so `No` was selected when Meta asked if the uploaded document included the business phone number.

## In progress / blocked

- Meta business verification is not submitted yet.
  - Meta is asking for another document containing both `Moaad LLC` and `+1 307 296 2107`.
  - No local file with that exact phone number was found.
- Second business-portfolio admin has not been added; a target email is still needed.
- Untracked `scripts/` directory in the repo was left untouched and was not committed.

## To do

1. Provide a PDF/JPG/PNG showing both `Moaad LLC` and `+1 307 296 2107`, then finish and submit the Meta business verification.
2. Provide the second-admin email, then invite that person with full access.
3. Optional hardening: add a passkey and/or a backup 2FA method.
4. Optional Meta profile cleanup: primary Page, primary business location, profile mobile, WhatsApp.
5. Optional Twilio cleanup: complete A2P registration/SMS compliance if Meta product flows need SMS later.
6. Clean up stale browser tabs and temporary files once no longer needed.

## Notes

- Do not record the EIN, passwords, or other sensitive values in this public repository.
- Browser MCP via `/tmp/opencode/browser-call.mjs` was used for the Meta/Twilio/browser work.
- Live site verification was done after the GitHub Pages CDN delay, not immediately after the push.
