# Go-live checklist

Everything is built and pushed **private**. These are the final steps to take the
portfolio public — deliberately left for you to run.

## 1. Flip the repos to public

Make these public (Settings → General → Danger Zone → Change visibility), in this order
so links resolve as people arrive:

- [ ] `security-homelab`
- [ ] `ad-attack-chain`
- [ ] `detection-engineering`
- [ ] `webapp-pentest-juiceshop`
- [ ] `ir-threat-hunt`
- [ ] `lab-walkthroughs` (do this before `manlikefelo` — the profile README links 25 PDFs here)
- [ ] `cybersecurity-portfolio` (this meta-repo)
- [ ] `manlikefelo` (**must be public** for the profile README to render)

Or with the GitHub CLI:

```bash
for r in security-homelab ad-attack-chain detection-engineering \
         webapp-pentest-juiceshop ir-threat-hunt cybersecurity-portfolio manlikefelo; do
  gh repo edit manlikefelo/$r --visibility public --accept-visibility-change-consequences
done
```

## 2. Pin the repos on your profile

On your GitHub profile → "Customize your pins" → pin these 6, in this order:
`cybersecurity-portfolio` (first), `ad-attack-chain`, `detection-engineering`,
`webapp-pentest-juiceshop`, `ir-threat-hunt`, `security-homelab`.

## 3. Verify it looks right

- [ ] Profile README renders at `github.com/manlikefelo`.
- [ ] The meta-repo README's links all resolve (they use absolute URLs now).
- [ ] Spot-check one `reviewer-path.md` per repo.
- [ ] Click a few walkthrough links in the profile README — they point at
      `lab-walkthroughs/blob/main/...` and 404 until that repo is public.
- [ ] Confirm no `content/` folders or `.env`/session files are public (they're
      gitignored — quick sanity check anyway).

## 4. Publish the walkthrough posts

Follow [`content/PUBLISHING-GUIDE.md`](content/PUBLISHING-GUIDE.md) (local only) — the
posts are drafted and ordered; post them as each repo goes public.

## 5. Optional polish

- Add a repo description + topics (`cybersecurity`, `wazuh`, `active-directory`,
  `detection-engineering`, `pentesting`, `blue-team`, `red-team`; for
  `lab-walkthroughs` use `tryhackme`, `hackthebox`, `writeups`) to each repo for
  discoverability.
- Update your GitHub profile bio + LinkedIn headline to
  *"SOC Analyst / Cybersecurity Analyst"* to match the profile README.
