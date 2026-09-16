# vps cheap: How to Find a Genuinely Cheap VPS That Doesn't Fall Over

Most people searching "vps cheap" want one thing: a virtual private server that costs very little per month but still runs reliably enough to actually host something. The problem is that the cheapest tier at most big-name providers — Vultr's $2.50/mo, IONOS's $1/mo intro, Hetzner's €3.29/mo — looks great on the pricing page and then quietly disappoints when you try to run a real workload on 512MB of RAM and a throttled 1Gbps port.

This guide walks through what actually makes a VPS cheap (and usable), where the real entry-level deals are right now, and how DMIT — a smaller premium-route provider whose name keeps coming up in low-end-VPS discussions — fits into the picture. DMIT is not the cheapest provider on the planet, but it has a few genuinely cheap annual plans that punch well above their price tier, and understanding why requires understanding what you're actually paying for.

## What "cheap" actually means for a VPS

A cheap VPS is not just a low monthly number. It's the combination of:

- **Upfront or recurring price** — monthly, quarterly, or annual billing, with annual usually being the cheapest effective rate.
- **Specs that match the price** — 1 vCPU and 1GB RAM is the realistic floor for a usable Linux server; anything below that struggles with even a basic LAMP stack.
- **Traffic allowance** — 500GB/mo is fine for personal use; 1TB+ is the threshold where you can host a small site without worrying about overages.
- **Port speed** — 1Gbps is the floor; 4Gbps and 10Gbps matter for bursty traffic or file distribution.
- **Routing quality** — the part most cheap-VPS buyers ignore, and the part that ends up mattering most if any of your users are in mainland China or Asia-Pacific.

The last point is where the "cheap VPS" conversation usually breaks down. A $2/mo VPS in Los Angeles with generic Tier 1 transit will give Chinese visitors 250–300ms latency with noticeable packet loss during evening peak hours. A $3/mo VPS with CN2 GIA routing to the same location can deliver 140–180ms with under 0.1% packet loss. Same city, same hardware class, very different user experience. That gap is what providers like DMIT are built around.

## The cheap VPS landscape in 2026

For context, here's roughly where the mainstream cheap-VPS market sits right now:

- **Vultr** — starts at $2.50/mo for 1 vCPU, 512MB RAM, 10GB SSD, 500GB traffic. Solid global network, generic routing.
- **Hetzner** — starts around €3.29/mo (≈$3.50) for 1 vCPU, 1GB RAM, 20GB SSD, 1TB traffic. Excellent value, Europe-focused.
- **IONOS** — $1/mo intro pricing for 1 vCPU, 512MB RAM, 10GB SSD. Cheap but specs are minimal.
- **Namecheap** — VPS plans from around $6/mo with managed options.
- **LowEndBox-listed providers** — sub-$2/mo deals exist but quality varies wildly.

DMIT sits in a slightly different niche. Its entry-level annual plans start at $36.9/year (roughly $3.08/mo effective) and come with AMD EPYC processors, KVM virtualization, and — critically — premium CN2 GIA or CMIN2 routing to mainland China. That's not the absolute cheapest VPS you can buy, but it's in the same price band as Vultr's cheapest monthly plan while offering meaningfully better routing for Asia-facing traffic.

## DMIT's three network series, explained simply

DMIT splits every plan across three network series. The same plan name (e.g. "WEE" or "STARTER") can exist on different series with different routing and different pricing. Understanding this is the key to not overpaying.

**Premium Network** — Tier 1 transit plus China Telecom CN2 GIA, China Unicom AS9929, and China Mobile CMI. The lowest-latency, lowest-loss path into mainland China. This is what DMIT is known for, and it's the most expensive series.

**Eyeball Network** — Tier 1 transit plus "reasonable-effort" China routing via CMIN2 or CMI. Better than plain Tier 1 for Chinese residential users, but without the premium guarantees. Middle pricing.

**Tier 1 Network** — clean international routing with no China-specific optimization. The cheapest series. Best for workloads that don't care about mainland China latency — backups, internal tooling, VPN relays, bulk storage.

If your users are mostly in North America or Europe with no China traffic, Tier 1 is the right pick and you're wasting money paying for Premium. If you're hosting anything that Chinese visitors will touch, Premium or Eyeball is the actual value play.

## The genuinely cheap DMIT plans worth knowing about

DMIT's lineup is large, but a handful of plans are the ones that come up whenever people discuss "cheap VPS" in the context of this provider. These are the limited-stock annual plans and the entry-level monthly plans across the three locations.

### The $36.9/year WEE plans

This is DMIT's headline cheap deal, and it exists in three different forms:

- **LAX.Pro.WEE** — Los Angeles, Premium Network (CN2 GIA), 1 vCPU, 1GB RAM, 20GB SSD, 500GB traffic at 500Mbps. $36.9/year.
- **HKG.T1.WEE** — Hong Kong, Tier 1 Network (international only), 1 vCPU, 1GB RAM, 20GB SSD, 1TB traffic at 4Gbps. $36.9/year.
- **TYO.T1.WEE** — Tokyo, Tier 1 Network, 1 vCPU, 1GB RAM, 20GB SSD, 1TB traffic. $36.9/year.

The LAX Pro WEE is the one that gets the most attention because it's the cheapest way to get genuine CN2 GIA routing — usually a premium feature — for under $3.10/mo effective. The Hong Kong and Tokyo T1 WEE plans are cheaper in spirit (more traffic, higher port speed) but lack the China optimization, so they're better if you just want a clean Asia-Pacific presence without mainland routing needs.

All three sell out periodically. If you see one in stock and it fits your use case, the general advice in low-end-VPS communities is to grab it rather than wait.

### The $49.9/year LAX.Pro.MALIBU

Same routing as the WEE (CN2 GIA), but with 1TB traffic at 1Gbps instead of 500GB at 500Mbps. Same 1 vCPU / 1GB RAM / 20GB SSD. It's the natural next step up when the WEE is sold out or when 500GB/mo isn't enough.

### The $100/year LAX.Pro.PalmSpring

2 vCPU, 2GB RAM, 40GB SSD, 2TB traffic at 2Gbps. This is the plan that tends to sell out fastest in the limited annual lineup because it's the value sweet spot — the jump to 2GB RAM is the threshold where you can comfortably run Nginx + PHP + MySQL without swapping, and 2TB/mo covers a real small website.

### The LAX.Pro.TINY at $88.88/year

1 vCPU, 2GB RAM, 20GB SSD, 1TB traffic at 1Gbps. Annual billing. This is the cheapest DMIT plan that gives you 2GB of RAM, which is the realistic minimum for running an actual web stack rather than just a proxy or a bot.

## Full DMIT plan comparison: all currently listed plans

The table below covers the plans DMIT currently shows on its location pricing pages across Los Angeles, Hong Kong, and Tokyo. Prices are as listed on the official site; some limited annual plans may be out of stock at any given time.

| Plan | Location / Network | vCPU | RAM | SSD | Traffic | Port | Price | Billing | Buy |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.Pro.WEE | LAX / Premium (CN2 GIA) | 1 | 1GB | 20GB | 500GB | 500Mbps | $36.9 | Annual | [Get LAX Pro WEE](https://www.dmit.io/aff.php?aff=18446&pid=183) |
| LAX.Pro.MALIBU | LAX / Premium (CN2 GIA) | 1 | 1GB | 20GB | 1TB | 1Gbps | $49.9 | Annual | [Get LAX Pro Malibu](https://www.dmit.io/aff.php?aff=18446&pid=186) |
| LAX.Pro.PalmSpring | LAX / Premium (CN2 GIA) | 2 | 2GB | 40GB | 2TB | 2Gbps | $100 | Annual | [Get LAX Pro PalmSpring](https://bit.ly/DmiT) |
| LAX.Pro.TINY | LAX / Premium (CN2 GIA) | 1 | 2GB | 20GB | 1TB | 1Gbps | $88.88 | Annual | [Get LAX Pro TINY](https://www.dmit.io/aff.php?aff=18446&pid=100) |
| LAX.Pro.Pocket | LAX / Premium (CN2 GIA) | 2 | 2GB | 40GB | 1.5TB | 4Gbps | $16.90 | Monthly | [Get LAX Pro Pocket](https://www.dmit.io/aff.php?aff=18446&pid=137) |
| LAX.Pro.STARTER | LAX / Premium (CN2 GIA) | 2 | 2GB | 80GB | 3TB | 10Gbps | $34.90 | Monthly | [Get LAX Pro STARTER](https://www.dmit.io/aff.php?aff=18446&pid=56) |
| LAX.Pro.MINI | LAX / Premium (CN2 GIA) | 4 | 4GB | 80GB | 5TB | 10Gbps | $62.90 | Monthly | [Get LAX Pro MINI](https://www.dmit.io/aff.php?aff=18446&pid=58) |
| LAX.Pro.MICRO | LAX / Premium (CN2 GIA) | 4 | 4GB | 160GB | 7TB | 10Gbps | $87.90 | Monthly | [Get LAX Pro MICRO](https://www.dmit.io/aff.php?aff=18446&pid=81) |
| LAX.Pro.MEDIUM | LAX / Premium (CN2 GIA) | 6 | 8GB | 160GB | 15TB | 10Gbps | $199.90 | Monthly | [Get LAX Pro MEDIUM](https://www.dmit.io/aff.php?aff=18446&pid=82) |
| LAX.EB.TINY | LAX / Eyeball (CMIN2) | 1 | 2GB | 20GB | 1TB | 1Gbps | $10.90 | Monthly | [Get LAX EB TINY](https://bit.ly/DmiT) |
| LAX.EB.STARTER | LAX / Eyeball (CMIN2) | 2 | 2GB | 80GB | 3TB | 10Gbps | $34.90 | Monthly | [Get LAX EB STARTER](https://bit.ly/DmiT) |
| LAX.T1.STARTER | LAX / Tier 1 (Intl) | 1 | 2GB | 40GB | 4TB | Performance-based | $12.90 | Monthly | [Get LAX T1 STARTER](https://bit.ly/DmiT) |
| LAX.T1.MINI | LAX / Tier 1 (Intl) | 2 | 2GB | 60GB | 8TB | Performance-based | $21.90 | Monthly | [Get LAX T1 MINI](https://bit.ly/DmiT) |
| LAX.T1.MICRO | LAX / Tier 1 (Intl) | 4 | 4GB | 80GB | 16TB | Performance-based | $32.90 | Monthly | [Get LAX T1 MICRO](https://bit.ly/DmiT) |
| HKG.Pro.MINI | HKG / Premium (CN2 GIA) | 4 | 4GB | 80GB | 1.5TB | 1Gbps | $149.90 | Monthly | [Get HKG Pro MINI](https://bit.ly/DmiT) |
| HKG.Pro.MICRO | HKG / Premium (CN2 GIA) | 4 | 4GB | 160GB | 2TB | 1Gbps | $199.90 | Monthly | [Get HKG Pro MICRO](https://bit.ly/DmiT) |
| HKG.Pro.MEDIUM | HKG / Premium (CN2 GIA) | 6 | 8GB | 160GB | 2.5TB | 1Gbps | $279.90 | Monthly | [Get HKG Pro MEDIUM](https://bit.ly/DmiT) |
| HKG.Pro.LARGE | HKG / Premium (CN2 GIA) | 8 | 16GB | 320GB | 3TB | 1Gbps | $359.90 | Monthly | [Get HKG Pro LARGE](https://bit.ly/DmiT) |
| HKG.Pro.GIANT | HKG / Premium (CN2 GIA) | 12 | 24GB | 640GB | 6TB | 1Gbps | $759.90 | Monthly | [Get HKG Pro GIANT](https://bit.ly/DmiT) |
| HKG.EB.STARTER | HKG / Eyeball (CMI) | 1 | 2GB | 40GB | 2TB | 2Gbps | $59.90 | Monthly | [Get HKG EB STARTER](https://bit.ly/DmiT) |
| HKG.EB.MINI | HKG / Eyeball (CMI) | 2 | 2GB | 60GB | 3TB | 2Gbps | $89.90 | Monthly | [Get HKG EB MINI](https://bit.ly/DmiT) |
| HKG.EB.MICRO | HKG / Eyeball (CMI) | 4 | 4GB | 80GB | 4TB | 4Gbps | $129.90 | Monthly | [Get HKG EB MICRO](https://bit.ly/DmiT) |
| HKG.T1.STARTER | HKG / Tier 1 (Intl) | 1 | 2GB | 40GB | 4TB | Performance-based | $12.90 | Monthly | [Get HKG T1 STARTER](https://bit.ly/DmiT) |
| HKG.T1.MINI | HKG / Tier 1 (Intl) | 2 | 2GB | 60GB | 8TB | Performance-based | $21.90 | Monthly | [Get HKG T1 MINI](https://bit.ly/DmiT) |
| HKG.T1.MICRO | HKG / Tier 1 (Intl) | 4 | 4GB | 80GB | 16TB | Performance-based | $32.90 | Monthly | [Get HKG T1 MICRO](https://bit.ly/DmiT) |
| TYO.Pro.TINY | TYO / Premium (CN2 GIA) | 1 | 1GB | 20GB | 500GB | 1Gbps | $21.90 | Monthly | [Get TYO Pro TINY](https://bit.ly/DmiT) |
| TYO.Pro.STARTER | TYO / Premium (CN2 GIA) | 1 | 2GB | 40GB | 1TB | 1Gbps | $45.90 | Monthly | [Get TYO Pro STARTER](https://bit.ly/DmiT) |
| TYO.Pro.MINI | TYO / Premium (CN2 GIA) | 2 | 4GB | 60GB | 2TB | 1Gbps | $89.90 | Monthly | [Get TYO Pro MINI](https://bit.ly/DmiT) |
| TYO.Pro.MICRO | TYO / Premium (CN2 GIA) | 4 | 4GB | 80GB | 4TB | 1Gbps | $189.90 | Monthly | [Get TYO Pro MICRO](https://bit.ly/DmiT) |
| TYO.Pro.MEDIUM | TYO / Premium (CN2 GIA) | 4 | 8GB | 160GB | 6TB | 1Gbps | $320.90 | Monthly | [Get TYO Pro MEDIUM](https://bit.ly/DmiT) |
| TYO.Pro.LARGE | TYO / Premium (CN2 GIA) | 8 | 16GB | 320GB | 8TB | 1Gbps | $429.90 | Monthly | [Get TYO Pro LARGE](https://bit.ly/DmiT) |
| TYO.Pro.GIANT | TYO / Premium (CN2 GIA) | 8 | 24GB | 640GB | 15TB | 1Gbps | $829.90 | Monthly | [Get TYO Pro GIANT](https://bit.ly/DmiT) |
| TYO.EB.STARTER | TYO / Eyeball (CMI) | 1 | 2GB | 40GB | 2TB | 2Gbps | $55.90 | Monthly | [Get TYO EB STARTER](https://bit.ly/DmiT) |
| TYO.EB.MINI | TYO / Eyeball (CMI) | 2 | 2GB | 60GB | 3TB | 2Gbps | $85.90 | Monthly | [Get TYO EB MINI](https://bit.ly/DmiT) |
| TYO.EB.MICRO | TYO / Eyeball (CMI) | 4 | 4GB | 80GB | 4TB | 4Gbps | $119.90 | Monthly | [Get TYO EB MICRO](https://bit.ly/DmiT) |
| TYO.T1.STARTER | TYO / Tier 1 (Intl) | 1 | 2GB | 40GB | 4TB | Performance-based | $12.90 | Monthly | [Get TYO T1 STARTER](https://bit.ly/DmiT) |
| TYO.T1.MINI | TYO / Tier 1 (Intl) | 2 | 2GB | 60GB | 8TB | Performance-based | $21.90 | Monthly | [Get TYO T1 MINI](https://bit.ly/DmiT) |
| TYO.T1.MICRO | TYO / Tier 1 (Intl) | 4 | 4GB | 80GB | 16TB | Performance-based | $32.90 | Monthly | [Get TYO T1 MICRO](https://bit.ly/DmiT) |

A few things worth noting about the table. The LAX Pro WEE, MALIBU, and PalmSpring are limited-stock annual plans that periodically sell out — if a link shows no stock, the next available step up is the TINY or the monthly Pocket. The Hong Kong Premium lineup currently starts at the MINI (the smaller WEE/TINY tiers aren't listed on the HKG Premium page right now). The Tier 1 STARTER/MINI/MICRO plans are identically priced across LAX, HKG, and TYO at $12.90/$21.90/$32.90, which makes them the cheapest way to get a presence in any of the three cities without paying for China routing.

## Active promo codes that actually reduce the price

DMIT runs plan-specific recurring discounts rather than blanket site-wide sales. The codes below are the ones that have been circulating and that DMIT's own promotion pages reference.

| Code | Discount | Applies to | Billing requirement |
| --- | --- | --- | --- |
| `LAX-EB-LAUNCH-NON-MONTHLY-RECURRING-20OFF` | 20% off recurring | LAX Eyeball TINY and higher | Quarterly or above |
| `HKG-T1-ANNUALLY-45OFF-RECUR` | 45% off recurring + upgraded specs | HKG Tier 1 STARTERv2 and higher | Annual |
| `2025-TYO-T1-HI-GSL-NON-MONTHLY-30OFF` | 30% off recurring | Tokyo Tier 1 | Quarterly or above |
| `2025-TYO-T1-HI-GSL-MONTHLY-10OFF` | 10% off recurring | Tokyo Tier 1 | Monthly |

The Hong Kong Tier 1 annual deal is the standout. It's not just a 45% recurring discount — DMIT also upgrades the specs (more vCPU, double the disk, 50% more memory, better IO). That's closer to "a different product at a lower price" than a typical promo. The catch is that the upgraded plans are part of an alpha test of a new distributed storage architecture, and DMIT explicitly notes there's no SLA guarantee on data loss or IO interruptions during the test period. Back up your data.

The LAX Eyeball 20% recurring code is the more conservative pick — it applies to a mature platform and stacks cleanly on quarterly or annual billing. With it, the LAX.EB.TINY drops from $10.90/mo to roughly $8.72/mo, and annual prepay brings the effective rate lower still.

Promo codes don't auto-apply. You need to enter them at checkout, and they're plan-specific — using a Tokyo Tier 1 code on a Hong Kong plan won't work.

## What happens when you hit your traffic cap

This is a detail that catches people off guard. DMIT doesn't cut you off when you exhaust your monthly transfer. Instead, it throttles the port speed — usually to somewhere between 2Mbps and 10Mbps depending on the plan tier. The LAX Pro line, for example, throttles WEE and MALIBU to 2Mbps, TINY/Pocket/STARTER to 4Mbps, MINI/MICRO to 8Mbps, and MEDIUM and above to 10Mbps.

For SSH sessions, small API calls, and monitoring pings, 2–4Mbps throttled is still usable. For a production website, it's not. The takeaway: pick a plan whose traffic allowance comfortably covers your normal monthly usage, and treat the throttle as a safety net rather than a target.

## Payment methods and refund window

DMIT accepts Visa/Mastercard, PayPal, Bitcoin and other cryptocurrencies, Alipay, and WeChat Pay. The Alipay and WeChat options are a real convenience if you're in mainland China and don't want to deal with international card friction.

The refund window is 3 days from purchase for new orders, with proportional refunds available within 30 days on some promotional plans. Three days is shorter than the 30-day windows at bigger providers, so test what you need to test promptly after signup.

## Cheap VPS use cases: which plan actually fits

A quick mapping from what you're trying to do to the cheapest DMIT plan that handles it sensibly:

**Personal proxy, light testing, a single bot.** LAX.Pro.WEE at $36.9/year. The 500GB traffic cap is the real limit; if you stay under it, the CN2 GIA routing is identical to plans costing ten times more.

**Small website or blog with Chinese visitors.** LAX.Pro.PalmSpring at $100/year or LAX.Pro.TINY at $88.88/year. The 2GB RAM is the threshold where Nginx + PHP + MySQL runs without swapping, and 1–2TB/mo covers a real site with moderate traffic.

**Cross-border API backend or SaaS.** LAX.Pro.STARTER at $34.90/mo. The 10Gbps port and 3TB traffic handle bursty API traffic, and the CN2 GIA return path keeps Chinese client latency flat through peak hours.

**Backup server, CI runner, internal tooling — no China traffic.** Any Tier 1 STARTER at $12.90/mo. The LAX, HKG, and TYO Tier 1 STARTER plans are identically priced, so pick by geography.

**Game server for Asia-Pacific players.** TYO.Pro.STARTER at $45.90/mo or HKG.Pro.MINI at $149.90/mo. Tokyo's ~28ms latency to mainland China is the lowest among DMIT's nodes; Hong Kong's ~15ms is even lower but the entry price is higher.

**Bulk storage or bandwidth-heavy workloads with no China need.** LAX.T1.MICRO at $32.90/mo with 16TB traffic. The Tier 1 international routing is fine when China optimization isn't a factor.

## Is DMIT actually a "cheap VPS"?

Honest answer: only on the annual limited plans. The LAX.Pro.WEE at $36.9/year, the HKG.T1.WEE at $36.9/year, and the LAX.Pro.TINY at $88.88/year are genuinely cheap by any standard — they're in the same price band as Vultr's cheapest monthly tier while offering meaningfully better routing for Asia-facing traffic. The monthly Premium plans (STARTER at $34.90, MINI at $62.90) are mid-tier pricing, not budget pricing, and you're paying for the CN2 GIA routing rather than for raw spec-per-dollar.

If your use case has zero China or Asia-Pacific traffic, you're probably better served by Hetzner or Vultr at lower cost. If even a fraction of your users are in mainland China, Hong Kong, or broader APAC, the routing quality is where DMIT earns its price — and the entry-level annual plans are the cheapest legitimate way to access that routing on the market right now.

The cheapest plan that's actually in stock and fits your workload is the right pick. The limited annual plans sell out, sometimes quickly; if you see one available and it matches your use case, the general advice from low-end-VPS communities is to grab it rather than wait. 👉 [Check current DMIT plan availability and pricing](https://bit.ly/DmiT)

## A few things worth knowing before you buy

**Plans sell out — this is real, not artificial scarcity.** DMIT doesn't oversell servers, so the limited annual plans (WEE, MALIBU, PalmSpring) go in and out of stock. If one is available and fits your use case, treat that as the decision point rather than a "I'll think about it" moment.

**Free IP replacement policy.** If your assigned IP gets blocked by the Great Firewall, DMIT allows one free replacement every 15 days. After that it's $5 per change. Useful if you're running something where IP health matters.

**IPv6 routing differs from IPv4 on Premium plans.** LAX Pro's IPv4 traffic uses CN2 GIA; IPv6 traffic runs through AS4134 (China Telecom's standard network) rather than the premium GIA path. For most use cases this doesn't matter, but if you're heavily IPv6-dependent, factor it in.

**3-day refund window.** Test what you need to test promptly after signup. The window is shorter than most providers offer.

**Hardware is consistently AMD EPYC across the lineup.** Even the cheapest WEE plan runs on the same EPYC platform as the top-tier plans — you're not getting last-generation hardware at the entry level. The AN5 platform (EPYC 9005 / Zen 5) is the current flagship in Los Angeles; AN4 (EPYC 9004 / Zen 4) and AS3 (EPYC 7003 / Zen 3) are the mature, field-proven platforms that handle most plans.

## The short version

If "vps cheap" means "the lowest possible monthly number regardless of anything else," DMIT is not the answer — Vultr, Hetzner, or IONOS will undercut it. If "cheap" means "best value for what you actually pay, especially when any of your traffic touches Asia," DMIT's annual limited plans are some of the best value-per-dollar in the VPS market right now. The $36.9/year WEE plans and the $88.88/year TINY are the entry points worth checking first. 👉 [Browse all current DMIT plans and check stock](https://bit.ly/DmiT)

Pick the plan that matches your actual traffic pattern and routing needs. Don't pay for CN2 GIA if you don't have China users; don't buy Tier 1 if you do. The cheapest plan is the one whose specs and routing fit your workload — not the one with the lowest sticker price.
