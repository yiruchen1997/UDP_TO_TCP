利用UDP Socket模擬TCP運作
====
簡介
----
以UDP socket實作TCP資料傳輸，包含Three-way handshake、影像檔案傳輸、延遲和遺漏封包的處理等。

* 實作封包傳遞影像資料，首先建立傳送端與接收端連線，利用Three-way handshake確認雙方能正確通訊後，<br>即可開始傳送接收端所請求的檔案。當成功地完成一般資料傳輸，下一步要模擬封包延遲與遺漏的情形；<br>TCP具有壅塞控制的能力，本次選擇嘗試Reno和Tahoe兩種機制進行模擬，利用有限狀態機之觀念進行狀態轉換，<br>在封包的接收上出現錯誤時便能盡快處理並復原。<br><br>
* 製作過程中，從封包的構造就有許多細節要注意，傳遞的過程中封包狀態會隨不同清況發生變化，<br>每次傳輸的檔案大小也需特別計算。<br><br>
* 經過親手實踐網路層傳輸的練習，讓我對於TCP與UDP的運作了解得更加深刻，雖然過程中經歷無數的失敗，<br>在一次次的除錯、修正後終於完成課題。

成果展示
----
Server端 : <br>
![server](https://github.com/yiruchen1997/udp_to_tcp/udp_to_tcp_server.JPG)
Client端 : <br>
![client](https://github.com/yiruchen1997/udp_to_tcp/udp_to_tcp_client.JPG)
