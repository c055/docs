#The Dai Credit System
##Decentralized, autonomous and insured by Maker

#####Version 0.2 – 2015-10-08








*The Dai is a fungible cryptobond that allows borrowers and lenders to transact in a credit system that is permissionless and has low risk. Dai issuers (borrowers) issue Dai by posting ether and other cryptocurrency as collateral on the Ethereum blockchain, and sell these Dai on the market to Dai holders (lenders) for liquid assets. Dai holders buy Dai in order to earn yield from the collateralized debt of the issuers, or to use it as a stable cryptocurrency. Maker is the  Decentralized Autonomous Organization that operates the infrastructure of the Dai Credit System, and provides limited default insurance to its users in exchange for an insurance fee. To maximize security the Dai credit system is designed not to allow Maker to have access to collateral or issued Dai.* 









##Glossary of terms
| | |
| --- | --- |
| **Dai** | A decentralized cryptobond with price stability that pays a yield |
| **Dai collateral** | Assets that can be locked cryptographically on the Ethereum blockchain |
| **Dai issuer** | A person who borrows money from the Dai Credit System by posting collateral |
| **Dai holder** | A person who lends money to the Dai Credit System and earns yield |
| **Maker** | Decentralized autonomous organization (DAO) operating the Dai Credit System software on the ethereum blockchain |
| **Makercoin** | A cryptocurrency that insures the collateralization of the Dai |
| **SDR** | Special Drawing Right, a currency basket maintained by the International Monetary Fund |



##Value proposition

**Dai issuers use the Dai** to borrow money at low interest rates, instantly and without any requirements beyond posting adequate collateral. There are no term limits, and debt positions can opened and covered at any time. This means the Dai can service any kind of credit demand, including margin trading, business credit and mortgage financing.

**Dai holders use the Dai** to invest money in a low risk asset that pays a steady yield, and that is by design autonomously pegged 1:1 to the SDR and thus free of volatility risk. The Dai has low risk relative to most blockchain assets because every Dai is provably backed by a diversified pool of collateral on the Ethereum blockchain, as well as by Makers insurance. The Dai is also useful as a **stable cryptocurrency** designed to have no volatility risk.

**Makercoin owners gain value from the Dai** because Makercoin represents the ownership of Makers insurance service. Issuers and holders pay an insurance fee on the Dai, and Maker steadily funnels this income to Makercoin owners by buying and permanently destroying Makercoin supply, thus, decreasing the supply and increasing market price. In return Maker is forced to bail out bad debt in the event of a major collateral crash, called a black swan event. If Maker does not have enough assets on hand to cover all bad debt, the Makercoin supply is automatically inflated and auctioned off to raise funds in order to cover all the bad debt. As a result Makercoin owners are exposed to both the profits and the risk of Makers insurance service.


##How it works
###Issuance and supply

The Dai is a token on the ethereum blockchain. The Dai’s value is pegged 1:1 with the Special Drawing Right (SDR), the international currency basket maintained by the International Monetary Fund (IMF). The 2015 composition of the SDR is: 0.4230 EUR + 12.1000 JPY + 0.1110 GBP + 0.6600 USD. Any Ethereum account can hold Dai, and can transfer it freely to other accounts.

Dai tokens are created through issuance, which is the act of locking collateral into a **collateralized debt position** (CDP), a software object in the Maker contract system. This software object can hold **issuance collateral** as well as **issuance debt** that initially is equal to the amount of issued Dai. Dai must be backed by at least 150% worth of collateral at the time of issuance. The collateral can be retrieved by paying down (“covering”) the issuance debt plus interest, returning the collateral to the issuer and deleting the CDP. The collateralization ratio of individual CDPs can be verified on the Ethereum blockchain by anyone at any time.


>*__Example 1__: An issuer that locks 150 SDR worth of BTC into a CDP is able to issue 100 Dai. The effective interest rate of the debt is 2% over the following year. When the issuer wants to retrieve his BTC, 102 Dai are required to cover the CDP.*

Issuing Dai can be considered as taking a loan in the Dai Credit System. In practice the issuer is either seeking to do a margin long of the asset used as collateral, or is seeking liquidity in a hard currency (such as BTC or USD) without wanting to sell the asset used as collateral. In both cases the way the issuer actually obtains the assets that he wants, is by selling the newly issued Dai on the market. Dai holders that pay hard currency in exchange for Dai, do this in order to earn the Dai yield, which is equal to the interest rate minus the insurance rate (A variable rate).


>*__Example 2__: An issuer posts 150 SDR worth of BTC to a CDP as collateral for 100 Dai and does not sell the newly issued Dai. His net exposure stays the same as his Dai holdings (100) equals his issuance debt (100), and he can close the CDP at any time to free his 150 SDR worth of BTC.*


>*__Example 3__: An issuer issues 100 Dai by posting 150 SDR worth of BTC to a CDP, and buys another 100 SDR worth of BTC with the newly issued Dai. This gives him a 1.66x exposure to BTC/SDR volatility, and he can freely transfer the 100 SDR worth of BTC, while CDP collateral is locked until the 100 issuance debt is covered.*


>*__Example 4__: An issuer uses an Over The Counter (OTC) Ethereum contract to issue 100 Dai CDP together with a counterparty that wishes to become a Dai holder. The issuer contributes 50 SDR worth of BTC as collateral while the holder contributes 100 SDR worth of BTC. The OTC contract gives the holder the 100 newly issued Dai, and he effectively bought 100 Dai for 100 SDR worth of BTC. The issuer gains ownership of the CDP, including its 100 issuance debt, and its 150 SDR worth of BTC collateral. Since he started with only 50 SDR worth of BTC he is now 3x leveraged.*

Interest on issuance debt in a CDP accumulates with every Ethereum block. The interest of a CDP’s debt accumulates on top of the original issuance debt, and is paid by the issuer when he covers the CDP. Similarly, Dai yield accumulates every block and is paid out to the Dai holder automatically every time the Dai is transferred.


>*__Example 5__: An issuer wants to cover a CDP that was created with 100 initial issuance debt, after owning the CDP for one year. During this year, the average interest rate was 10% APR, and the issuer is thus required to pay 110 Dai in order to cover the CDP and retrieve his collateral.*


Ownership of CDP’s is transferable, but CDP’s are not fungible with each other. This allows them to be used in smart contracts that can perform more complex methods of issuance involving more than one actor, such as the 3x leverage example above.


###Price stability

The stability of the Dai 1:1 SDR peg is maintained using **interest rate adjustment** while **collateral redemption** is a mechanism for short term liquidity and price support.

Maker determines the current Dai price by polling an aggregate of price feeds, including both internal price feeds by members of the Maker organization running a software daemon, as well as independent decentralized price feeds such as Augur.

####Long term price stability

Interest rate adjustments ensure that the Dai peg remains stable over the long term through daily adjustments of the interest rate on Dai issuance. 

If the price of Dai goes below 1 SDR, the interest rate will begin increasing with approximately 1% APR per day until the Dai trades for 1 SDR again. This causes issuance to be more expensive, reducing demand for CDPs, and thus also reducing Dai supply. At the same time Dai holding will be more profitable since yield is higher, which increases Dai demand. The end result is that the Dai price will return to its ideal rate over time.

Similarly, if the price of Dai goes above 1 SDR the interest rate decreases by approximately 1% APR per day, increasing Dai supply (due to more issuance at the lower rate) and reducing Dai demand (less profit from yield), causing the Dai price to go back down until SDR parity is again reached. 

When the price of Dai is too close to the peg for Maker to autonomously determine if, and which direction, to move the interest rate, a group of human controlled Ethereum accounts called the **board of governors** are instead tasked with fine tuning the interest rate to best serve the liquidity requirements of the market. 

Every governor publishes a target interest rate that they can update and change at any time. If the peg is holding the current interest rate moves up to 1% in the direction of the **median** of the governors’ target interest rates per day.

The power of the board of governors is limited, as their input is only taken into consideration when the peg is already solid (within 1% of the ideal rate), meaning they are unable to maliciously move the interest continuously in one direction in an attempt to break the peg (since doing so would strip them of their powers until Maker autonomously adjusted the interest rate back).



####Short term liquidity and price support

To counteract supply, demand or liquidity shocks, a secondary stability mechanism exists: **collateral redemption**.

Every Dai in existence is always backed by at least 125% of its value in collateral during normal market conditions. This collateral is locked in collateralized debt positions, and the collateralization ratio of individual CDPs (as well as aggregate Dai collateralization) can be verified on the Ethereum blockchain by anyone at any time.

Each Dai has a direct claim to its collateral, and can instantaneously claim it from CDPs using the collateral redemption mechanism. Collateral redemption means that the redeemer (Dai holder) pays down the debt of someone else’s CDP, and in return “buys” a portion of that CDP’s collateral. The amount of collateral that the redeemer buys is determined relative to a price feed. The leftover collateral that isn’t redeemed gets returned to the issuer, and the CDP is deleted.

The downside to collateral redemption is that the Dai holder who wishes to redeem collateral is forced to pay a negative **bounty**, paying a higher price per unit of collateral than if they had bought at the open market.

The bounty varies based on the collateralization of the redeemed CDP, with better collateralized CDP’s having a lower bounty. For standard CDPs, the bounty starts at -10% for 175% collateralization and decreases linearly to 0% at 125%, which is called the **margin cutoff** below which collateral redemption is also referred to as **margin calling.**

The purpose of collateral redemption is to provide a large buffer of liquid assets from the CDPs in case the price of Dai suddenly drops dramatically due to shock in supply or demand. 


>*__Example__: Consider the scenario where there are still CDPs at 150% collateralization and a large Dai selloff suddenly occurs. Should sell orders at less than 0.95 SDR appear on an exchange, CDP’s with 150% or less collateralization will have their collateral redeemed by profit seeking traders who perform arbitrage by buying up the Dai valued at less than 0.95 SDR, and then using them to redeem 0.95 SDR worth of liquid collateral.*

The result is that if a major drop in the price of Dai occurs, a large amount of CDP’s will be closed due to collateral redemption, reducing supply and pressuring the price back up towards 1 SDR at a rapid response time compared to the daily interest rate adjustment mechanism. 

The below figure explains the collateral redemption curve for a standard CDP (which starts at 150% collateralization and gets margin cutoff at 125%). A more thorough explanation of what happens in the red **margin call zone** and the black **dead zone** below the margin cutoff is given in the next section.

<a href='https://ipfs.pics/Qmb98McWQbmK7m6EMKLb4poB2tuJtPQdt3vRUqLCcRnJ4C'><img src='https://ipfs.pics/ipfs/Qmb98McWQbmK7m6EMKLb4poB2tuJtPQdt3vRUqLCcRnJ4C'/></a>

###Undercollateralization 

The biggest risk to the stable value of the Dai, is the risk of undercollateralization.
Should a collateralized debt position see a massive price decrease in its collateral to the point where its collateralization ratio falls below 100%, there would no longer be enough collateral in the position to buy back all the Dai it originally issued (plus interest). If such undercollateralization events were left unchecked and allowed to happen to a significant amount of the outstanding CDPs, it could destroy confidence in the Dai and break the peg. Widespread undercollateralization is also known as a **black swan event**.

To ensure the stability of the Dai under all circumstances, Maker employs three different **risk mitigation mechanisms** to prevent undercollateralization from happening at different stages of a potential black swan event. 

The risk mitigation mechanisms are: 


+ **Margin call,** 
+ **Maker bailout,** and 
+ **Forced Makercoin inflation**
+ \* *(Listed in the order in which they would be triggered during a potential black swan event.)*


**Margin call**: The margin call for CDPs serves the same purpose as margin calls in traditional financial markets. The mechanics of a margin call work identical to collateral redemption, except the bounty which is positive rather than negative. The positive bounty means that a margin caller will earn a profit by margin calling the CDP, relative to the market price of the collateral. This incentivizes traders to instantly margin call all CDP’s that fall below the margin cutoff, enforcing a healthy collateralization of CDP’s.

Just like collateral redemption, the positive margin call bounty depends on the collateralization of the margin called CDP. At 125% collateralization, the margin call bonus is 0%, and it increases in a steep linear curve to a +20% bounty at 120% collateralization. At 120% collateralization and below, performing a margin call will give the caller the entire pool of collateral in the CDP.

**Maker bailout**: Despite the massive profit incentive for traders to perform margin calls once the collateralization of a position falls just a few percentage points below the margin cutoff, there is still a risk of one or more CDPs becoming undercollateralized (collaterization<100%, see figure 1 above). This could for instance be due to CDPs experiencing a major collateral price crash. Once a CDP becomes undercollateralized and has less collateral than it has debt, there is no longer a profit incentive for traders to margin call it.

Instead, Maker will autonomously perform a Maker bailout, using funds from the Maker vault, (Makers Dai account). The Maker vault receives an insurance fee from every debt positions, and thus always has a pool of available funds that correlates in size with the amount of outstanding debt in the system.

Should CDPs become simultaneously undercollateralized to the point where there isn’t enough Dai in the Maker vault to bail them out, Maker automatically issues Dai backed by emergency debt. Emergency debt doesn’t require external collateral but is backed by the ability of Maker to inflate the Makercoin supply. In this fashion Maker ultimately insures and secures the Dai credit system and covers all undercollateralized CDPs.

**Forced Makercoin inflation**: If Maker takes on emergency debt and doesn’t cover it in full within 1 week, forced Makercoin inflation is triggered. Until there is no emergency debt remaining, a weekly amount equal to 1% of the current Makercoin supply is automatically inflated into existence by Maker, and then put on an open auction and sold off for Dai. All proceeds from the auction are used to pay down the emergency debt, and if all the debt isn’t paid down after an auction, a new auction happens the week after with another 1% of newly inflated Makercoin. These weekly auctions continue until all emergency debt is paid down.
    
**The function of Makercoins**:  Ultimately it is the Makercoin that  insures the debt in the Dai Credit System, and is exposed to its risk. To compensate Makercoin owners for taking on this risk, every week that there **isn’t** any emergency debt, 1% of the Dai in the Maker vault are auctioned off for Makercoin in the **buy & burn auction**. All Makercoin obtained from the auctioned Dai is burned, removing it from the total Makercoin supply. The result is that, as long as there are no serious undercollateralization events, the supply of Makercoin is decreasing over time, causing its price to increase.

###Collateral requirements and debt ceilings

There are two primary factors that determine the risk of a given collateral type: Market depth and volatility. While these two factors are related - more market depth means less volatility - they still contribute separately to the overall risk and are thus each managed with a separate mechanism.

####Market depth risk

The impact of market depth on the risk of a collateral type is managed through the **debt ceiling**. In short, the debt ceiling is the maximum amount of issuance debt that can be held in CDPs that use the same type of collateral. Once the debt ceiling for a collateral type has been reached, no more Dai can be issued using the asset as collateral, until existing CDPs using the asset are closed. New Dai can still be issued using a different asset as collateral.

The debt ceiling is set so that there is always significantly more open orders on the market than there is collateral locked in CDPs. The goal is that it should be possible to liquidate every single CDP without causing slippage to the point that a black swan event occurs. For instance, if the market for ether is able to absorb 3 million SDR worth of ether without causing a crash, then the ether debt ceiling would be set at a rate below this, such as 1.5 million. Once 1.5 million Dai has been issued using ether as collateral, no further Dai can be issued that are backed by ether.

The debt ceiling for each asset type is constantly reviewed and updated by the board of governors. For more risky assets with smaller markets and less market depth, there will be routine reviews and adjustments at least every week. In the long term Maker will be able to perform some of the debt ceiling adjustments autonomously, by using a decentralized oracle to determine the approximate market depth of the collateral types.

The debt ceilings for the initial set of approved Dai collateral will depend on a multitude of factors, and will not be set until the Dai credit system launches.

####Volatility risk

Volatility of the collateral types is managed through the **volatility risk classification**, which classifies different assets based on their volatility and determines their collateral requirements based on their class. Initially there will only be two volatility classes: **Low risk and high risk.**


**The standard volatility class will initially include bitcoin, ether and Digixglobal gold.**

Initial collateral requirements for standard CDP’s is 150% collateralization. Collateral redemption is possible from 175% down to 125% collateralization, with a linear decreasing penalty for the redeemer that starts at -10% at 175% and goes to 0% at 125%. The margin call bounty goes to +20% at 120% collateralization, and encompasses the entire collateral pool below that level.


**The high risk volatility class will include Makercoin and Augur REP.**

Initial collateral requirements for the high risk class is 200% collateralization. Collateral redemption starts at -10% at 250% collateralization, goes to -5% at 200% and 0% at 150%. Margin call bounty goes to +40% at 140% collateralization.

###Governance and system security

Due to the complex nature of Maker’s business logic, it is being built using the dappsys framework so that it can be dynamically upgraded in a modular fashion while still seamlessly and securely operating the Dai Credit System.

The primary feature of dappsys is the **kernel contract**, a singular contract that serves a purpose similar to the kernel of an operating system to the Maker dapp system, while also providing a forward-compatible, non-breaking public facing interface for when other contracts need to interact with Maker.

The kernel contract has full permissions to modify anything in the Maker dapp system, and it is able to execute arbitrary input meaning it can change or delete literally any part of Maker. Performing this kind of arbitrary execution is called an **action**, and is ultimately the way every party of the Maker dapp system is deployed and controlled. To prevent abuse of these wide reaching powers, two very strong security mechanisms are in place.

The first mechanism is the primary governance system of Maker: **Makercoin voting**. Makercoin owners are able to vote to support or oppose a command that has been proposed to the kernel contract. Even if a proposal gains a majority positive votes, it still has to pass the cutoff rate of positive votes before it is added to the **action queue.**

Once an action has been queued, it doesn’t instantly execute. Instead, the second and most important security mechanism goes into effect: the **priming delay**. The priming delay means that actions have to be publicly primed for a long amount of time before they can be executed. This allows all stakeholders in the dapp system to evaluate the action long before it happens, and if they determine the action is malicious or unsafe, they have a long period where they can freely move away from using the dapp system services, with no chances of any of their money getting stuck or stolen, even in the extreme case where a majority of Makercoin voters or dynasties are malicious and actively attempt to steal the money of the users.

Priming delays will start being just a single week, but are meant to eventually last a full year when Maker dapp system has fully grown into a finished autonomous application and won’t need rapid upgrading.

To get around the cumbersome security mechanisms of the kernel contract, for day to day operations Makercoin owners can instead use their voting powers to install **dynasties.** 

Dynasties are small autonomous teams and usually have full freedom over inviting new members, and can modify their own budget within set boundaries. The idea is that team members shall be free to work as if they were a centralized organization, and can use traditional management models. Should any member of a dynasty be malicious or incompetent, the entire dynasty can be held accountable.

In the long run there will be a large amount of Maker dynasties each with their own niches, functions and specializations - examples are: development dynasties, marketing dynasties, passive investment and asset management dynasties, B2B financing sales dynasties.

The dynasty design acknowledges that organisations tend to become corrupt and inefficient over time if they aren’t constantly threatened by competition and forced to adapt and evolve. The small size and redundancy of dynasties makes it easy for Makercoin voters to “kill off” any dynasty that gives them a reason to believe it is no longer a net asset to the overall ecosystem.

Makercoin voting is designed to be reactive rather than proactive, meaning that voters will generally only be expected to vote when they are being actively harmed by incompetence or malicious intent of the dynasties. Reactive voting is generally the situation where voters are best able to mobilize form a voting majority quickly. Makercoin owners are not expected to be proactive in their voting and perform the necessary tasks such as analysing and creating proposals, since they are not getting compensated for voting and therefore cannot be expected to do work as a part of Makers routine operations.


###Long term design

As the Dai Credit System matures it will increasingly focus on servicing broader credit demand than just cryptocurrency margin trading. The restrictionless nature of the Dai means that it can be used for any type of credit, including:

+ **DAO and business credit:** An income generating business can use self-owned shares as collateral for dai issuance, where the dai is used to fund day to day operations. Dao’s can use the token that is exposed to their business profits in CDP’s, and legal companies can use a stock gateway, such as DACx, to put Ethereum listed stock in CDP’s. If the market depth of an individual company’s publicly traded stock isn’t high enough to get a useable Dai debt ceiling, they can instead use the security repackaging method described below to repackage their debt securities into an asset that will have better access to Dai credit.

+ **Legal security repackaging**: The existence of stock gateways means it is possible to repackage other legal securities into a holding company that lists its shares on Ethereum and uses them as collateral to issue Dai that are then used to buy more securities. This means the Dai Credit System can be used to finance things such as mortgages, small business credit or consumer loans. However this will not be at the Dai interest rate for the loan taker, as the holding company will need to charge a spread on the interest rate.

In the very long term the Dai will be decoupled from the SDR, and be pegged to a global consumer price index. This will be to ensure the value of the Dai stays stable to the price of goods, even in the event that the SDR becomes more volatile. After the Dai has been decoupled from the SDR and no longer targets an exchange rate, it will instead target a 2% yearly inflation rate.

The Maker governance model will move towards becoming a fully fledged futarchy in the very long run. This means that Makercoin owners could eventually become more directly involved in the governance of the system, and dynasties will be less important for ensuring day to day operations, and be relegated to tasks that require human interaction or trust on behalf of Maker.

