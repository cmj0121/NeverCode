# Design Pattern / 設計方式 #

## Over-design ##
在設計你的 API 過程中，需要瞭解到通用性 (general) 以及一致性 (consistent)。
另外也需要考慮到是否有過度設計 (over-design) 的狀況發生：像是資料的獲取方式 (getter)
回傳資料的格式有很多種。然而為了滿足各方面的需求，而設計出各種可能的回傳格式，
這就稱之為過度設計。e.g.

+ getDataRaw (回傳 raw data，也就是 array)
+ getDataJson (回傳格式為 json)

## Check Status ##
在檢查狀態的時候可能會遇到非同步 (asynchronous) 的狀況，像是：觸發之後需要等一段時間才知道結果，
設計上就需要考量合理的等待時間 (threshold) 與即時性 (on-time)：

+ hardcode 寫死一個等待時間是不合理的，彈性降低也容易有不需要的等待時間。
+ 沒有終止條件是不合理的，無限制地等待會造成系統不會中止。
+ 頻繁的檢查是不合理的，檢查邏輯會變成是一個 busy-loop，要善用 sleep 來釋放 CPU 資源。
