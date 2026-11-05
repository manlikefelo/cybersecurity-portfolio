# Go-live checklist

Run the safety check first: Gitleaks over the full history of every repo, plus a review
of evidence images. Visibility changes are hard to take back, because public content can
be cached or forked.

## 1. Make the repos public

`lab-walkthroughs` is already public and `portfolio-website` stays private. Make these
public in this order, so links resolve as people arrive:

- [ ] `security-homelab`
- [ ] `ad-attack-chain`
- [ ] `detection-engineering`
- [ ] `webapp-pentest-juiceshop`
- [ ] `ir-threat-hunt`
- [ ] `detection-as-code`
- [ ] `adversary-emulation`
- [ ] `soc-automation`
- [ ] `sigmatest`
- [ ] `ruleguard`
- [ ] `cybersecurity-portfolio`
- [ ] `manlikefelo` (**must be public** for the profile README to render)

## 2. Require CI on detection-as-code

Require `detections-ci` to pass on `main`, so the README's "cannot be merged" claim is
true. Then open a PR with the rule from `examples/broken-rule-demo/` and capture the
blocked state.

## 3. Set up the profile

- **Name:** Felix Githure
- **Bio:** QA Engineer & Cybersecurity Analyst · Playwright, API testing, Wazuh, Sigma
- **Pins, in order:** `cybersecurity-portfolio`, `ruleguard`, `detection-as-code`,
  `ad-attack-chain`, `detection-engineering`, `sigmatest`
- **LinkedIn headline:** QA Engineer (Playwright, API Testing) | Cybersecurity Analyst
  (SOC, Wazuh, Sigma, Incident Response) | Open to QA & SOC Analyst Roles

## 4. Deploy the website

Import `portfolio-website` into Vercel, confirm `url` in `src/config/site.ts` matches the
live address, and redeploy if it changed.

## 5. Verify

- [ ] Profile README renders at `github.com/manlikefelo`.
- [ ] Every link in the profile README, the index README, and the website resolves.
- [ ] CI badges render, and the CV downloads from the website.
- [ ] No `content/` folders or `.env`/session files are public.

## 6. Publish the posts

Follow [`content/PUBLISHING-GUIDE.md`](content/PUBLISHING-GUIDE.md) (local only).
