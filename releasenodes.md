### Core
- #875 a99c2dd3bb [Zerocoin] GMP BigNum: Fix limits for random number generators (random-zebra)
- #888 0c071c3fd0 [Zerocoin] remove CTransaction::IsZerocoinSpend/IsZerocoinMint (random-zebra)
- #891 855408c2c3 [ZPIV] Zerocoin public coin spend. (furszy)
- #897 65bd788945 [zPIV] Disable zerocoin minting (random-zebra)
- #899 4b22a09024 [zPIV] Disable zPIV staking (random-zebra)
- #909 458b08c8f2 [Consensus] Mainnet public spend enforcement height set. (furszy)
- #924 988b33dab8 [Backport] Max tip age to consider a node in IBD status customizable. (furszy)
- #925 a9827a0e63 [Consensus] Time checks (warrows)

### Build System
- #810 a373fee908 [Depends] Fix archs (fixes s390x and ppc64el builds on snap) (cevap)
- #906 8a47747b59 [Build] Add CMake Support (Fuzzbawls)
- #910 07c8fb8f88 [Build] Clean all coverage files during make clean (Fuzzbawls)
- #913 473976c619 [Depends] Update from upstream (Fuzzbawls)
- #914 5a43ea790a [Gitian] Bump gitian build versions (Fuzzbawls)
- #917 b38ef04838 [Build] TravisCI Update (Fuzzbawls)
- #922 0f98fd4d3f [Build] Fix app name casing in mac deploy related files (Fuzzbawls)

### P2P Protocol and Network Code
- #908 95b584effd [NET] Non-running dns servers removed from chainParams. (furszy)
- #929 7e8855d910 [Net] Update hard-coded seeds (Fuzzbawls)
- #930 5061b486c2 [Net] Add a couple new testnet checkpoints (Fuzzbawls)

### GUI
- #874 23f17ce021 [Qt] Add new budget colors (warrows)
- #895 0417d52ef9 [QT] Options UI cleanup (Alko89)
- #896 b2fcefee93 [UI] Simplify Qt margins. (warrows)
- #898 3d496cc746 [Qt] Fixup duplicate label names (Fuzzbawls)
- #900 5f7559bc7b [UI] Fix improperly parented walletView and segmentation fault on QT 5.10 (Julian Meyer)
- #928 2482572f89 [Qt] Update Translations (Fuzzbawls)

### RPC/REST
- #877 54c8832d80 [RPC] Remove deprecated masternode/budget RPC commands (Fuzzbawls)
- #901 be3aab4a00 [RPC] Fix typos and oversights in listunspent (CaveSpectre11)
- #911 484c070b22 [RPC] add 'getblockindexstats' function (random-zebra)

### Wallet
- #813 80bf51e7c9 [Refactoring] [Move Only] Move wallet files into their own folder (warrows)
- #916 a4f02ed946 [Staking] Don't assert if we were beaten to the block (CaveSpectre11)

### Unit Tests
- #806 fc6b5a191d [Test] Create new per-test fixtures (Wladimir J. van der Laan)
- #902 8adeeb9727 [Tests] Add tests for CAddrMan (warrows)

###Miscellaneous
- #744 7e52f58b82 [Refactor] Refactor bignum header file into several files (warrows)
- #808 8b54f7150b [Scripts] Add optimize pngs python script (cevap)
- #824 3323f26848 [Refactor] Remove stale obfuscation code (Fuzzbawls)
- #830 81038da4f8 [Refactor] Remove BOOST_FOREACH (Fuzzbawls)
- #844 0a0dcf0d4e [Refactor] Replace deprecated auto_ptr with unique_ptr (cevap)
- #856 da26ddeeb9 [Refactor] Move per-chain budget cycle blocks to chainparams (Fuzzbawls)
- #879 5f0d72659c [Refactor] Rename ui_interface.h file (Fuzzbawls)
- #890 fddac44eab [Refactor] Remove unused setStakeSeen variable (warrows)
- #903 68c81c407a [Log] Handle errors during log message formatting (warrows)
- #904 6f597629d8 [zPIV] Free memory from ToString() (warrows)
- #912 5f167c2c7e [Cleanup] compiler warnings in coinSpend object. (furszy)
- #919 c0233e4af6 [zPIV] Debug missing jump line. (Matias Furszyfer)
- #920 a56cc2948d [Docs] Overhaul documentation files (Fuzzbawls)
- #921 893183339e [Scripts] Overhaul supplemental python/shell scripts (Fuzzbawls)
- #926 49a69b8931 [Doc] 3.3.0 Notable Changes (Fuzzbawls)
- #927 048d1295dc [Trivial] Update header copyright years (Fuzzbawls)

##Credits

Thanks to everyone who directly contributed to this release:

- Alko89
- CaveSpectre11
- Fuzzbawls
- Julian Meyer
- Matias Furszyfer
- cevap
- Wladimir J. van der Laan
- random-zebra
 -warrows
