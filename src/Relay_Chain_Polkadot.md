今天聊聊最近看的 会比较杂 relay chain （接力链） 主要作用是解决链与链交换token的问题， 目前有很多解决方案， relay BTC是 btc对以太坊 首先确定锁定BTC 等 block mined 发到contract 中 完成交换 这里的问题是单向型 BTC 并没有contract。 BTC 有自己独有的2-way peg（双向锁定） 有很多种实现方式 中心化的可以设置一个交易所可以实现双向锁， 或者请求链外信息oracle（先知）的公正即加一个multsig 的wallet。 去中心化也有两种 一种叫Sidechains（侧链） 先锁BTC， 发SPV（Simplified Payment Verification）然后对方链 确认 发SPV 回来 解锁 这里面有个问题是 如何确认对方链不double spending。 另外一个方案Entangled Blockchains（双链合并）这里面 对方链里保存BTC中的header 信息 ， 其实这里面还要加一个OP_RETURN的操作信息 对方链中 block 保证有BTC block 作为父block 可以保证撤销交易（这个我没完全研究清楚， 求大神给讲一讲）。 最新的relay chain是 Parity 正在研究的Polkadot 这个很有意思的一片论文。  Topology（网络结构）是一个中心（Hub） 其中有四个角色 Validators， Nominators（提交者）  Collators（校对者）Fishermen（城管）. 上图： 这个可以链接任何区块链 把所有区块链的状态写入自己block中 为了最大限度包容所有Blockchain，系统设计做了最大容忍。 C 作用是在各个区块链client中mining，负责提供ZK的查询，  N是把token stake 到系统中，为V 提供资格 V主要流动在系统group中完成不同区块链状态的查询和写入本身自己的区块中， 最后F 随时查找adversary（坏人）获得系统奖励。 （题外话 不知道这个ICO 不 ）论文我没看完 已经受益匪浅 推荐大家看看 。 最后 今天看了一下 long chain attract 即 攻击者 在genesis block（初始0 块） 进行mining， 最后可以颠覆整个区块的攻击 这种攻击的特点是一定要在图灵完成的区块链中才会出现 解决方案 就是保存所有中间的temp(临时) hash ， 这样保护区块链 但是这样子就无法避免ASIC的集中问题 ASIC是专门电路设计特别适合hash的电子器件， 或者不接受过分旧的时间的区块也可以解决这个问题。
链接：https://blog.ethereum.org/2014/05/15/long-range-attacks-the-serious-problem-with-adaptive-proof-of-work/
链接：https://blog.stephantual.com/web-3-0-revisited-part-one-across-chains-and-across-protocols-4282b01054c5
链接：https://ethereum.stackexchange.com/questions/16911/what-is-polkadot-in-laymans-terms
链接：http://www.rsk.co/blog/sidechains-drivechains-and-rsk-2-way-peg-design


https://aion.network/downloads/aion.network-technical-introduction_en.pdf 

https://www.youtube.com/watch?v=_aLmzq-23pE

https://www.youtube.com/watch?v=z8INzy9E628

https://medium.com/@jeffzoch/ark-vs-aion-a-comparison-of-two-blockchain-bridging-efforts-b513094381ca
