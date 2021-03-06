---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-05"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 常見問題：裸機伺服器

## 為什麼 BIOS 要求輸入密碼？

目前，{{site.data.keyword.cloud}} 無法讓您直接存取 BIOS。這可能有各種原因，但不表示您無法變更 BIOS。如果您需要在 BIOS 中修改任何項目（包括開機順序），請透過[客戶入口網站](control.softlayer.com)的「支援中心」>「新增問題單」來建立問題單，並要求您需要的特定變更。

\*\*附註\*\* 這需要將伺服器重新開機才能執行，因此，請準備好核准重新開機，及（或）提供您要進行變更的時間範圍。

## 您是否提供增補的「OS 重新載入」？

自動化 OS 重新載入是免費的，可以透過[客戶入口網站](control.softlayer.com)執行。這些包括自訂的 OS 重新載入（變更作業系統、新增/移除控制面板/分割區編輯等等）。如需執行「OS 重新載入」的詳細資訊，請參閱 [OS 重新載入程序](../vsi/vsi_perform_os_reload.html)。


## 裸機伺服器上的主要磁碟機顯示為 /dev/sdb。哪裡出錯？

原因可能是 IPMI 中使用 /dev/sda 插槽的「虛擬磁碟」。連接至 IPMIView 並瀏覽至「虛擬媒體」標籤，即可放心地予以停用。選取**選項 > 停用**，然後按一下**套用**按鈕來進行變更。下次將 {{site.data.keyword.baremetal_short}} 重新開機時，主要磁碟機會顯示 /dev/sda。


## CPU 速度為何錯誤？

如果您登入伺服器以檢查 CPU 資訊，並注意到處理器速度不正確。這項差異可能是「增強型 Intel SpeedStep 技術 (EIST)」所造成。EIST 是動態頻率調整技術的 Intel 名稱。在較舊的系統中，此技術也稱為 *CPU 節流控制* 或*匯流排迴轉*。在某些 AMD 系統上，有類似的技術稱為 *Cool'N'Quiet* 或 *PowerNow!*。雖然這些技術並非全部相同，但目標都相同，就是在未大量使用處理器時，藉由讓 CPU 速度變慢，來降低耗電量和熱生產。伺服器回復成低於載入時，會視需要提高時鐘速度。

如果您要瞭解伺服器上的 Intel 處理器是否支援 SpeedStep、客戶入口網站，請執行下列動作： 
1. 按一下**裝置**。
* 在清單中，識別您的伺服器。
* 按一下伺服器名稱，以檢視**裝置詳細資料**。
* 找出標題為**硬體**的子區段，以尋找伺服器處理器型號的 CPU 速度。
* 使用伺服器處理器型號，跳至 [Intel 處理器搜尋器](http://processorfinder.intel.com/)，並使用此型號來尋找處理器的相關資訊，以及它是否支援「加強型 Intel SpeedStep 技術」。

EIST 是已建立的技術。您應該沒有理由關閉 EIST。不過，如果您決定不要使用此特性，請向「支援團隊」開立問題單以停用此特性。為了停用此特性，伺服器將重新開機。


## 如果裸機伺服器的韌體已過期，會發生什麼情況？

如同軟體更新，請務必持續更新韌體，以確保最佳裝置相容性及穩定性。如果 {{site.data.keyword.baremetal_short}} 韌體已過期，則可以在[客戶入口網站](https://control.softlayer.com)內於 [OS 重新載入](../infrastructure/software/vsi_reload_os.html)處理程序期間起始韌體更新。

您也可以藉由從裝置清單中選取裸機伺服器，並從動作功能表下拉清單中選取**更新韌體**，來更新韌體。
