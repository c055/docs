To be included in the Maker Prospectus

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
