---
subtitle: 如何選擇雲端運算
hero_height: is-small
layout: page
hero_image: "/img/sitev1.0/homeen.jpg"
---

cloud是形象的定義，也是模糊的定義。以我們常用的虛擬伺服器為例，前代產品為網站設計，主要特徵是缺少公共IP，網站需要計算資源相對簡單，於是只要網站能解析域名就可以，若要單需要獨立IP，前代方案叫Dedicate Server，比網站用伺服器貴很多。

#### 雲端運算是計算資源商業化的結果

同前代產品相比，雲端運算採用搭積木方法，多用多付，少用少付，用1付1,用10付10。價格非常適合小企業使用。例如，從前若需要某種應用軟體，一種方法採用叫Client/Server方式，只能採用內部IP，意味著只能在安裝地內部使用。另一種方式需要自建Data center，也許能採用公共IP，但造價昂貴，非中小企業能承受。而云端計算使計算資源價格降低，同時有公共IP，意味著只要有網絡，就可以訪問應用軟體。

#### 關於延遲

我們見到如AWS(亞馬遜雲),Google Cloud在靠近用戶所在地自建計算中心，為防止應用軟體延遲。對於某些用戶，例如用戶數大的通訊app，延遲0.1 微秒可能很要緊，但云端運算的基礎是寬帶網絡，延遲1微秒，對於多數中小企業不重要。要緊的是價格。

#### 選擇雲端供應商

市場上有很多雲端供應商，該選哪家？

以下是依次考慮的要素：

- 價格，以Odoo 12.0為例，docker container方式，雲端安裝。預計20個用戶同時使用，估計可供50個用戶使用，估計4GB內存，2vCPU夠用
-AWS， 4GB 2vCPU，Linux on t3.medium，Asia Pacific (Hong Kong) 簽約保證使用3年，USD566/3 年預付， 合USD 15.7/Month， [AWS MONTHLY CALCULATOR](https://calculator.s3. amazonaws.com/index.html)
-Google Cloud,type: n1-custom-2-4096, Region: Taiwan, Commitment term: 3 Years, USD 30.50 per 1 month, (google cloud pricing calculator)
-Dgitalocean CPUs 2, Memory 4 GB, Storage 80 GB, Transfer 4 TB USD20/Month
- 規模，憑運氣猜越大越不容易倒閉，好在可以預先遷移。
- 聲譽，因個人理解不同

#### 結語

對於中小企業涉足雲端運算，應採取與大型公司不同的策略，中小企業看中的是計算資源商業化帶來的價格優勢，使中小企業能在雲端部署企業需要的應用軟體，通過聯網實時訪問應用裡的數據。
