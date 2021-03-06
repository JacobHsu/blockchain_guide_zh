## 同態加密

### 定義

同態加密（Homomorphic Encryption）是一種特殊的加密方法，允許對密文進行處理得到仍然是加密的結果。即對密文直接進行處理，跟對明文進行處理後再對處理結果加密，得到的結果相同。從抽象代數的角度講，保持了同態性。

同態加密可以保證實現處理者無法訪問到數據自身的信息。

如果定義一個運算符 $$\triangle{}$$，對加密算法 `E` 和 解密算法 `D`，滿足：

$$E(X\triangle{}Y) = E(X)\triangle{} E(Y)$$

則意味著對於該運算滿足同態性。

同態性來自代數領域，一般包括四種類型：加法同態、乘法同態、減法同態和除法同態。同時滿足加法同態和乘法同態，則意味著是代數同態，即全同態（Full Homomorphic）。同時滿足四種同態性，則被稱為算數同態。

對於計算機操作來講，實現了全同態意味著對於所有處理都可以實現同態性。只能實現部分特定操作的同態性，被稱為特定同態（Somewhat Homomorphic）。

### 問題與挑戰

同態加密的問題最早在 1978 年由 Ron Rivest、Leonard Adleman 和 Michael L. Dertouzos 提出（同年 Ron Rivest、Adi Shamir 和 Leonard Adleman 還共同發明了 RSA 算法）。但第一個“全同態”的算法直到 2009 年才被克雷格·金特里（Craig Gentry）在論文《Fully Homomorphic Encryption Using Ideal Lattices》中提出並進行數學證明。

僅滿足加法同態的算法包括 Paillier 和 Benaloh 算法；僅滿足乘法同態的算法包括 RSA 和 ElGamal 算法。

同態加密在雲計算和大數據的時代意義十分重大。目前，雖然雲計算帶來了包括低成本、高性能和便捷性等優勢，但從安全角度講，用戶還不敢將敏感信息直接放到第三方雲上進行處理。如果有了比較實用的同態加密技術，則大家就可以放心的使用各種雲服務了，同時各種數據分析過程也不會洩露用戶隱私。加密後的數據在第三方服務處理後得到加密後的結果，這個結果只有用戶自身可以進行解密，整個過程第三方平臺無法獲知任何有效的數據信息。

另一方面，對於區塊鏈技術，同態加密也是很好的互補。使用同態加密技術，運行在區塊鏈上的智能合約可以處理密文，而無法獲知真實數據，極大的提高了隱私安全性。

目前全同態的加密方案主要包括如下三種類型：

* 基於理想格（ideal lattice）的方案：Gentry 和 Halevi 在 2011 年提出的基於理想格的方案可以實現 72 bit 的安全強度，對應的公鑰大小約為 2.3 GB，同時刷新密文的處理時間需要幾十分鐘。
* 基於整數上近似 GCD 問題的方案：Dijk 等人在 2010 年提出的方案（及後續方案）採用了更簡化的概念模型，可以降低公鑰大小至幾十 MB 量級。
* 基於帶擾動學習（Learning With Errors，LWE）問題的方案：Brakerski 和 Vaikuntanathan 等在 2011 年左右提出了相關方案；Lopez-Alt A 等在 2012 年設計出多密鑰全同態加密方案，接近實時多方安全計算的需求。

目前，已知的同態加密技術往往需要較高的計算時間或存儲成本，相比傳統加密算法的性能和強度還有差距，但該領域關注度一直很高，筆者相信，在不遠的將來會出現接近實用的方案。

### 函數加密
與同態加密相關的一個問題是函數加密。

同態加密保護的是數據本身，而函數加密顧名思義保護的是處理函數本身，即讓第三方看不到處理過程的前提下，對數據進行處理。

該問題已被證明不存在對多個通用函數的任意多密鑰的方案，目前僅能做到對某個特定函數的一個密鑰的方案。

