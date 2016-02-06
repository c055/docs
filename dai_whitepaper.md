#The Dai Credit System
##Decentralized, autonomous and insured by Maker

#####Version 0.3 – 2016-01-31








*The Dai is a stable, deflationary cryptocurrency that enables borrowers and lenders to transact in a credit system that is permissionless and has low risk. Dai issuers (borrowers) issue Dai by posting ether and other cryptocurrency as collateral on the Ethereum blockchain, and sell these Dai on the market to Dai holders (lenders) for liquid assets. Dai holders use the Dai as a stable cryptocurrency for trade, and to earn capital gains from its deflation. Maker is the Ethereum powered Decentralized Autonomous Organization that operates the infrastructure of the Dai Credit System, and provides default insurance to its users in exchange for an insurance fee.* 









##Glossary of terms
| | |
| --- | --- |
| **Dai** | An Ethereum based cryptocurrency with short term price stability and long term price deflation |
| **Dai collateral** | Assets that can be locked cryptographically on the Ethereum blockchain |
| **Dai issuer** | A person who borrows money from the Dai Credit System by posting collateral |
| **Dai holder** | A person who lends money to the Dai Credit System and earns capital gains from Dai deflation |
| **Maker** | Decentralized Autonomous Organization (DAO) operating the Dai Credit System infrastructure on the Ethereum blockchain |
| **MKR** | A cryptocurrency that insures the collateralization of the Dai |
| **SDR** | Special Drawing Right, a currency basket maintained by the International Monetary Fund |



##Value proposition

**Dai issuers use the Dai** to borrow money instantly and without any requirements beyond posting adequate collateral. There are no term limits, and debt positions can opened and covered at any time. This means the Dai can service any kind of credit demand, including margin trading, business credit and mortgage financing.

**Dai holders use the Dai** as a stable cryptocurrency on the Ethereum blockchain, and as a low risk investment asset that is free from volatility risk and is long term deflationary. The Dai has low risk relative to most blockchain assets because every Dai is provably backed by a diversified pool of collateral on the Ethereum blockchain, as well as by Makers insurance.

**MKR owners gain value from the Dai** because MKR represents the ownership of Makers insurance service. Dai issuers an insurance fee on the Dai, and Maker steadily funnels this income to MKR owners by buying and permanently destroying MKR supply, thus, decreasing the supply and increasing market price. In return Maker is forced to bail out bad debt in the event of a sudden collateral crash (a so-called a black swan event). If Maker does not have enough assets on hand to immediately cover all bad debt, the MKR supply is automatically inflated and sold off to raise funds in order to cover all the bad debt over time. As a result Makercoin owners are exposed to both the profits and the risk of Makers insurance service.

##Note on oracles, governance and roadmap

This document describes only the economic mechanisms of the fully implemented Dai Credit System. The Maker Prospectus (will be released soon) contains information about crucial supporting features such as the price feed oracles that deliver data to the blockchain, the governance scheme of the Maker DAO, as well as the current planned long term design roadmap for Maker from deployment to widespread adoption.

##How it works
###Issuance and supply

The Dai is a cryptocurrency on the Ethereum blockchain. Any Ethereum account can hold Dai, and can transfer it freely to other Ethereum accounts.

When the Dai Credit System is initially deployed in early 2016, the value of the Dai will be pegged to a **target price** of 0.73 Special Drawing Rights (SDR). The SDR is an international currency basket maintained by the International Monetary Fund (IMF). Over time the target price will increase, resulting in long term deflation.

The supply of Dai tokens is controlled through a decentralized issuance scheme that allows anyone to issue new Dai, while ensuring the Dai price remains stable around the target price. Issuing new Dai is done by locking collateral in a **collateralized debt position** (CDP) smart contract. A CDP holds **issuance collateral** as well as **issuance debt**. At the time when new Dai is issued, the issuance debt is set equal to the amount of newly issued Dai, but increases over time as the CDP accrues an **insurance fee**. The collateral can be retrieved by the issuer paying down (“covering”) the issuance debt, plus the additional insurance fee, which is paid to the Maker Vault. Paying down the issuance debt and insurance fee returns the collateral to the issuer and deletes the CDP.

>*__Example 1__: An issuer wishes to issue 100 Dai, and locks Bitcoin with a market value of significantly more than 100 Dai (“excess collateral”) into a CDP. The insurance rate is 2% over the following year. When the issuer wants to retrieve his Bitcoin, 102 Dai are required to cover the CDP.*

The Dai deflation means that the market value of the issuance debt will also have increased over time in terms of SDR, and issuers will need to take the deflation into consideration in addition to the insurance fee as the total effective cost of issuing the Dai. The deflation is a transfer of value from the issuer to the Dai holders (as payment for borrowing capital), and the insurance fee is a transfer of value from the issuer to Maker (as payment for insuring the collateral).

>*__Example 2__: An issuer issues 100 SDR worth of Dai (note: this is not 100 Dai) by locking 150 SDR worth of Bitcoin into a CDP. The total effective cost of insurance and deflation over the following year is 5% relative to SDR. When the issuer wants to retrieve his Bitcoin, 105 SDR worth of Dai is required to cover the CDP.*

Issuing Dai can be considered as borrowing capital from the Dai Credit System. In practice the issuer is either seeking to take a leveraged long position on the asset used as collateral (margin trading), or is seeking liquidity in a hard currency (such as BTC or USD) without selling the asset used as collateral. The last example could be the case of a business collateralizing stock in order to raise short term liquidity for operational expenses. In both cases the way the issuer actually obtains the asset that he wants is by first creating the CDP with their collateral and issuing Dai, then selling the newly issued Dai on the market in exchange for their desired asset or currency. Dai holders that pay assets and currency in exchange for Dai do this in order to earn capital gains from the Dai deflation and/or use it as a stable cryptocurrency on the Ethereum blockchain. 

>*__Example 3__: An issuer issues 100 SDR worth of Dai by posting 150 SDR worth of BTC to a CDP, and buys another 100 SDR worth of BTC with the newly issued Dai. This gives him a 1.66x exposure to BTC/SDR volatility, and he can freely transfer the 100 SDR worth of BTC, while the 150 SDR worth of BTC held in the CDP as collateral is locked until the 100 issuance debt plus insurance fee is covered.*

The ownership of a CDP is transferable, but CDPs are not fungible with each other. This allows them to be used in smart contracts that can perform more complex methods of issuance involving more than one actor.

>*__Example 4__: An issuer uses an Over The Counter (OTC) Ethereum contract to issue a 100 SDR worth of Dai together with a counterparty that wishes to become a Dai holder. The issuer contributes 50 SDR worth of BTC while the holder contributes 100 SDR worth of BTC. The OTC contract creates a CDP and issues 100 SDR worth of Dai, and then gives the holder this newly issued Dai. The holder effectively bought 100 SDR worth Dai for 100 SDR worth of BTC. The OTC contract gives the issuer ownership of the CDP, including its 100 SDR worth of issuance debt as well as its 150 SDR worth of BTC collateral. Since he started with only 50 SDR worth of BTC he is now 3x leveraged.*
###Price stability

The stability of the Dai around the target price is maintained using **deflation rate adjustment** to continuously match demand between holders and issuers, while **forced cover** is the mechanism that enforces the target price with the collateral from the CDPs, as well as ensuring short term liquidity and price support in the face of demand shocks for the Dai.

####Long term price stability

Deflation rate adjustments ensure that the Dai market price remains stabilized around the target price.

When the market price is below the target price, the deflation rate increases. This causes issuance to be more expensive, decreasing demand for issuance, and thus reducing Dai supply. At the same time the capital gains from holding Dai go up as the deflation rate increases, and this increases Dai holding demand. The decreased supply and increased demand will cause the market price to increase, pushing it up towards the target price.

The same mechanism works in reverse if the market price is higher than the target price. The deflation rate decreases, increasing demand for issuance and thus increasing Dai supply, while decreasing demand for holding Dai (less capital gains from deflation), causing the Dai price to decrease, pushing it down towards the target price.

This mechanism can be considered a negative feedback loop. Any deviation from the target price by the market price will trigger a mechanism that pushes the market price back towards the target price. The magnitude of the deflation rate adjustments depend on how strongly the market price deviates from the target price; very strong deviations result in bigger adjustments whereas small deviations result in very small adjustments. 

####Short term liquidity and price support

To counteract demand shocks, a secondary stability mechanism exists: **forced cover**.

Every Dai in existence is always backed by excess collateral during normal market conditions. This collateral is locked in collateralized debt positions, and the collateralization ratio (how much debt to collateral the CDP has) can be verified cryptographically on the Ethereum blockchain.

A Dai token represents an insured claim to the collateral contained in the CDP portfolio, and can enforce this claim through the forced cover mechanism. A forced cover works by having the Dai holder pay down the debt on behalf of the CDP issuer, and in return buying a portion of the of the CDPs collateral. The amount of collateral that the forced cover buys, is determined relative to a price feed. The leftover collateral that isn’t bought gets returned to the issuer, and the CDP is deleted.

The cost of doing a forced cover on a properly collateralized CDP comes in the form of a negative **bounty**, which means the Dai holder has to pay a higher price per unit of collateral relative to the target price (note: not the market price).

The bounty varies based on the collateralization of the CDP subject to the forced cover, with better collateralized CDPs having a lower/more negative bounty. All CDPs have a **collateral curve**, which is a function that determines the bounty based on the collateralization of the CDP. This collateral curve is defined based on the **zero point**, the collateralization percentage at which the bounty is 0%. The zero point is different for each collateral type, and is based on their tendency to be volatile (riskier asset classes will have higher zero points).

The slope of the collateral curve is initially simplified to always be approximately 1, so a 1% movement in collateralization in a direction produces a corresponding 1% change in the bounty.

>*__Example 5__: Bitcoin has a zero point of 130%. A CDP is created with 135% collateralization. At this level of collateralization, the CDP has a bounty of -5%, and performing a forced cover that costs 100 SDR worth of Dai will only buy 95 SDR worth of Bitcoin, giving a 5% loss (assuming that the market price of Dai is equal to the target price when the forced cover happens).*

If the collateralization ratio of a CDP goes below the zero point, the bounty for performing a forced cover on the CDP becomes positive. At this point the forced cover is also referred to as a margin call, as it has a similar function of closing out positions that are too risky. The positive bounty will generally cause market forces to instantly margin call the CDP in order to earn the free profit from buying a larger portion of the CDPs collateral at the same price.

>*__Example 6__: An issuer creates a CDP with 130 SDR worth of Bitcoin as collateral, and uses it to issue 100 SDR worth of Dai. The price of Bitcoin subsequently falls 10%, leaving the CDP at 117% collateralization. The bounty is now +13%, and a Dai holder quickly margin calls it, paying down the 100 SDR debt, but obtaining 113 SDR worth of Bitcoin, with only 4 SDR worth of Bitcoin remaining for the issuer.*
 
The purpose of the forced cover is to provide a buffer of liquid assets from the CDPs in case the price of Dai suddenly drops dramatically due to a shock in demand. This is because a CDPs bounty is determined in terms of the Dai target price, and the **effective bounty** changes in response to the market price, changing with the same magnitude but in the opposite direction of a deviation of the market price from the target price. This creates another negative feedback loop that serves to push the market price towards the target price.

>*__Example 7__: Consider the scenario where there are active Bitcoin CDPs at 135% collateralization and a large Dai selloff suddenly occurs. If the Dai market price deviates more than 5% below the target price, the effective bounty of all CDPs will increase correspondingly. Thus a CDP with 135% or lower collateralization which have a nominal bounty of -5%, will see their effective bounty hit 0% or higher, causing them to be margin called by profit seeking traders. This causes the supply of Dai to decrease and creates positive pressure on the Dai market price, pushing it upwards.*

The mechanism of forced covers and the collateral curve has a different effect on the market price when the market price deviates above the target price. The zero point of a collateral type is also the minimum initial collateralization requirement for issuing new Dai, but like the bounty, this collateralization requirement is given in the target price. Thus, when the market price increases, the effective collateral requirement for issuing Dai go down, which in turn increases demand for issuance, increasing supply of Dai, which pushes the price down in the direction of the target price.

###Undercollateralization 

The biggest risk to the stable value of the Dai, is the risk of CDP undercollateralization.
Should a Collateralized Debt Position see a massive price decrease in its collateral to the point where its collateralization ratio falls below 100%, there would no longer be enough collateral in the position to buy back all the Dai it originally issued (plus insurance fee). If such undercollateralization events were left unchecked and allowed to happen to a significant amount of the outstanding CDPs, it could destroy confidence in the Dai and break its stability. Widespread, sudden undercollateralization that happens too fast to be mitigated by margin calls is also referred to as a **black swan event**.

To ensure the stability of the Dai under all circumstances, Maker provides the service of Maker Insurance, which shields the Dai Credit System from the losses of black swan events by transferring the loss to MKR holders, through two mechanisms: **Maker bailout** and **Forced MKR inflation**.

**Maker bailout**: Despite the massive profit incentive for traders to perform margin calls once the collateralization of a position falls just a few percentage points below its zero point (giving it a positive bounty), there is still a risk of one or more CDPs becoming undercollateralized. Once a CDP becomes undercollateralized and has less collateral than it has debt, there is no longer a profit incentive for traders to margin call it.

Instead, Maker will autonomously perform a Maker bailout, using funds from the Maker vault, (Makers Dai account). The Maker vault receives the insurance fees paid out from CDP when they are covered and thus always has a pool of funds readily available to perform Maker bailouts.

Should many CDPs become simultaneously undercollateralized to the point where there isn’t enough Dai in the Maker vault to bail them out, Maker automatically issues Dai backed by emergency debt. Emergency debt doesn’t require external collateral but is backed by the ability of Maker to inflate the MKR supply, there is also no limit to the amount of emergency debt that can be issued, and it will always correspond to the combined debt of CDPs that became undercollateralized.

**Forced MKR inflation**: Once Maker assumes emergency debt, forced MKR inflation gets triggered. The inflation is continuous at a rate that corresponds to a 100% increase of the MKR per year. The inflated MKR is automatically sold off for Dai, that is then used to pay down and remove the emergency debt. The forced inflation continues until all emergency debt is paid down and the system returns to normal.
    
**The function of MKR**:  Ultimately it is the market value of MKR that insures the collateral of the Dai Credit System, and the price of MKR is directly exposed to the risk of the system. To compensate MKR owners for taking on this risk, during times of stability where there is no outstanding emergency debt, the Dai held in the Maker Vault is slowly sold off for MKR, and the obtained MKR is then permanently destroyed, in an autonomous mechanism known as buy & burn. The rate at which the buy & burn happens is determined by MKR holders through voting. The result is that, in the absence of undercollateralization events, the supply of MKR is decreasing over time, which causes its price to increase.

###Collateral requirements and debt ceilings

There are two primary factors that determine the risk of a given collateral type: Market depth and volatility. While these two factors are related - more market depth means less volatility - they still contribute separately to the overall risk and are thus each managed with a separate mechanisms.

####Market depth risk

The impact of market depth on the risk of a collateral type is managed through the **debt ceiling**. In short, the debt ceiling is the maximum amount of issuance debt that can be held in CDPs that use the same type of collateral. Once the debt ceiling for a collateral type has been reached, no more Dai can be issued using the asset as collateral, until existing CDPs using the asset are covered. New Dai can still be issued using a different asset as collateral.

####Volatility risk

Volatility of the various collateral types is managed through the collateral curve, which is defined by the zero point. The zero point is set so there is a sufficient buffer of collateralization at which CDPs using the collateral will have a positive bounty and thus get margin called, in order for them to withstand the highest volatility observed for the asset under normal conditions. This means more volatile assets will have higher zero points, allowing for less leverage by issuers, and less volatile assets will have lower zero points, allowing for more leverage.
