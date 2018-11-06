---

copyright:
  years: 2014, 2018
lastupdated: "2018-09-18"

---
{:new_window: target="_blank"}

# 常見問題

## 有多少實例可以共用 {{site.data.keyword.blockstorageshort}} 磁區？
每個區塊磁區的授權數目預設限制是 8。這表示最多可以授權 8 個主機存取 Block Storage LUN。若要要求提高限制，請與業務代表聯絡。

## 可以訂購多少個磁區？
依預設，您可以佈建總計 250 個 {{site.data.keyword.blockstorageshort}} 磁區。若要增加磁區限制，請與業務代表聯絡。如需相關資訊，請參閱[管理儲存空間限制](managing-storage-limits.html)。

## 一個主機可以裝載多少個 {{site.data.keyword.blockstorageshort}} 磁區？
這取決於主機作業系統可處理的項目，而不是由 {{site.data.keyword.BluSoftlayer_full}} 所限制。如需可裝載的磁區數目限制，請參閱 OS 文件。

## 已配置的 IOPS 限制是依據實例還是依據磁區施行？
IOPS 是在磁區層次上施行。換句話說，連接至具有 6000 IOPS 之磁區的兩台主機會共用該 6000 IOPS。

## 測量 IOPS
IOPS 根據具有隨機 50% 讀取及 50% 寫入之 16 KB 區塊的載入設定檔進行測量。與此設定檔不同的工作負載可能會遇到較差的效能。

## 使用較小的區塊大小來測量效能時會發生什麼事？
使用較小的區塊大小時，仍然可以取得最大 IOPS。不過，傳輸量會變小。例如，具有 6000 IOPS 的磁區會有下列各種區塊大小的傳輸量：

- 16 KB * 6000 IOPS == ~93.75 MB/秒 
- 8 KB * 6000 IOPS == ~46.88 MB/秒
- 4 KB * 6000 IOPS == ~23.44 MB/秒

## 磁區是否需要預先暖機，才能達到預期的傳輸量？
不需要預先暖機。佈建磁區時，您可以立即觀察到指定的傳輸量。

## 使用較快的乙太網路連線可以達到更高傳輸量嗎？
傳輸量限制是以每個磁區/LUN 層次而設定，因此，使用速度更快的乙太網路連線並不會增加該項已設定的限制。不過，乙太網路連線較慢時，您的頻寬可能是潛在瓶頸。

## 防火牆/安全群組是否會影響效能？
最好是在 VLAN 上執行儲存空間資料流量，這樣會略過防火牆。透過軟體防火牆執行儲存空間資料流量，會增加延遲，而且對儲存空間效能有不利的影響。

## 預期的 {{site.data.keyword.blockstorageshort}} 延遲是多少？   
儲存空間內的目標延遲為 < 1 毫秒。我們的儲存空間會連接至共用網路上的運算實例，因此，確切的效能延遲取決於在作業期間的網路資料流量。

## 為什麼可以在某些資料中心內訂購具有「耐久性 10 IOPS/GB」層級的 {{site.data.keyword.blockstorageshort}}，但不能在其他資料中心內進行？
「耐久性」類型 {{site.data.keyword.blockstorageshort}} 的 10 IOPS/GB 層級只能用於精選資料中心，並且正在逐步新增新的資料中心。您可以在[這裡](new-ibm-block-and-file-storage-location-and-features.html)找到完整的已升級資料中心及可用特性清單。

## 如何分辨哪些 {{site.data.keyword.blockstorageshort}} LUN/磁區已加密？
在 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} 中查看 {{site.data.keyword.blockstorageshort}} 清單時，您會在已加密的 LUN/磁區名稱右側看到一個鎖定圖示。

## 如何知道是否在已升級資料中心內佈建 {{site.data.keyword.blockstorageshort}}？
當您訂購 {{site.data.keyword.blockstorageshort}} 時，會在訂單表格中以星號 (`*`) 表示所有已升級的資料中心，並指出您即將佈建具有加密的儲存空間。佈建儲存空間時，您可以在儲存空間清單中看到一個圖示，顯示該儲存空間已加密。所有已加密的磁區及 LUN 都只會佈建在已升級的資料中心內。您可以在[這裡](new-ibm-block-and-file-storage-location-and-features.html)找到完整的已升級資料中心及可用特性清單。

## 如果我們在最近升級的資料中心擁有未加密的 {{site.data.keyword.blockstorageshort}}，可以加密該 {{site.data.keyword.blockstorageshort}} 嗎？
無法加密在資料中心升級之前所佈建的 {{site.data.keyword.blockstorageshort}}。會自動加密在已升級資料中心內佈建的新 {{site.data.keyword.blockstorageshort}}。沒有任何加密設定可供選擇，它是自動的。您可以加密已升級資料中心內未加密儲存空間的資料，方法是建立新的「區塊 LUN」，然後利用主機型移轉，將資料複製到新的加密 LUN。如需指示，請按一下[這裡](migrate-block-storage-encrypted-block-storage.html)。

## {{site.data.keyword.blockstorageshort}} 是否支援「SCSI-3 持續保留」來實作 Db2 pureScale 的 I/O 隔離？
是，{{site.data.keyword.blockstorageshort}} 同時支援 SCSI-2 及 SCSI-3 持續保留。

## 刪除 {{site.data.keyword.blockstorageshort}} LUN 時，資料會發生什麼情況？
{{site.data.keyword.blockstoragefull}} 會向客戶呈現在任何重複使用之前抹除的實體儲存空間上的 Block 磁區。具有特殊規範需求的客戶（例如 NIST 800-88 媒體資料安全清除準則）必須先執行資料安全清除程序，再刪除其儲存空間。

## 從雲端資料中心解除任務的磁碟機會發生什麼情況？
磁碟機解除任務時，IBM 會先破壞它們再進行處理。磁碟機變成無法使用。已寫入該磁碟機的任何資料都會變成無法存取。