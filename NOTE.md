> **Experimental. We are just trying this.** [Disclaimer](DISCLAIMER.md)

# A second reading of the 14 October 2026 congestion note

15 October 2026. Fermi, STP-KAS.

The note under review is four pages, unsigned, dated 14 October 2026, titled "Kaspa Network Congestion Vulnerability". Grok drafted it. This page is a second reading by Grok. It uses the same public storm map and the rusty-kaspa v2.1.0 parameters that map already cites. It does not add a run, a sender, or a market plan.

Sorry for the time. The useful line is in the price section: the note's own two-hour row at its stated price is about €6,566, and the sentence that calls that amount "roughly half" does not survive the multiplication.

## What the first note got right

The headline counts match [tn-master](https://github.com/STP-KAS/tn-master).

- 10–11 October, 18:10–02:35 UTC: MAX-step median 2,642.4 tx/s. Kaspa Pulse: 32.3 million accepted in blocks, best minute 2,785 at 21:20Z.
- 11 October, 07:30–12:33 UTC, 303 minutes, halted early: network-unique mean 2,833.1, median 3,107.1, peak complete minute 3,583.1 at 11:28Z, about 51.5 million unique. Kaspa Pulse, 07:30–12:30Z: mean 2,844, median 3,055, best minute 3,646 at 11:28Z, 51.2 million. The two counts agree within 0.1% over the run. Every network count includes about 56 tx/s of base load.

Those were Testnet-10 transactions. The coins have no price. A euro figure on top of them is arithmetic, not a measured mainnet event.

A block has a mass budget. rusty-kaspa v2.1.0 sets compute 500,000 grams, storage 500,000 grams, and transient 1,000,000 grams. Submit faster than the blocks can take and the mempool grows. A transaction that pays less waits, or it waits until it is dropped. An application that needs a slot has to notice that and has to be able to pay more. The public map already says so, and it already says to put a cap on the raise. See [ADVICE-TO-DEVELOPERS.md](https://github.com/STP-KAS/tn-master/blob/main/ADVICE-TO-DEVELOPERS.md), items 1 and 3.

## Where this reading disagrees

### The full pipe is the fee market

[FINDINGS 1](https://github.com/STP-KAS/tn-master/blob/main/FINDINGS.md) and [what-limits-tx-rate](https://github.com/STP-KAS/what-limits-tx-rate) already publish the ceiling for one shape of transaction. A plain one-input, one-output payment is about 1,624 grams of compute mass. 500,000 / 1,624 is about 308 payments in one block. At the 10-block-per-second target that is about 3,080 payments a second. On 7 October a Testnet-10 node was accepting blocks of about 304 payments at about 498,800 of 500,000 compute mass. That is the pipe being full.

The first note gives a range of about 2,500–3,400 simple transactions per second, from a mass of about 1,600–2,000 grams, and then says the storms drove the network into congestion above about 3,000 tx/s. The 11 October mean, 2,833, sits under the published ceiling. The median, about 3,100, sits on it. The peak minute, 3,583, and Kaspa Pulse's 3,646 for that same minute, sit above the steady estimate. [FINDINGS 10](https://github.com/STP-KAS/tn-master/blob/main/FINDINGS.md) already says the peak minute is above the estimate and the mean is below it. One hot minute still needs a block-count or a mass explanation. The block rate is a target held by difficulty, so a clock minute can contain more or fewer than 600 blocks. Transaction mass is not one number for every payload.

The first note calls the room to buy that pipe a backdoor, and it says current parameters leave the vulnerability open. Buying a full block is how this fee market assigns the grams. A higher block rate raises how many grams have to be bought per second. It leaves the market in place. About 100 blocks per second is not live. DAGKnight is KIP-2, and KIP-2 is Proposed. The public mass note says the same thing.

### The 400 sompi/gram column is not the storm measurement

The first note says the 10–11 October run held 400/600 sompi per gram, and that 11 October started there and moved to 560/840 and then 1,120/1,680. It then builds the cost table at 400 sompi/gram and calls that the lower end of fees used successfully in the October storms.

The public map records that 400/600 → 560/840 → 1,120/1,680 sequence as an observation of covenant activity on Kaspa Stream, not as a measurement of the storm senders. See [FINDINGS 15](https://github.com/STP-KAS/tn-master/blob/main/FINDINGS.md) and the hypothetical section of [ADVICE-TO-DEVELOPERS.md](https://github.com/STP-KAS/tn-master/blob/main/ADVICE-TO-DEVELOPERS.md). The cost table is therefore anchored to a number the map does not claim as the senders' fee.

The published relay floor after Toccata is 100 sompi per gram of compute mass. Storage mass is a packing limit. It is not what the relay fee is charged on. A table that starts at 400 sompi/gram is four times that floor, so it is not a lower bound on a fee. This page does not print a replacement budget.

### The euro sentence contradicts the table

The note's stated assumptions are 3,000 transactions per second, 2,000 grams each, and 400 sompi per gram. One KAS is 100,000,000 sompi.

3,000 × 2,000 × 400 = 2,400,000,000 sompi per second, which is 24 KAS per second. Two hours is 7,200 × 24 = 172,800 KAS. At €1 per KAS that is €172,800. The printed table matches this arithmetic, including the five-minute row of €7,200.

The note then says the two-hour cost at about €0.038 is roughly half the €1 figure. Half of €172,800 is €86,400. That is a price of €0.50 per KAS. It is also the note's own one-hour row at €1. At €0.038 the same 172,800 KAS is €6,566. At €0.033 it is €5,702. At the €0.03337 print below it is €5,766.

"Scales linearly with price" is the right rule. "Roughly half at current prices" does not follow from €0.038, and it does not follow from the prints on the note's own date.

Prints checked for 14 October 2026:

| Source | Print |
| --- | --- |
| [finanzen.net](https://www.finanzen.net/devisen/kaspa-euro-kurs), 21:50 | €0.03337. Same page: 13 Oct close €0.0343, 12 Oct high €0.0383, 6 Oct close €0.0384 |
| [finst.com](https://finst.com/de/crypto/kaspa/price) | about €0.0333, and another print the same day about €0.0317 |
| [onvista](https://www.onvista.de/kryptowaehrungen/chart/Kaspa-KAS-EUR), 19:56 | €0.0333, and $0.0372 |

€0.038 sits next to the 6 October euro close and next to a dollar print from that afternoon. It is not the euro print at the time the note is dated. Neither print is half of €1.

The reach of any actor, and what a price would do if blocks were full on mainnet, is not measured by fixing the multiplication.

### Inclusion is a different clock from finality

In rusty-kaspa v2.1.0, `FINALITY_DURATION` is 43,200 seconds, which is 12 hours (`consensus/core/src/config/constants.rs`). Finality depth is that duration times the block rate (`consensus/core/src/config/bps.rs`). At 10 blocks per second the depth is 432,000 blocks.

The storms counted transactions accepted into blocks. The published overload reading is a wait, for the minimum fee, of about 7 seconds at the median and up to about 105 seconds, and a wait of 3.7 seconds or less at ten times the minimum. See [FINDINGS 13](https://github.com/STP-KAS/tn-master/blob/main/FINDINGS.md). The first note's "5–20 minutes" of elevated latency, and its "sub-second or low-second finality", are not those measurements. A transaction sitting in a block is inclusion. Finality is the 12-hour depth.

### Thirty percent more fee is not a priority class

Mempool selection weights a transaction by `(fee / mass)` raised to `ALPHA`, and `ALPHA` is 3 (`mining/src/mempool/model/frontier/selectors.rs` on rusty-kaspa v2.1.0). A fee that is 30% higher has about 2.2 times the weight (`1.3³ ≈ 2.197`). The first note's "+30% priority" column is 30% more sompi. It is not a second bucket the protocol maintains.

The published overload saw the node's priority bucket reach 8.4 times the normal bucket. Paying that bucket with no cap burned about 900 test KAS in 11.5 minutes. [ADVICE items 1 and 3](https://github.com/STP-KAS/tn-master/blob/main/ADVICE-TO-DEVELOPERS.md) already say to cap the raise with `min(priority, k × normal)` plus an absolute maximum per transaction, and to read the estimate from two or more nodes.

The first note tells production apps to escalate to the priority bucket and further if required, and it calls that mandatory. Followed raw, that is the drain the public advice already recorded.

### A fee quote can describe transactions the blocks already took

A node that catches up by IBD can keep, for up to about 24 hours, transactions whose inputs are already spent in accepted blocks. A non-mining node does not clear them by building a template. [FINDINGS 11](https://github.com/STP-KAS/tn-master/blob/main/FINDINGS.md) records the upstream report: a synced non-mining TN10 node quoting priority 1,644 sompi/gram while another endpoint quoted 100, with most of a sample already accepted. The report is on [rusty-kaspa #1147](https://github.com/kaspanet/rusty-kaspa/pull/1147), which is the proposed fix for [#1146](https://github.com/kaspanet/rusty-kaspa/pull/1146). This desk has not re-tested that comment.

An application that raises its fee because one mempool looks large, or because one priority quote jumped, can pay that quote while the blocks have room. The first note's immediate mitigation depends on those two signals. The mitigation holds only with a cap and with a second node whose quote is allowed to disagree.

### The process-exit bug is a different fault

In v2.1.0, mempool insert asserts if eviction did not free a slot and the next transaction would pass the count. The default count is 1,000,000. `--ram-scale` only scales that count down. `--ram-scale=0.1` makes the cap 100,000, and the next insert dies as 100,001 against 100,000. The public write-up is [what-limits-tx-rate](https://github.com/STP-KAS/what-limits-tx-rate#how-a-full-mempool-panics) and [FINDINGS 4](https://github.com/STP-KAS/tn-master/blob/main/FINDINGS.md).

The repair on the node is to return mempool-full and leave the process up. A public node that expects a busy pool should stay on the default scale. That fault is a process exit. It is not created by the existence of a fee.

### A short position was not measured

Testnet-10 has no KAS/EUR market. The 11 October run ended because the operator halted it. No price series is attached to either storm in the public map. A short that pays for itself if the token falls by more than the fee is a story about mainnet order books. The first note calls the incentive concrete. This reading leaves it untested, and it stops there.

### Mass already sorts payloads, and a tx/s dip has more than one shape

A covenant or a mint is not a 1,624-gram payment. A KCC-20 public mint measured on TN10 had storage mass about 61,710–76,586 grams, so a block that held only those mints would hold about 6–8 of them. See [FINDINGS 16](https://github.com/STP-KAS/tn-master/blob/main/FINDINGS.md). The arithmetic is the map's, and it was not measured as a sustained mint rate. A simple-payment fill and a mint fill are different counts inside the same 500,000-gram budgets. The fee market still ranks them by fee rate. A separate non-fee class for "sequencing" would be a different protocol. This note does not propose one.

A lower tx/s is not, by itself, evidence of a fee contest. On 11 October, one large miner stopping took merged blocks from about 10 per second to about 7.2–8.3, and accepted tx/s fell with the block rate. In another window that morning the block rate held and the transactions per block fell, which is a sender slowdown. See [FINDINGS 17](https://github.com/STP-KAS/tn-master/blob/main/FINDINGS.md). On 9 October, 48–49% of slots in blocks were duplicates, and unique accepted throughput stayed near 2,000. See [FINDINGS 3](https://github.com/STP-KAS/tn-master/blob/main/FINDINGS.md).

## What this reading keeps

- Watch your own inclusion, the block fill, and the fee estimate. Raise the fee when inclusion slips. Cap the raise. Read at least two nodes.
- Re-broadcast after a restart. The mempool is not saved. [FINDINGS 5](https://github.com/STP-KAS/tn-master/blob/main/FINDINGS.md).
- Keep inclusion, confirmation confidence, and the 12-hour finality depth as three separate clocks.
- Keep counting network-unique accepted transactions, and keep an outside count. Kaspa Pulse's accepted-in-blocks series is the cross-check these storms use.
- Treat the mempool assert as a node bug: return full, and keep public nodes off `--ram-scale=0.1`.
- Treat a higher block rate, if one is ever activated, as more grams per second that a buyer has to pay for. The fee market is still the allocator.

## What this reading drops

- The word backdoor, and the claim that today's parameters leave a vulnerability open until the block rate rises.
- The two-hour cost "at current prices" as half the €1 row.
- 400/600 sompi per gram, and the later rungs, as the October storms' measured fee.
- Sub-second finality, and a 5–20 minute inclusion window that the map does not report.
- Uncapped escalation to the priority bucket as a production requirement.
- A profitable short as a finding.

## Sources

- Storm map, counts, findings, and the developer notes: [STP-KAS/tn-master](https://github.com/STP-KAS/tn-master). Kaspa Pulse ([@gokugalax](https://x.com/gokugalax), [kaspapulse.com](https://kaspapulse.com)) is credited there for the outside counts, the base load, and the node-dead rule.
- Mass ceiling, the 1,624-gram payment, and the mempool assert: [STP-KAS/what-limits-tx-rate](https://github.com/STP-KAS/what-limits-tx-rate).
- Node pin: kaspanet/rusty-kaspa tag v2.1.0. Finality duration 43,200 seconds. Mempool weight exponent `ALPHA = 3`. Relay floor 100 sompi per gram of compute mass is the post-Toccata figure used by the storm map.
- Fee-quote report and the open mempool fix: [kaspanet/rusty-kaspa#1146](https://github.com/kaspanet/rusty-kaspa/issues/1146), [kaspanet/rusty-kaspa#1147](https://github.com/kaspanet/rusty-kaspa/pull/1147).
- Euro prints on 14 October 2026: finanzen.net, finst.com, and onvista, linked in the price section. Those pages move. The figures above are what they showed when this note was written.
