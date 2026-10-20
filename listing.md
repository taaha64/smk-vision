# Chrome Web Store submission — SMK Vision 5.1.0

Everything below is ready to paste. Fields are in the order the dashboard asks for them.

---

## STORE LISTING tab

**Item name** (max 75)
```
SMK Vision — Screenshot Question Answerer
```

**Short description / summary** (max 132 — this is the manifest `description`, already set)
```
Screenshot answers with independent single-model and parallel-review pipelines, plus your own in-page hotkeys.
```

**Category:** Productivity
**Language:** English (United States)

**Detailed description** (paste as-is)
```
SMK Vision answers the question that is on your screen.

Press one shortcut. It screenshots the visible tab, sends it to the AI models you have
configured, and shows the answer in a small panel in the corner of the page. Click the
answer to copy it. The panel clears itself after five seconds.

WHAT MAKES IT DIFFERENT

Most tools ask one model and hope. SMK Vision can ask several at once, then have one of
them re-solve the question from the original screenshot and settle any disagreement. You
can see what every model said and how long each one took.

SET UP IN ONE STEP

Paste one API key for any supported service and press Save. That is the entire required
setup.
  - Google Gemini, Groq, OpenRouter and Mistral all offer free tiers
  - OpenAI is supported for paid accounts
  - Models, timeouts and the prompt are tucked under Advanced and are entirely optional

THREE CARE LEVELS

  - Fastest - one model, direct answer
  - Balanced - the models you pick, double-checked
  - Most careful - every model you have a key for, double-checked

MORE THAN MULTIPLE CHOICE

Multiple choice, multiple-select, fill in the blank, true/false, dropdowns, matching and
ordering, calculations, written answers and code. Answers come back as the answer alone -
no preamble, no restating the question, no explanation you did not ask for.

YOUR KEYS STAY YOURS

  - API keys are stored only in your own browser
  - They are never sent anywhere except to the service you chose
  - Screenshots are never saved by the extension
  - No account, no server of ours, no analytics, no tracking, no remote code
  - Keys are stripped out of every error message

ALSO INCLUDED

  - Select a region instead of capturing the whole screen
  - Your own keyboard shortcuts, including combinations Chrome refuses to assign
  - The last 10 answers are kept locally and can be redisplayed with no new request
  - Dark, light and follow-system themes
  - Cancel a request mid-flight

REQUIREMENTS

You need your own API key from one of the supported services. Several of them have a free
tier. SMK Vision does not resell access and does not include credits.
```

**Screenshots** — upload in this order:
| File | Shows |
| --- | --- |
| `screenshot-1-one-api-key.png` | The whole required setup: one key, one care level |
| `screenshot-2-answer-on-page.png` | The answer panel on a question page |
| `screenshot-3-popup.png` | The toolbar popup |
| `screenshot-4-keyboard.png` | Chrome shortcuts plus custom hotkeys |
| `screenshot-5-advanced.png` | Advanced panel, for reviewers who want to see the depth |

**Store icon:** `store-icon-128.png` — 128x128 PNG with the 16px transparent safe margin the store expects.
(The extension's own `icons/icon128.png` is edge-to-edge on purpose, which is right for the toolbar
but looks oversized in a listing row. Use `store-icon-128.png` for the dashboard field.)

**Small promo tile:** `promo-tile-440x280.png` (optional but recommended)

---

## PRIVACY tab

**Single purpose description**
```
SMK Vision captures a screenshot of the page the user is currently viewing, sends it to an
AI vision model the user has configured with their own API key, and displays the model's
answer to the question in that screenshot as an overlay on the page.
```

**Permission justifications**

`activeTab`
```
Used to capture a screenshot of the tab the user explicitly invokes the extension on, via
the toolbar button or a keyboard shortcut. No capture happens without that explicit action.
```

`tabs`
```
Used to read the URL of the tab an answer was captured from, so that a saved answer is only
re-displayed on the same page it came from, and so the extension can refuse to run on pages
Chrome does not allow extensions to modify.
```

`scripting`
```
Used to inject the answer overlay and the area-selection rectangle into the page on demand
when the user runs the extension. Nothing is injected until the user acts.
```

`storage`
```
Used to store the user's own API keys, their preferences, their custom hotkeys and their
last 10 answers locally in their browser. Nothing is transmitted to us.
```

`offscreen`
```
Used to run model requests inside an offscreen document so a request that takes longer than
the service worker lifetime is not killed halfway through.
```

`clipboardWrite`
```
Used to copy the answer to the clipboard when the user clicks the answer panel.
```

**Host permission justification** (`http://*/*`, `https://*/*`)
```
Two features need access to ordinary web pages. First, the answer overlay has to be drawn on
whatever page the user is reading, including re-displaying a saved answer on the tab it came
from, which activeTab alone cannot do. Second, the user's own custom keyboard shortcuts are
detected by a small content script that listens only for the specific key combinations the
user configured in settings; it reads no page content and holds no API keys. Page content is
never read, scraped or transmitted - the only thing sent anywhere is a screenshot image the
user explicitly asked for.
```

**Remote code:** select **No, I am not using remote code.**
(Verified: no `eval`, no `new Function`, no externally hosted scripts or stylesheets.)

**Data usage — tick only these**
| Type | Collected? | Why |
| --- | --- | --- |
| Personally identifiable information | No | |
| Health information | No | |
| Financial and payment information | No | |
| Authentication information | **Yes** | The user's own API keys are stored locally so requests can be made on their behalf |
| Personal communications | No | |
| Location | No | |
| Web history | No | |
| User activity | No | |
| Website content | **Yes** | A screenshot of the visible tab is sent to the AI provider the user configured |

**Then tick all three certifications:**
- I do not sell or transfer user data to third parties, outside of the approved use cases
- I do not use or transfer user data for purposes that are unrelated to my item's single purpose
- I do not use or transfer user data to determine creditworthiness or for lending purposes

**Privacy policy URL:** host `privacy-policy.html` (next to this file) anywhere public and paste the URL here. Required — submission stays locked without it.

---

## DISTRIBUTION tab

- **Visibility:** Public (or Unlisted if you only want to share the link)
- **Distribution:** All regions, or narrow it as you prefer
- No "contains ads", no in-app purchases

---

## Before you hit Submit

- [ ] Upload `smk-vision-5.1.0.zip` (built separately — store assets are NOT inside it)
- [ ] Store icon uploaded (`store-icon-128.png`)
- [ ] All 5 screenshots uploaded
- [ ] Privacy policy hosted and URL pasted
- [ ] All 7 permission justifications filled
- [ ] Remote code = No
- [ ] 3 certification boxes ticked
