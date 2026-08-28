# Ahmed Sharif Khan Noor — Meta Ads Metrics Lab

Meta (Facebook) Ads-এর ফুল-ফানেল সিমুলেটর। একটা স্লাইডার নাড়ালে CPM থেকে ROAS পর্যন্ত কোন মেট্রিক কেন বদলাল — পুরো কার্যকারণ বাংলায় ব্যাখ্যা হয়।

**লাইভ ডেমো:** `https://<your-username>.github.io/<repo-name>/`

## ফিচার

- **৬টা লিভার** — Creative Quality, Audience Broadness, Market Competition, Frequency/Fatigue, Landing Page Quality, Offer Strength
- **১২টা মেট্রিক** তিন ফানেল স্তরে, প্রতিটায় লাইভ ডেল্টা (▲/▼)
- **মেট্রিকে ক্লিক** → সেই মেট্রিকের সংজ্ঞা, ইন্ডাস্ট্রি স্ট্যান্ডার্ড রেঞ্জ, কে এটাকে নাড়ায়, করণীয় ও স্কেলিং ইঙ্গিত
- **কারেন্সি সুইচ** — টাকা ↔ ডলার, রেট নিজে বসানো যায়
- **মার্জিন-ভিত্তিক ব্রেকইভেন** — ব্রেকইভেন ROAS ও CPA স্বয়ংক্রিয় হিসাব
- **ডেটা রেঞ্জ (১–৩০ দিন)** — দিন বাড়লে Frequency বাড়ার প্রভাব ধরে দৈনিক ROAS চার্ট, ব্লেন্ডেড ROAS আর ডেটার নির্ভরযোগ্যতা
- **স্কেলিং অ্যাডভাইজার** — Hold / Optimize / Wait / Horizontal / Expand / Scale Steady / Scale Hard, সাথে বাজেট ল্যাডার
- **বটলনেক ডায়াগনোসিস + সেনসিটিভিটি র‍্যাংকিং** — কোন লিভার নাড়ালে ROAS সবচেয়ে বেশি বাড়বে
- **৬টা প্রিসেট সিনারিও** — Eid/Q4 রাশ, ক্রিয়েটিভ ফাটিগ, ন্যারো অডিয়েন্স, স্লো ল্যান্ডিং পেজ ইত্যাদি
- মোবাইল-ফ্রেন্ডলি, কীবোর্ড অ্যাক্সেসিবল, `prefers-reduced-motion` সাপোর্টেড

## GitHub Pages-এ চালু করা

1. রিপোতে `index.html` (আর চাইলে এই `README.md`) পুশ করুন
2. **Settings → Pages → Source: Deploy from a branch → `main` / `root`**
3. এক-দুই মিনিটে লিংক লাইভ হবে

কোনো বিল্ড স্টেপ, npm বা ব্যাকএন্ড লাগে না — পুরোটা একটাই HTML ফাইল।

## মডেল সম্পর্কে

নাম্বারগুলো Meta auction-এর সরলীকৃত কিন্তু সঙ্গতিপূর্ণ মডেল:

```
CTR       = (1.56 + 0.0223 × (Creative − 50)) × fatigue
Relevance = 1.4 + 2.25 × CTR%
CPM       = 338 × f(Relevance) × f(Competition) × f(Audience) × f(Frequency)
Impressions = বাজেট ÷ CPM × 1000
Clicks → LP Views → Add to Cart → Purchases  (প্রতি ধাপে আলাদা রেট)
```

বেসলাইন বাংলাদেশি ইকমার্সের সাধারণ রেঞ্জে ক্যালিব্রেট করা (CPM ৳৩৩৮, CTR ১.৫৬%)। এটা শেখার টুল — বাস্তব ক্যাম্পেইনে learning phase, attribution window ও audience overlap-ও কাজ করে।

## লাইসেন্স

MIT — শেখানো, ফর্ক করা, নিজের মতো বদলানো সব চলবে।
