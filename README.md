# meetings and links

**Group Chat:** https://t.me/LSPstandards
Join for invite to bi-weekly calls

**Website:** https://balls.dev


**6/22/2022 10AM UTC - LSP Spec Meeting**

**Attendees:** 
John Carvalho, Zero Fee Routing, Yaacov Slama, Reza Bendegi, Severin Buhler (lnrouter.app), Pavel Nikolov, Nick Slaney
Notes by Nick Slaney

Reza looked at Yaacov’s specs
Blocktank allows user to request LSP channel with channel specs
- Channel is set up before user makes any payments
Breez works by user telling LSP about a payment they’re looking to receive and LSP opens channel and takes fee in line
- Payee can decide not to accept LSP feerate, and channel is not opened
- LSP decides channel size
- User could request different channel size
Breez shares payment secret with LSP
- Payment secret is not the preimage
- Payment secret = payment address
How does breez choose what size channel to make when requested?
Where is trust in the system?
- Blocktank – user trusts LSP to open channel
-- Might be able to make this trustless
-- Allow user to pay on-chain, LSP opens channel from there
- Breez – user does not have to trust LSP
API should provide fee information etc.
Fees
- Different ways user could want to pay fees
- Upfront
- Only routing fees– likely opened from user
- Combo – tiers, other methods, feerates, lending rates etc.
- Recurring channel maintenance fees
-- Could signal counterparty the need to pay a fee to keep channel open
-- Could raise fees with inactivity
- User can check on channel lease, – or LSP can signal to user
API could use liquidity ads, or communicate out of band (onion messages/bolt12?), potentially offer combination of both



**6/8/2022 10AM UTC - LSP Spec Meeting**

**Attendees:** 
Bosch, John Carvalho (Blocktank), Reza Bandegi (Blocktank), Pavel Nikolov, Akiba Slama (Breez), Roy Sheinfeld (Breez), Lucas de C. Ferreira (LL)
Notes by Nick Slaney

Want to make APIs common
Blocktank all open source, comparing to Breez etc.
Roy would like to open Breez to third party LSPs
Wants to keep LSP open source
“Marketplaces”
- How to represent to user that there are LSP options?
- UI to allow choice
- Or maybe wallet chooses LSP automatically in the background
- API to match users with LSPs
- How to choose the right LSP?
- Single or multiple LSPs
- Magma
- Pool
- Liquidity Ads
-- Has mechanism to punish channel openers when they close too early
-- Roy prefers to focus on web interface / HTTP
Simple URL standard- request / responses
Agree on basic API
- Next step is marketplaces– how to find / pick different / new LSPs
- How do we rate LSPs? Reputation? BOS score
- 1. Showing pricing for channels, commitment, selling automating channels
- John - we could expand to a lot of things
- Roy - LSP should be focused on selling channels
- Peerswap, offline payments etc. should be LWS
(Roy wants LSP to be focused on channels only)
- Trampoline payments, onion messages OK, LSP represents closest node
- Fiat conversion– mobile notifications offline
- Synonym’s Hub product feels different from an LSP, so distinction can make sense
Breez + Blocktank (Akiba + Reza) will try to merge an API
- Breez is GRPC
- Blocktank is REST
- GRPC or REST? Both?
- Will work on converging APIs
May need features from the node implementations
Can do things in plugins– but would be better to have nodes code things in – LSP version of a node
Should get more LSPs into the group
