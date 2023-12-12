---
title: "Rescan"
parent: Advanced Features
---

# Rescan

{: .warning}
Rescanning will remove any saved transaction keys and destination addresses, which may be useful for proving payments.

If your XMR transaction is still not appearing and the sync state of the wallet is `SYNCHRONIZED`, then you can rescan by opening the menu in the top-right, tapping `Connection and sync`, then tapping `Rescan`.

## To rescan your wallet

[![Click hamburger menu](/images/rescan-1.jpg){:width="32%"}](/images/rescan-1.jpg)
[![Click Connection and sync](/images/rescan-2.png){:width="31.1%"}](/images/rescan-2.jpg)
[![Click rescan](/images/rescan-2.1.png){:width="31.1%"}](/images/rescan-2.jpg)
[![Add restore height](/images/rescan-3.jpg){:width="32%"}](/images/rescan-3.jpg)
[![Wait for wallet to sync](/images/rescan-4.jpg){:width="32%"}](/images/rescan-4.jpg)
[![Wallet synchronized](/images/rescan-5.jpg){:width="32%"}](/images/rescan-5.jpg) 

Enter a date or a block height from about a week before you created this wallet. So, if it was created in February 2020 sometime, you could use January 31st, 2020 as the 'restore from date.' Alternatively, you can look at your wallet's very first transaction, and it will tell you the "Height" it was included in. You can enter this very same number as your "Block height" when you Rescan, and it will work perfectly.

After entering the date and tapping Rescan, you need to leave the Cake Wallet app open with your phone awake while the wallet rescans the blocks for transactions involving your wallet. When the rescan starts, your transaction history will disappear and your balance will read as 0.0 XMR. As the wallet continues scanning new blocks, you will begin seeing your transaction history appearing - one transaction at a time. When the Rescan is completed, you will see a `SYNCHRONIZED` label at the top of the balance screen and your entire transaction history, as well as the proper balance.
