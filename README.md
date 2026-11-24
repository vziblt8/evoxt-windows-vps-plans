# Cheap Windows VPS: What $2.99 a Month Really Buys, How the 180-Day Windows Licence Works, and When You Need a Bigger Plan (All Evoxt Plans Compared)

A cheap Windows VPS in 2026 costs roughly $3 to $6 a month for 1–2 GB of RAM. Evoxt sits at the bottom of that band: VM-0.5 is $2.99/month, and the 2 GB VM-1 is $5.99/month. Neither price carries a Windows surcharge the way some competitors do. Evoxt's public pages also don't state whether a licence is included, and that gap matters more than the plan price, because an unlicensed Windows Server shuts itself down every hour once the 180-day evaluation expires.

What follows covers all 11 Evoxt plans, the licence mechanics that decide your real annual cost, the two-session RDP ceiling that hits small teams, and which plan fits a single user, three colleagues, or a .NET and SQL Server workload.

> **Most readers should buy VM-1 at $5.99/month.** 1 vCore, 2 GB RAM, 20 GB storage, 300 GB monthly transfer, weekly offsite backup included. It is the smallest Evoxt plan with enough RAM to hold a Windows desktop session without constant paging, and 2 GB is also Microsoft's stated floor for Windows 11 Pro.
> 👉 [Deploy the VM-1 Windows plan](https://console.evoxt.com/deploy.php?aff=1168)

## Every Evoxt plan, side by side

Evoxt sells one VM family in 11 sizes. Each step up adds cores, RAM, disk and monthly transfer together, so there is no odd plan with plenty of one resource and very little of another.

| Plan | vCPU / RAM | Storage / monthly transfer | Price (USD, monthly) | Order |
| --- | --- | --- | --- | --- |
| VM-0.5 | 1 core / 512 MB | 5 GB / 150 GB | $2.99 | Deploy |
| VM-0.75 | 1 core / 1 GB | 10 GB / 250 GB | $4.99 | Deploy |
| VM-1 | 1 core / 2 GB | 20 GB / 300 GB | $5.99 | Deploy |
| VM-1.5 | 2 cores / 2 GB | 20 GB / 300 GB | $6.95 | Deploy |
| VM-2 | 2 cores / 4 GB | 30 GB / 600 GB | $11.99 | Deploy |
| VM-3 | 4 cores / 4 GB | 30 GB / 700 GB | $14.99 | Deploy |
| VM-4 | 4 cores / 8 GB | 60 GB / 1,000 GB | $23.99 | Deploy |
| VM-6 | 8 cores / 8 GB | 60 GB / 1,250 GB | $29.99 | Deploy |
| VM-8 | 8 cores / 16 GB | 80 GB / 2,000 GB | $47.99 | Deploy |
| VM-12 | 16 cores / 16 GB | 80 GB / 2,500 GB | $60.95 | Deploy |
| VM-16 | 16 cores / 32 GB | 100 GB / 4,000 GB | $95.99 | Deploy |

All 11 plans include a weekly offsite backup at no extra cost. Additional IPv4 addresses are $3/month each. Billing runs from monthly up to three years, and you can top up account credit and let Evoxt apply it to future invoices.

Two notes on the numbers. Prices above are monthly list prices in USD for the standard region. Evoxt also sells Premium and Premium Plus regions with adjusted bandwidth allowances and different list prices; VM-0.5, for example, is listed at $3.49/month on Premium Plus. The deploy screen shows the final figure for whichever region you pick, so check it there before paying. VPSBenchmarks recorded the same VM-1, VM-2, VM-4 and VM-8 prices in August 2026 as the official list, which suggests the standard pricing has been stable rather than promotional.

## The $2.99 plan can run Windows. That doesn't make it usable.

Evoxt's Windows RDP page starts its plan list at VM-0.5, the 512 MB box. Treat that as a listing, not a recommendation. Windows 11 Pro won't install below 2 GB of RAM, and a Windows Server install with a graphical desktop will page heavily at 512 MB before you have opened a browser. The 5 GB disk is the harder limit: a patched Windows Server install plus updates can consume most of it, leaving nothing for your application, logs, or the weekly backup restore you might need.

VM-1 at $5.99 is the first plan where a Windows desktop is a working environment rather than a demo. 20 GB of storage is still tight for Windows. If you plan to install SQL Server, Visual Studio, a trading terminal with years of chart history, or anything that writes logs continuously, start at VM-2 with 30 GB and 4 GB of RAM at $11.99.

## What the sticker price leaves out: the 180-day licence clock

Microsoft's evaluation build is what most budget providers install, and it behaves the same way everywhere. You get 10 days to activate online. The install then runs in full for 180 days, with the remaining days displayed on the desktop. On day 181 the server keeps its data and installed software, but Windows shuts down every hour and accepts only security updates until a licence is applied. Adding a key converts the existing installation in place, with no reinstall.

A Windows Server licence is real money, and the two common ways providers handle it show up clearly in their prices. MassiveGRID charges $6.31 per vCPU on top of the plan price, or lets you bring your own key. VMHeaven states outright that no licence is included and that the price covers the server only, with RDS CALs not sold at all. Atlantic.Net takes the opposite route: its Windows plans ship with licensed editions, and the page from March 2023 priced Windows at $15/month against $4/month for the equivalent Linux plan. That $11 gap is roughly what the licence costs inside a monthly price.

Evoxt doesn't publish a Windows licence line item, and a third-party review of the provider describes Windows Server as available on any plan at no extra cost. No surcharge and an included licence are two different things, though. Before you pay, open the deploy screen and read what the Windows image is labelled as, or ask support directly whether the template is an evaluation build or a pre-licensed install. That single answer can change your first-year cost by more than the server itself.

👉 [Check which Windows images Evoxt offers on the deploy screen](https://console.evoxt.com/deploy.php?aff=1168)

## Two admin sessions, then the bill changes

Windows Server includes two simultaneous Remote Desktop sessions for administration. A third person logging in at the same time needs the Remote Desktop Session Host role plus RDS CALs from Microsoft, and that is a separate purchase from the VPS.

How much this costs depends entirely on the provider. MassiveGRID sells extra users at $8.90 per user per month. VMHeaven does not sell RDS CALs at all, so a three-person team has to source them independently. Evoxt doesn't publish an additional-user price, which means the CAL question goes to Microsoft either way.

The practical consequence: a three-person setup on a $5.99 VPS is not a $5.99 project. You are looking at the VPS, three CALs or a per-user fee, and enough RAM for three concurrent desktop sessions. That usually pushes the machine to VM-2 or VM-3 territory before the licensing conversation even starts.

## Server 2025, 2019, or desktop Windows 11?

Windows Server 2025 is Microsoft's current default for new server deployments. Server 2016, 2019 and 2022 remain available for software that hasn't been certified on the newer release, and most budget hosts still offer the full spread. Evoxt's pricing page doesn't list OS versions; the deploy screen is where the actual image list appears.

Windows 10 reached end of support on 14 October 2025 and no longer receives security updates. If you are moving an existing workload off Windows 10, plan for Windows 11 Pro or Windows Server rather than reinstalling the same desktop OS.

Desktop Windows is a special case on any VPS. Microsoft does not let hosting providers rent Windows 10 or 11 licences, so providers supply the desktop template unactivated and you enter your own product key after first login. Desktop editions also allow only one interactive session, so they suit a single remote worker or a single trading terminal, not a team.

## Picking a plan by workload

**One person, one app that has to stay online.** A trading terminal, a bot, a scraping job, or a remote work desktop. VM-1 at $5.99. If the app is memory-hungry, such as MetaTrader with several charts open or a browser-based dashboard, VM-2 at $11.99 buys 4 GB and doubles the disk to 30 GB.

**A small IIS site with a light database.** VM-2 or VM-3. SQL Server needs RAM before it needs cores, so VM-3's 4 cores and 4 GB is a worse database box than VM-4's 4 cores and 8 GB at $23.99. If the database is SQL Server Express, VM-2 is usually enough to start.

**Two or three people on RDP at once.** VM-2 minimum, VM-3 or VM-4 if they run heavy desktop software. Budget for RDS CALs separately, and check whether Evoxt will support the Session Host role on the plan you choose before you commit a year.

**Fastest possible path to a working desktop.** VM-1, Windows image selected at deploy, connect over RDP. Evoxt's browser-based VNC console is the fallback if a firewall rule or a changed RDP port locks you out, which is the failure mode that matters most on a self-managed Windows box.

👉 [Deploy VM-2 if you need 4 GB and a 30 GB disk](https://console.evoxt.com/deploy.php?aff=1168)

## Where Evoxt sits against other cheap Windows VPS

The headline prices across this segment differ by a factor of five, and almost none of the difference is about CPU speed. It is about whether a licence is bundled, whether cores are shared, and how many users can log in at once.

| Provider | Windows entry price | Licence included? | Extra concurrent users | Console access |
| --- | --- | --- | --- | --- |
| Evoxt | $2.99/mo (512 MB), $5.99 (2 GB) | Not stated publicly; no Windows surcharge listed | Windows default of 2; additional users not priced publicly | Custom panel + browser VNC |
| MassiveGRID | $3.99/mo | 180-day evaluation, or +$6.31 per vCPU | $8.90 per user/month | Not stated |
| VMHeaven | €4.99/mo (Amsterdam) | Evaluation only; bring your own key | Not sold; RDS CALs from Microsoft | VNC console |
| Atlantic.Net | $15/mo (page dated March 2023) | Licensed editions included | Not stated | Not stated |

Read that table as four different products rather than four prices for the same thing. Atlantic.Net's $15 includes the licence, so it is not five times the cost of a $2.99 plan that leaves you to license Windows yourself. MassiveGRID's $3.99 becomes $10.30 on a single-core plan once you add the $6.31 licence, and VMHeaven's €4.99 is a server with an evaluation clock running.

Evoxt's position is unusual in that it doesn't charge a Windows premium and doesn't publish a licence position. Its other specs are ordinary for the segment: 18 data centres across four continents, a custom control panel, a browser VNC console, firewall rules you can set without connecting to the machine, floating IP reassignment, VM cloning, and a REST API. It does not bill hourly, does not advertise DDoS protection, and accepts credit cards, PayPal and Bitcoin.

## Before you pay: six things to confirm

1. **The licence status of the Windows image.** Evaluation or licensed. Ask before you deploy, not after day 180.
2. **The region.** Standard, Premium and Premium Plus carry different prices and bandwidth allowances. The number on the pricing page may not be the number at checkout.
3. **Disk headroom.** 20 GB on VM-1 is enough for Windows and one application, not for Windows, SQL Server and a year of logs.
4. **RDP hardening from day one.** Change the port off 3389, restrict the firewall rule to your own IP, and keep Network Level Authentication on. Set the firewall rule before you change the port, or you lock yourself out.
5. **Backup expectations.** Weekly offsite backup is included on every plan, but a reinstall wipes the disk. Take a manual snapshot before big changes if the panel offers one.
6. **Billing term.** Monthly to three years. A long prepay locks the price and locks you in equally.

One user with one application that must stay up: VM-1 at $5.99. Two or three people, or a database: VM-2 at $11.99 and upward, with RDS CALs in the budget. The licence answer is the one line that can dwarf the plan price, so settle it on the deploy screen before anything else.

👉 [Start with VM-1 and confirm the Windows image at checkout](https://console.evoxt.com/deploy.php?aff=1168)
