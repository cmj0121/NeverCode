# Design Pattern / 設計方式 #

## Over-design ##
在設計你的 API 過程中，需要瞭解到通用性 (general) 以及一致性 (consistent)。另外也需要考慮到是否有過度設計
(over-design) 的狀況發生：像是一個資料的獲取方式 (getter)，提供資料的方式有很多種，但為了一致性就需統一資料格式，
而通用性代表獲取資料之後，是否需要額外的方式來解析這些資料，然而為了滿足各方面的需求，而設計出各種可能的回傳格式，
這就稱之為過度設計。e.g.

+ getDataRaw (回傳 raw data，也就是 array)
+ getDataJson (回傳格式為 json)
