ION Core version *3.1.0* is now available from:  <https://github.com/ioncoincore/ion/releases>

This is a new major version release, including various bug fixes and performance improvements, as well as updated translations.

Please report bugs using the issue tracker at github: <https://github.com/ioncoincore/ion/issues>


Mandatory Update
==============

ION Core v3.1.0 is a mandatory update for all users. This release contains new consensus rules and improvements that are not backwards compatible with older versions. Users will have a grace period of one week to update their clients before enforcement of this update is enabled. 

The new Spork Key implementation is scheduled for Thursday, GMT: Monday, 31. December 2018 00:00:01.  
The old Spork key will be rejected Wednesday, GMT: Sunday, 6. January 2019 00:00:01. Users must upgrade prior to this time.

Users updating from a previous version after Sunday, 6. January 2019 00:00:01 will require a full resync of their local blockchain from either the P2P network or by way of bootstrap.

How to Upgrade
==============

Shut down old client, ensure the shutdown process has completed fully (this process may take some time). Find the appropriate installer/files for your OS at: https://github.com/ioncoincore/ion/releases On Windows: Run the installer for version 3.1.x. MacOS: Copy the new ionQT to /Applications/ION-Qt Linux: Replace iond/ion-qt (on Linux).


Compatibility
==============

ION Core is extensively tested on multiple operating systems using
the Linux kernel, macOS 10.8+, and Windows Vista and later.

Microsoft ended support for Windows XP on [April 8th, 2014](https://www.microsoft.com/en-us/WindowsForBusiness/end-of-xp-support),
No attempt is made to prevent installing or running the software on Windows XP, you
can still do so at your own risk but be aware that there are known instabilities and issues.
Please do not report issues about Windows XP to the issue tracker.

ION Core should also work on most other Unix-like systems but is not
frequently tested on them.

### :exclamation::exclamation::exclamation: MacOS 10.13 High Sierra :exclamation::exclamation::exclamation:

**Currently there are issues with the 3.x gitian release on MacOS version 10.13 (High Sierra), no reports of issues on older versions of MacOS.**

 
Notable Changes
==============

IIP  0003 implementation  
--------
The updated block reward schedule has been implemented as per IIP 0003
https://github.com/ionomy/iips/blob/master/IIP_0003.md

- **Year 3** - Block reward - 11.5   
- **Year 4-9** - Block reward - 5.75      
- **Year 10** - Block reward - 1.90  
- **Year 11-100** - Block reward - 0.2  

Old ion implementation refactored
--------------

Previous implementation of ION-based code has been refactored. Sources are now inline with [latest PIVX](https://github.com/PIVX-Project/PIVX/tree/4b1be14505ded427378f267d9c31a3a0f72bda75) as of release time.

Windows masternode.conf bug
--------------

Windows Masternode Controller wallets were experiencing an issue reading the `masternode.conf` file during startup that prevented the wallet from opening properly. 

Windows file icons
-------------

The Windows program icons and installer images were of less than ideal quality, often appearing grainy or distorted. These icons/images have been replaced with higher resolution images.

Updated artworks
-------------

CSS, artworks and their sources have been updated/renewed


Updated translations, you can follow the status [on Transifex](https://www.transifex.com/cevap/ioncoin/)
-------------
Transifex is a web-based translation platform that assists with translation of open source technical projects with frequently updated content like software and documentation. Users can now contribute to localization of ion through Transifex at: https://www.transifex.com/cevap/ioncoin/

Initiated transition to bech32 address encoding  
-------------


Fix checklocktimeverify unit tests   
-------------


New issue templates  
----

To assist with better support, templates for various github issues are now available
https://github.com/ioncoincore/ion/issues/new/choose


xION Updates
--------------

### xION Staking

xION Staking is here! xION staking will be activated on the morning of the Sunday, 6. January 2019 00:00:01.  
With the release of xION staking, there are effectively 2 versions of xION, xION minted on the 3.0.6 ION wallet or lower, and xION minted on ION 3.1.x wallet version or higher.  
New features in this release will require the use of xION v2, xION minted on this wallet release 3.1.x or later. If you currently hold xION v1 and wish to take advantage of xION staking and deterministic xION, you will need to redeem the xION v1 to yourself and remint xION v2. 
Note: To find your xION version, click the privacy tab, then the xION Control button then expand the arrows next to the desired denomination.


### Deterministic xION Seed Keys

xION is now associated with a deterministic seed key. With this seed key, users are able to securely backup their xION, and restore to another wallet. xION can also be transferred from wallet to wallet without the need of transferring the wallet data file.


### Updated xION minting

xION minting now only requires 1 additional mint (down from 2) to mature. xION mints still require 20 confirmations.  Mints also require that the 'second' mint is at least two checkpoints deep in the chain (this was already the case, but the logic was not as precise).


### xION Search

Users will now have the ability to search the blockchain for a specific serial # to see if a xION denomination has been spent or not.


ION/xION Staking and Masternode Rewards
--------------

### ION, xION and Masternode Payment Schedule

To encourage the use of xION and increase the ION zerocoin anonymity set, the ION payment schedule has been changed to the following:

If a user staking xION wins the reward for their block, the following xION reward will be: 
- 5 xION (5 x 1 denominations) rewarded to the staker and 6.5 ION rewarded to the masternode owner for a total reward of 11.5

If a user staking ION wins the reward, the following amounts will be rewarded: 
- 5.75 ION to the ION staker and 5.75 ION to the Masternode owner for a total of 11.5

xion staking and masternode reward schedule
-------
- **Year 3** - Block reward - 11.5 (5 xion to Staker / 6.5 ion to Masternode)  
- **Year 4-9** - Block reward - 5.75 (2 xion to Staker/ 3.75 ion to Masternode)    
- **Year 10** - Block reward - 1.90 (.9 xion to Staker / 1 ion to Masternode)     

ion staking and masternode reward schedule  
------
- **Year 3** - Block reward - 11.5 (5.75 to Staker / 5.75 to Masternode)    
- **Year 4-9** - Block reward - 5.75 (2.875 Staker/2.875 to Masternode)  
- **Year 10** - Block reward - 1.90 (.95 to Staker / .95 to Masternode)  

### Return change to sender when minting xION

Previously, xION minting would send any change to a newly generated "change address". This has caused confusion among some users and in some cases loss due to insufficient backups of the wallet. The wallet will now find the contributing address which contained the most ION and return the change from a xION mint to that address.


User Experience
--------------

### Graphical User Interface

The visual layout of the ION Qt wallet has undergone a near-complete overhaul.
A new 'vertical tab' layout is now being used instead of the prior 'horizontal tab' layout, as well as a completely new icon set.
The overview tab has been simplified greatly now displaying only the balances that are active or relevant. Zero-balance line items are hidden by default.


### Wallet Options

There have been a number of changes to the tasks that may be performed from the wallet options. Users will now have the ability to do the following: 
-	Enable and disable the auto xION minting feature. This is enabled by default and the enablezeromint=0 setting in the ion.conf file will overwrite the GUI option.
-	The percentage of autominted xION can now be set from 1 to 100, changed from 10 – 100.
-	The stake split threshold can now be set VIA the wallet options. This setting is an advanced feature for those wishing to continue staking regularly.
-	“Unlock for staking and anonymization only” is now selected by default when unlocking the wallet from the User Interface


### In-wallet Ban Management

Peer bans are now manageable through the Peers tab of the tools window. Peers can be banned/unbanned at will, without the need to restart the wallet client. No changes have been made to the conditions resulting in automatic peer bans.


Backup to external devices / locations
--------------

### Summary

 The ION wallet can now have user selected directories for automatic backups of the wallet data file (wallet.dat). This can be set by adding the following lines to the ion.conf file, found in the ION data directory.
- backuppath = <directory / full path>
- xionbackuppath = <directory / full path>
- custombackupthreshold = <backup limit>
Note: System write permissions must be appropriate for the location the wallet is being saved to.

* Configured variables display in the _Wallet Repair_ tab inside the _Tools Window / Dropdown Menu_
* Allows for backing up wallet.dat to the user set path, simultaneous to other backups
* Allows backing up to directories and files, with a limit (_threshold_) on how many files can be saved in the directory before it begins overwriting the oldest wallet file copy.


### Details:

* If path is set to directory, the backup will be named `wallet.dat-<year>-<month>-<day>-<hour>-<minute>-<second>`
* If xION backup, auto generated name is `wallet-autoxionbackup.dat-<year>-<month>-<day>-<hour>-<minute>-<second>`
* If path set to file, backup will be named `<filename>.dat`
* walletbackupthreshold enables the user to select the maximum count of backup files to be written before overwriting existing backups.


### Example:

* -backuppath=/\<mynewdir>/        
* -walletbackupthreshold=2

Backing up 4 times will result as shown below


                date/time
    backup #1 - 2018-04-20-00-04-00  
    backup #2 - 2018-04-21-04-20-00  
    backup #3 - 2018-04-22-00-20-04  
    backup #4 - 2018-04-23-20-04-00  
    
    1.
        /<mynewdir>/
            wallet.dat-2018-04-20-00-04-00
    2.
        /<mynewdir>/
            wallet.dat-2018-04-20-00-04-00
            wallet.dat-2018-04-21-04-20-00
    3.
        /<mynewdir>/
            wallet.dat-2018-04-22-00-20-04
            wallet.dat-2018-04-21-04-20-00
    4.
        /<mynewdir>/
            wallet.dat-2018-04-22-00-20-04
            wallet.dat-2018-04-23-20-04-00
            
### ION QT

### New certificates > 

### Gitian 

Signature location (For verification) https://github.com/gitianuser/gitian.sigs-ion
Build, release and translation process - started w/pivx core imported bitcoin core components. 
switch from trusty to ubuntu bionic for the build system 

### Snap Builds

### Translations
Transfinex encourage people to use https://www.transifex.com/ioncoincore/ioncore/

### New Repositore
ioncoincore - main official repository for community coin development will be updated more often
ionomy - corporate releases (stable)






ION Daemon & Client (RPC Changes)
--------------

### RPC Ban Management

The ION client peer bans now have additional RPC commands to manage peers. Peers can be banned and unbanned at will without the need to restart the wallet client. No changes have been made to the conditions resulting in automatic peer bans. New RPC commands: `setban`, `listbanned`, `clearbanned`, and `disconnectnode`


### Random-cookie RPC authentication

When no `-rpcpassword` is specified, the daemon now uses a special 'cookie' file for authentication. This file is generated with random content when the daemon starts, and deleted when it exits. Its contents are used as an authentication token. Read access to this file controls access through RPC. By default it is stored in the data directory, however its location can be overridden with the option `-rpccookiefile`.
This is similar to Tor's CookieAuthentication: see https://www.torproject.org/docs/tor-manual.html.en 
This allows running iond without having to do any manual configuration.


### New RPC command
`getfeeinfo`

This allows a user (such as a third party integration) to query the blockchain for the current fee rate per kb and also get a suggested rate per kb for high priority transactions.


### New RPC command 
`findserial`

Search the zerocoin database for a zerocoinspend transaction that contains the given serial. This will be a helpful tool for Users and the ION support group, which often times see confusion around xION. This RPC call allows for users and support to use the serial to find the spend transaction on the blockchain.


### New RPC commands 
`createmasternodebroadcast`

`decodemasternodebroadcast`

`relaymasternodebroadcast`

A new set of rpc commands masternodebroadcast to create masternode broadcast messages offline and relay them from online node later (messages expire in ~1 hour).

### New RPC command
`getextendedbalance`

extened overview of current balance

### New RPC command
`listtransactionrecords`

varation of listtransaction prints transaction overview similar to qt output

### New RPC command
`listrecordssinceblock`

### New RPC command
`fundtransaction`
A tool for manually creating raw transactions

### 


Network Layer 2 Changes (Proposals / Budgets / SwiftX)
--------------

### Monthly Budget Increase

As voted on by the ION masternodes, the monthly budget available to be utilised has been increased to 42,000 ION / month. This ION only has the opportunity to be raised once per month (paid to winning proposals) with any unused ION not created by the blockchain.

### Budget Finalization Fee

The ION finalization fee for successful proposals has now been reduced, this fee is now 5 ION down from 50 ION. The total fee outlay for a successful proposal is now a total of 55 ION.


### SwiftX Raw Transactions

 When creating a raw transaction, it is now possible to create the transaction as a SwiftX transaction. See the updated help documentation for the `createrawtransaction` RPC command.

Technical Changes
--------------

### Migration to libevent based http server

The RPC and REST interfaces are now initialized and controlled using standard libevent instead of the ad-hoc pseudo httpd interface that was used previously. This change introduces a more resource friendly and effective interface.


### New Notification Path 
`blocksizenotify`

A new notification path has been added to allow a script to be executed when receiving blocks larger than the 1MB legacy size. This functions similar to the other notification listeners (`blocknotify`, `walletnotify`, etc).


### Removed Growl Support

Growl hasn't been free nor needed for many years. MacOS versions since 10.8 have the OS notification center, which is still supported after this.


### Autocombine changes

The autocombine feature was carrying a bug leading to a significant CPU overhead when being used. The function is now called only once initial blockchain download is finished. It is also now avoiding combining several times while under the threshold in order to avoid additional transaction fees. Finally, the fee computation has been changed and the dust from fee provisioning is returned in the main output.


### SOCKS5 Proxy bug

When inputting wrong data into the GUI for a SOCKS5 proxy, the wallet would crash and be unable to restart without accessing hidden configuration. This crash has been fixed.

Minor Enhancements
--------------

-	Enforced v1 xION spends to require a security level of 100
-	Updates to xION spends to avoid segfaults
-	Updates to configuration will now reflect on the privacy tab
-	Fixed a  bug that would not start masternodes from the ION-Qt masternodes tab
-	Updated ION-Qt tooltips
-	Icon added to the wallet GUI to reflect the status of autominting (active / inactive)
-	Updated errors causing the blockchain to corrupt when experiencing unexpected wallet shutdowns
-	Updated RPC help outputs & removed the deprecated obfuscation. 
-	Refactored code
-	Various bug fixes
-	Updated documentation

Further Reading: Version 2 Zerocoins
==============

Several critical security flaws in the zerocoin protocol and ION 's zerocoin implementation have been patched. Enough has changed that new zerocoins are distinct from old zerocoins, and have been labelled as *version 2*. When using the xION Control dialog in the QT wallet, a user is able to see xION marked as version 1 or 2.

xPoS (xION staking)
--------------

Once a xION has over 200 confirmations it becomes available to stake. Staking xION will consume the exact zerocoin that is staked and replace it with a freshly minted zerocoin of the same denomination as well as a reward of three 1 denomination xION. So for example if a 1,000 xION denomination is staked, the protocol replaces that with a fresh 1,000 denomination and three1 denomination xIONs.

Secure Spending
--------------

Version 1 zerocoins, as implemented by [Miers et. al](http://zerocoin.org/media/pdf/ZerocoinOakland.pdf), allow for something we describe as *serial trolling*. Spending zerocoins requires that the spender reveal their serial number associated with the zerocoin, and in turn that serial number is used to check for double spending. There is a fringe situation (which is very unlikely to happen within ION 's zerocoin implementation due to delayed coin accumulation) where the spender sends the spending transaction, but the transaction does not immediately make it into the blockchain and remains in the mempool for a long enough duration that a malicious actor has enough time to see the spender's serial number, mint a new zerocoin with the same serial number, and spend the new zerocoin before the original spender's transaction becomes confirmed. If the timing of this fringe situation worked, then the original spender's coin would be seen as invalid because the troll was able to have the serial recorded into the blockchain first, thus making the original spender's serial appear as a double spend.

The serial troll situation is mitigated in version 2 by requiring that the serial number be a hash of a public key. The spend requires an additional signature signed by the private key associated with the public key hash matching the serial number. This work around was conceived by Tim Ruffing, a cryptographer that has studied the zerocoin protocol and done consulting work for the ZCoin project.

Deterministic Zerocoin Generation
--------------

Zerocoins, or xION, are now deterministically generated using a unique 256 bit seed. Each wallet will generate a new seed on its first run. The deterministic seed is used to generate a string of xION that can be recalculated at any time using the seed. Deterministic xION allows for users to backup all of their future xION by simply recording their seed and keeping it in a safe place (similar to backing up a private key for ION). The xION seed needs to remain in the wallet in order to spend the xION after it is generated, if the seed is changed then the coins will not be spendable because the wallet will not have the ability to regenerate all of the private xION data from the seed. It is important that users record & backup their seed after their first run of the wallet. If the wallet is locked during the first run, then the seed will be generated the first time the wallet is unlocked.

Zerocoin Modulus
--------------

ION 's zerocoin implementation used the same code from the ZCoin project to import the modulus use for the zerocoin protocol. The chosen modulus is the 2048 bit RSA number created for the RSA factoring challenge. The ZCoin project's implementation (which ION used) improperly imported the modulus into the code. This flaw was discovered by user GOAT from the [Civitas Project](https://github.com/eastcoastcrypto/Civitas/), and reported to ION using the bug bounty program. The modulus is now correctly imported and ION 's accumulators have been changed to use the new proper modulus.

*3.1.0* Change log
--------------

Detailed change notes follow. This overview includes changes and commits, and then the underlying commits that were created after.

- `35f4f5b` Remove the old trading dialog code (Mitchell Cash)
- `48fe3e4` [gitian] Move keys to contrib/gitian-keys (Mitchell Cash)
- `ccc26e5` Cleanup the old CEVAP references in README (Mitchell Cash)
- `d715ee6` Build: Fix macOS signing (Mitchell Cash)
- `209f82f` Add extended balance RPC call (Fornax)
- `86c3885` snapcraft: update to development branch v3.1.1 (cevap)
- `2b4c91a` Snapcraft: replace libssl (cevap)
- `8ea6d33` Big update (3.0.2-3.1.01) (cevap)
- `846dfdc` Snapcraft: readd prepare insted of override-build (cevap)
- `0544c84` fix: folder paths in util.cpp (cevap)
- `a638373` Fix typo in chainparams.cpp (cevap)
- `533a9d8` Fix typo in snapcraft.yaml (cevap)
- `993883f` Remove unrequired snapcraft files (cevap)
- `9c7f9f2` Snapcraft: add part after: desktop-qt5 (cevap)
- `25de2da` Snapcraft: trigger stable build for version 3.0.4 (cevap)
- `1d3b6af` Fix tag version (cevap)
- `8e9f88a` Snapcraft: trigger stable build for version 3.0.5 (cevap)
- `11d96a4` Snapcraft: trigger stable build for version v3.1.01 (cevap)
- `4949c75` Snapcraft: add build-packages (cevap)
- `a7481d8` Snapcraft: use default architectures [all] (cevap)
- `9eb4aeb` Update xion rewards (cevap)
- `9acbd23` Add accumulator checkpoints (cevap)
- `679c5ea` Change help adddresses (cevap)
- `59eb465` Add checkpoints (cevap)
- `89da505` Change urls for osslsigncode (cevap)
- `0e2fde2` Update coin supply amount (FornaxA)
- `9ad8974` Update README.md (cevap)
- `4dc1fa2` Remove old image Sagittarius.jpg (cevap)
- `92950b9` Update README.md (cevap)
- `541cf9e` Update snapcraft.yaml (cevap)
- `a3e796b` Change enforce spork timestamp (cevap)
- `ac2d402` Update devtools (cevap)
- `ccbab92` Update devtools readme (cevap)
- `9b8e6e5` Miner: use std methods instead of boost for timing conditions (Fuzzbawls)
- `728e69c` Remove Boost dependency from the httpserver (Fuzzbawls)
- `2b24742` Ust std threading in sync.{h,cpp} (Fuzzbawls)
- `e441c23` Update QT locales (cevap)
- `166c54e` Add python script for gitian builds (cevap)
- `795d622` Add install script for db4 (cevap)
- `ebcd334` Update zerocoin v2 startheight (cevap)
- `5396326` Zerocoin maintenance mode switched on (cevap)
- `617b248` Bump versino to 3.1.00 (cevap)
- `c67bf54` Snapcraft: add ion-tx (cevap)
- `6430b7b` Update checkpoints (main (cevap)
- `8225d46` Add last v1 accumulator checkpoint (cevap)
- `ceb6da0` Disable zerocoin maintenance mode (cevap)
- `ba74a01` Artworks update: automint icon (cevap)
- `48b47ef` Artworks update: bittrex logo (cevap)
- `13a9376` Artworks update: about.png (cevap)
- `40a9cec` Artworks update: remove warning (cevap)
- `2b9d163` Artworks update: tx_mined.png (cevap)
- `f9870d7` Artworks update: horizontal logo (cevap)
- `cd571dc` Artworks update: ion-black.svg (cevap)
- `7027429` Artworks update: about sources (cevap)
- `1c59446` Artworks update: default css (cevap)
- `0e65933` Transifex: update urls (cevap)
- `ee02191` Ported CLTV from BIP65 to ION. Added checks for supermajority activation. (Benjamin Allred)
- `65cde52` Update changes for CLTV (presstab)
- `7b4b7ea` Fix checklocktime verify unit tests (blondfrogs)
- `0b56540` Update zerocoin v2 start to after Jan. 06 (cevap)
- `041f7ce` Update checkpoints (cevap)
- `7d2a779` Add action to hide orphans in overview and txlist (random-zebra)
- `f674a63` Add CLTV activation version (cevap)
- `1173a21` 7 day CLTV activation (presstab)
- `915d428` Show BIP65 soft-fork progress in getblockchaininfo (Fuzzbawls)
- `b389e9a` Fix xION spend when too much mints are selected (warrows)
- `6ab8e6e` Unify shutdown proceedure in init rather than per-app (Fuzzbawls)
- `29149a9` Do not record zerocoin tx's in ConnectBlock() if it is fJustCheck (presstab)
- `830f04a` Remove Boost dependency from sync.cpp (Fuzzbawls)
- `65034b0` Initialize lockstack to prevent null pointer deref (Fuzzbawls)
- `7bdeb00` Remove unused fTry from push_lock (Fuzzbawls)
- `c968200` Use c++11 nullptr instead of macros or void(0) in sync.cpp/h (Fuzzbawls)
- `af3b3ce` Finalize cleanup of sync.cpp/h (Fuzzbawls)
- `3942766` Add a security warning to the debug console's default output. (Fuzzbawls)
- `e02826b` Add release notes (cevap)
- `02b25e1` Merged CHECKSEQUENCEVERIFY from https://github.com/phoreproject/Phore/commit/de7acaba10fb4eeb196165521c6dc2a5c256b2e5 (wqking)
- `3b30fd0` IONCORE-47 Introduction of wrappers (FornaxA)
- `f8ee3a8` IONCORE-48 First batch of removing intermediary functionality (FornaxA)
- `07aa760` Consensus: Refactor: Decouple CValidationState from main::AbortNode() (FornaxA)
- `508fbf1` Add debug message to CValidationState for optional extra information (FornaxA)
- `3a45ecc` Add memusage.h and core_memusage.h (FornaxA)
- `cf804ff` Introduce Coin, a single unspent output (FornaxA)
- `bbafd77` IONCORE-47 Introduce wrappers for Coin and AccessCoin() (FornaxA)
- `7f87033` Import Bech32 C++ reference code & tests (FornaxA)
- `f0d2206` IONCORE-52 Implement {Encode,Decode}Destination without CBitcoinAddress (FornaxA)
- `dbddc7b` Second batch of removing intermediary functionality (FornaxA)
- `e834f27` Remove CBitcoinAddress (FornaxA)
- `442bbaf` IONCORE-66 Subtract fee from the amount (FornaxA)
- `354a80c` IONCORE-66 Add FundTransaction method and RPC to wallet (FornaxA)
- `2c467e1` IONCORE-62 initial bech32 address encoding functionality (FornaxA)
- `d6361f6` rpc: Accept scientific notation for monetary amounts in JSON (Wladimir J. van der Laan)
- `ef36201` IONCORE-62 bech32 and legacy encoding wrappers (FornaxA)
- `3d6e391` IONCORE-62 Switch to using bech32 wrappers (FornaxA)
- `a40fa4b` Properly display required fee instead of minTxFee (MarcoFalke)
- `082b976` Bump version for master and set release to false (cevap)
- `781442a` [fix] Add consensus/validation.h to Makefile.am (FornaxA)
- `4b8b347` Fix travis: missing dstencode.h (cevap)
- `dc4817a` Update README.md (cevap)
- `387b9f7` Update INSTALL Info (cevap)
- `f1309bf` Update snapcraft icon (cevap)
- `617c2d6` Update release notes and rename conf (cevap)
- `e139f23` Fix snapcraft for every GUI and update artworks/shortcuts (cevap)
- `b5c0aab` Update artworks and cleanup (cevap)
- `c74163b` Bump release candidate version (cevap)
- `212335c` update client ver and set as non release (cevap)
- `952dd95` update snapcraft config (cevap)
- `1bfeb9a` fix typo and trigger snapcraft build (cevap)
- `c16eb29` Update README.md (cevap)
- `4011e7c` Create CNAME (Cevap Master)
- `d4d19ed` Set theme jekyll-theme-dinky (Cevap Master)
- `7499345` Update documentation (cevap)
- `4b62637` Update README.md (cevap)
- `b133b55` Update example masnternode.conf (cevap)
- `c5a95e5` Update documentation (cevap)
- `d7e1899` Remove unrequired plugs for QT (cevap)
- `dd6a3b4` Update gitian-build.py (cevap)
- `e51a886` Update gitian-build.py (cevap)
- `e24c138` Update gitian-build.py MacOS SDK url (cevap)
- `45e19cf` Update README.md (cevap)
- `a08aa55` Set theme jekyll-theme-tactile (Cevap Master)
- `6ff6690` Update README.md (Cevap Master)
- `24e4cf0` Update README.md (Cevap Master)
- `3cda6a0` Assets: delete and move to wiki (cevap)
- `0b38bd5` Update Readme.md, move assets to wiki (cevap)
- `cc18e2a` Update README.md - Update moved assets links (cevap)
- `d82a873` Update README.md: update download links for binaries (cevap)
- `8daa2e0` Update README.md: update download links for binaries (cevap)
- `0d0ed43` contrib/gitian-build.py (cevap)
- `ce52c93` Bump beta release v3.1.0-beta1 (cevap)
- `3124135` Trigger test build of candidate v3.1.0-rc3 (cevap)
- `5fb477c` Trigger test build of edge unstable release v3.1.99-master, built from master (cevap)
- `fa713a5` Update gitian build script (cevap)
- `7c93490` Trigger devel build (cevap)
- `a42b950` Trigger build of stable v3.0.5 (cevap)
- `7e50800` Trigger stable build of v3.0.5 (cevap)
- `010a4a2` Trigger latest edge release (cevap)
- `b97dfb5` Snapcraft: change prepare to override-build to apply the patch (cevap)
- `c2f09f8` Snapcraft: change prepare to override-build for berkeleydb (cevap)
- `9848fde` Snapcraft: remove install part for berkeleydb (cevap)
- `b3cc3f5` Optimize PNGs (cevap)
- `f711cf0` Snapcraft: Add desktop-qt5 stage packages (cevap)
- `07eb151` Snapcraft: cleanup snapcraft.yaml (cevap)
- `48bbf5d` Update gitian-build.py script (cevap)
- `0438624` Enable creating zerocoin v1 spend transaction (cevap)
- `b522c93` Update CONTRIBUTING.md (cevap)
- `4fd3709` Bump to v3.1.0-rc4 and trigger snap builds (cevap)
- `197ca2f` Update gitian descriptors to bionic (cevap)
- `5dcf711` Bump version to master/unstable/devel (cevap)
- `10d01e8` Cleanup: Move gitian documentation (cevap)
- `8d454ef` Update dependencies (cevap)
- `590af25` Add dependencies patches (cevap)
- `053e846` Bump version to release and v3.1.0-rc5 (cevap)
- `3048603` Bump version to master/unstable/devel and trigger a new build (cevap)
- `9001d49` Contrib: remove old gitian-build.sh script (cevap)
- `acec024` Snapcraft: add ion description with all links (cevap)
- `5b211f2` Update build-aux (cevap)
- `3fbbfab` Revert build-aux/m4/ax_boost_program_options.m4 (cevap)
- `01c396e` Bump version to retrigger release and v3.1.0-rc5 (cevap)
- `7ed4a43` Add build_msvc (Building Ion Core with Visual Studio) (cevap)
- `d3d40f4` Patch build_msvc to ion (cevap)
- `b676b28` Gitian: revert depends to stable working (cevap)
- `6c7702a` Gitian: update gitian building to bionic (cevap)
- `31c0ad3` Release candidate v3.1.0-rc6 (cevap)
- `b478a8a` Gitian: fix building for darwin 14 on bionic (cevap)
- `aa9dc4b` contrib: update qt translations (cevap)
- `834e91e` Gitian: add aarch64 support for gitian script (cevap)
- `e80c1ba` BerkeleyDB script and documentation update (cevap)
- `1131810` Docu: cleanup assets update bootstrap.md (cevap)
- `ff6bee3` Docu: update assets from wiki in bootstrap.md (cevap)
- `f4d3ad0` Update README.md (cevap)
- `010d452` Gitian: update linux and windows descriptors (cevap)
- `d8d317a` Gitian: cleanup gitian script from double/error entries (cevap)
- `4f80f60` contrib: create new makeseeds script getting ip's from chainz (cevap)
- `4f2a28d` Update hardcoded seeds with new script (cevap)
- `f83496f` Gitian: add trusty and bionic descriptors (cevap)
- `871ee5f` Gitian: linux, downgrade for descriptor gcc from gcc8 to gcc7 (cevap)
- `b7ca4cf` Gitian: update descriptors and cleanup (cevap)
- `7a10585` Gitian: remove risc support and cleanup gitian-build.py (cevap)
- `83c4246` Update README.md - fix link to aarch64 build (Cevap Master)
- `1a3c23f` Update README.md - cleanup formatting (cevap)
- `060ff86` Update README.md - fix arm download link (cevap)
- `d8d7e2e` Bump master branch versioning (cevap)
- `000a6a3` Snapcraft: bump version to master, non stable, devel (cevap)
- `9bcbd06` Gitian: update descriptors (cevap)
- `3fea798` Update QT dependencies (cevap)
- `2914b48` Gitian: cleanup gitian-build.py script (cevap)
- `687154f` Update build-aux (cevap)
- `16d28bc` Gitian: add docker to gitian-build.py (cevap)
- `50d41c6` Retagg v3.1.0-rc6 (cevap)
- `316e44e` Bump master branch versioning (cevap)
- `1f7ec62` Gitian: fix TabError in gitian-python.py script (cevap)
- `0c3eecb` Retagg v3.1.0-rc6 (cevap)
- `65a0290` Bump master branch versioning (cevap)
- `3949613` Docu: update translation process documentation (cevap)
- `67720ae` delete tmp files (cevap)
- `c1bef9f` Revert build-aux for compilation on trusty (cevap)
- `dcd8c14` Retagg v3.1.0-rc6 (cevap)
- `e9f7dc6` Bump master branch versioning (cevap)
- `99739dc` Add xcode extraction script (cevap)
- `e1dbc1a` Update gitignore (cevap)
- `d262ec2` SNAP: Trigger build of candidate (stable) branch (cevap)
- `0288c6a` SNAP: Trigger build of candidate (stable) branch as release (cevap)
- `8db664c` Bump master branch versioning (cevap)
- `bb0c9ca` Add in qtwayland5 for Fedora (ckti)
- `65de552` Add in config.guess and config.sub from depends (ckti)
- `19ee6a0` SNAP: Update snapcraft.yaml and add new icons (cevap)
- `516e95a` SNAP: Replace libssl1.0-dev with libssl-dev (cevap)
- `461d5c4` SNAP: Add wget to packages (cevap)
- `166788a` SNAP: remove all icons and shortcuts except for ion-qt main (cevap)
- `ea50794` SNAP: fix ion.desktop (cevap)
- `cd5ee28` Gitian: updated gitian script (gitianuser)
- `983402b` Gitian: replace MacOS.sdk gzip with xz,update configs and scripts (gitianuser)
- `0769c99` Add MacOSX10.11.sdk folder to .gitignore (gitianuser)
- `4f7ec7a` Gitian: Change source for detached signatures (gitianuser)
- `f5fc1a3` Add tar.xz to .gitignore (cevap)
- `e0e7da7` Remove only trusty part from win descriptor (cevap)
- `1a4944a` Trigger snap rebuild for v3.1.00 stable candidate (cevap)
- `db88af3` Gitian: revert windows descriptors for trusty (cevap)
- `862a945` Gitian: add temporarly gitian-descriptors for bionic (cevap)
- `33cb567` Fix sync (cevap)
- `9b132a7` Fix sync of zerocoin v1 tx before zerocoin v2 starts (cevap)
- `2c3b152` Update .gitignore (cevap)
- `d47ce19` Change BIP44 for ION (cevap)
- `62357d9` IIP_0003 (cevap)
- `b6a8a0c` Bump master branch versioning (cevap)
- `f2562b0` Trigger snap rebuild for v3.1.00 stable candidate (cevap)
- `2591738` Bump master branch versioning (cevap)
- `ab7b3d0` ReTrigger snap rebuild for v3.1.00 stable candidate (cevap)
- `c65a711` Bump master branch versioning (cevap)
- `96f62f8` #91 Update accumulator checkpoints (FornaxA)
- `ae57675` Switch to internal console for vscode gdb output (FornaxA)
- `dc477ae` Retrigger v3.0.4 build (cevap)
- `17fd7db` Retrigger v3.0.5 build (cevap)
- `36586fe` Bump master branch versioning (cevap)
- `611d041` Set testnet fork parameters (FornaxA)
- `3d63fe3` Disable minting v2 xION (FornaxA)
- `eda947e` Fix whitespace error (FornaxA)
- `410a0ad` Set supermajority fork parameters to switch to block version 9, not block version 5. (FornaxA)
- `670a49e` Readd gitian-aarch64.yml for pathching (cevap)
- `dc02551` Depends: Update to most recent version (Fuzzbawls)
- `81acf5f` Build: Add automated man page generation (Fuzzbawls)
- `a077fd2` Build: Update coverage build target(s) (Fuzzbawls)
- `1715724` Build: Add bash completion support to the build system (Fuzzbawls)
- `90944d0` Build: Update build system to upstream master (Fuzzbawls)
- `3f951a6` Build: Fix gmp lib linking (Fuzzbawls)
- `adf8e4c` Remove unrequired files (cevap)
- `fbe22fe` Build: Introduce endian and byteswap (Fuzzbawls)
- `db02303` Build: Introduce Symbol and Security check scripts to the build system. (Fuzzbawls)
- `3538122` Build: Show PIC/PIE flags in configure summary (Fuzzbawls)
- `ec31683` Build: utility test updates (Fuzzbawls)
- `6e5359e` Build: Include limits.h in bignum header (Fuzzbawls)
- `4a7bc5f` Gitian: remove reference datetime (Fuzzbawls)
- `15c814c` Gitian: update descriptors for bionic (Fuzzbawls)
- `c7787d9` Travis: Update to use docker with Bionic target (Fuzzbawls)
- `50bf24d` Contrib: Update init scripts for *nix (Fuzzbawls)
- `7fd5959` Contrib: Update macdeployqtplus subdir (Fuzzbawls)
- `0590e7f` Don't show staking/automint status icons without a wallet (Fuzzbawls)
- `faa643d` Add script part for patching (will be removed) (cevap)
- `dcb836a` Travis: Introduce .travis subdir and better job folding (Fuzzbawls)
- `0941b84` Cleanup gitian-aarch64.yml after patching (cevap)
- `424db72` Add updated patched osx and linux gitian descriptors (cevap)
- `1103401` Travis: remove subtree checks (cevap)
- `9b40a8a` Fix config var in test_06_script and edit comment in before script (cevap)
- `107f5ca` Travis: disable unit tests as those fail currently (cevap)
- `958e11b` Remove redundant/duplicate declarations. (FornaxA)
- `4f0840a` Change autocombine (Cevap Master)
- `0bd3182` Update spork key valid time (FornaxA)
- `9356f7e` Revert nRejectOldSporkKey to 1546732801 (Cevap Master)
- `e1ab572` Depends: fix certificate error by moving to our repo (cevap)
- `76a287f` Update QT to 5.9.7 (cevap)
- `a643fcc` Add new checkpoint for ion v3.1.0 rc7.2 release (cevap)
- `374b1c7` Update hardcoded seeds from chainz.cryptoid.info/ion/ (cevap)
- `3d43e30` Bump candidate version v3.1.00-rc7.2 (cevap)
- `11c8bd6` Bump master branch versioning (cevap)
- `1af3ceb` Gitian: cleanup old unused descriptors for win (cevap)
- `fd4c2bf` Update README.md (cevap)
- `064f3f3` Update README.md (cevap)
- `8f60afc` Update README.md (cevap)
- `770e289` Update README.md, fix table (cevap)
- `88f63ea` Update README.md, remove table (cevap)
- `c4ae3f5` Update CPD (Cevap Master)
- `1f38e77` Update issue templates (Cevap Master)
- `416c28a` Create PULL_REQUEST_TEMPLATE (Cevap Master)
- `47d3241` Update issue templates (Cevap Master)
- `2e2d89e` Update issue templates (Cevap Master)
- `df097e3` Update issue templates (Cevap Master)
- `a5d4c61` Update README.md, fix method numbering (cevap)
- `ddde279` Set locks on cs_wallet for SelectCoinsMasternode() which is called by `masternode outputs` (FornaxA)
- `79a6743` Add proposal monitoring and voting tab (mrmetech)
- `506e77c` Stretch voting tab (warrows)
- `fc07ba0` Replace "open" with "copy" proposal url in the proposal tab (warrows)
- `9ed2968` Replace "date" with "block" in proposal tab (warrows)
- `1af0609` Update PIVX copyrights (cevap)
- `8d113dd` Add PHORE copyrights headers to proposal tab files (warrows)
- `f405485` Use without CBitcoin (cevap)
- `623a0a5` Update snapcraft.yaml (Cevap Master)
- `10db9fc` Update gitian-build.py with copyrigths (Cevap Master)
- `8eaec2b` Gitian: add risc build (cevap)
- `7550adc` openssl: abstract out OPENSSL_cleanse (Cory Fields)
- `aa9e7bc` Switch memory_cleanse implementation to BoringSSL's to ensure memory clearing even with link-time optimization. (Adam Langley)
- `d29eb79` Make checks for MN-autovoting deterministic (Mrs-X)
- `42a8628` Periodic translation update (Fuzzbawls)
- `da67a84` Update glibc_compat.cpp with risc (cevap)
- `8f1beea` Gitian: Remove depreciated non ioncoincore gpg keys (cevap)
- `fb9ba00` Gitian: add gitian keys info and README.md (cevap)
- `aa40569` Change links and names to ioncoincore specific settings (cevap)
- `64dc32a` Change ioncore.xyz to ioncoin.org (cevap)
- `d290528` Readd bittrex png (cevap)
- `f7c4fef` Fix merge issues (cevap)
- `4b4c2f5` Update SNAP links to new name (cevap)
- `ade0177` Update snapcraft (cevap)
- `abb5668` Update copyrights: bitcoin (cevap)
- `f4fd2bb` Update Ion copyrights (cevap)
- `9d70cbc` Fix: readd getextendedbalance (cevap)
- `69d940f` Update snapcraft (Ion Coin Developers)
- `17379d1` Update chainparams.cpp (cevap)
- `42a1e16` Move Transaction-Record from Qt section to Wallet section (FornaxA)
- `7243842` Move - continued (FornaxA)
- `9cf8bac` Add rpc call to view transactions as mutations to balance (FornaxA)
- `2ebc297` Remove stale RPC help data - re-add when all specs are agreed upon (FornaxA)
- `40dbeb8` Add listrecordssinceblock RPC command (currently unsorted) (FornaxA)
- `94cb5ad` Fix: add MASTERNODE_COLLATERAL_AMOUNT (cevap)
- `dc74472` Fix the way anonymizable balance calculated and fix conditions for OBF (#10) (Mitchell Cash)
- `5def41c` Print hash in CMutableTransaction::ToString (Mitchell Cash)
- `143ca24` Masternode Setup Script (ckti)
- `de455a4` Update CNAME (Ion Coin Developers)
- `06ea21a` Update issue templates (Ion Coin Developers)
- `605c21f` Update issue templates (Ion Coin Developers)
- `532a63b` Update issue templates (Ion Coin Developers)
- `89a55b5` Update harcoded seeds and add new testnet ip's (cevap)
- `bec7f11` Update issue templates (Ion Coin Developers)
- `e0a92f1` Add address to transaction records rpc output (FornaxA)
- `bb37e0a` Update issue templates (Ion Coin Developers)
- `2a53dfa` Fix Missing Explorer Icon (sicXnull)
- `29a4f25` Undo disabling minting v2 zerocoin (FornaxA)
- `5ef3c6e` update gitian-keys readme (fixes gpg fetching) (cevap)
- `c75a31e` Update gitian keys.txt (cevap)
- `2b269cb` Update FornaxA's gpg key (ioncoincore)
- `fc81e5f` Add in new key for ckti (ckti)
- `5c6b172` Update README.md, set snap name ioncore (cevap)
- `a5fc0af` Update README.md, and info about revision installation (cevap)
- `c61421d` Update README.md, add instructions for setting aliases (cevap)
- `a347313` Add additional seed ip for testnet (cevap)
- `a3fa554` Update hardcoded seeds (cevap)
- `2e2617e` Add testent checkpoint on height 500535 (cevap)
- `9dea783` Update keys.txt, add gpg fingerprint from @ioncoincore (ioncoincore@gmail.com (cevap)
- `88b8cd7` Update keys.txt, add gpg fingerprint from devpenguin (cevap)
- `f471cff` Update keys.txt, add gpg fingerprint from @zeroedge83 (cevap)
- `7d48d4c` Update keys.txt, add gpg fingerprint from @mrcoinzzz (cevap)
- `ac4d7e1` Update keys.txt, add gpg fingerprint from @gitianuser (cevap)
- `290ac97` Update keys.txt, update gpg fingerprint from @zeroedge83 (cevap)
- `635b3cb` Update symbol check script (cevap)
- `c23dc3f` Update linux descriptor (cevap)

 
## Credits

Thanks to everyone who directly contributed to this release:
- Adam Langley
- Benjamin Allred
- blondfrogs
- cevap
- Cevap Master
- ckti
- Cory Fields
- Fornax
- FornaxA
- Fuzzbawls
- gitianuser
- ioncoincore
- Ion Coin Developers
- MarcoFalke
- Mitchell Cash
- mrmetech
- Mrs-X
- presstab
- random-zebra
- sicXnull
- warrows
- Wladimir J. van der Laan
- wqking

As well as everyone that helped translating on [Transifex](https://www.transifex.com/cevap/ioncoin/), the QA team during Testing and the Node hosts supporting our Testnet.
