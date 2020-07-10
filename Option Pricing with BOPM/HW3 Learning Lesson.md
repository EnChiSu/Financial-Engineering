# HW3 Lesson learn

1. 這次作業的一個insight是，在BOPM下，我們即使不知道上漲下跌的機率為多少，但我們可以透過當下的無風險報酬率、上漲報酬率以及下跌報酬率得到此上漲下跌的機率，而有了此機率搭配無風險報酬率，我們就可以根據該期不同漲跌情境的payoff回推前一期選擇權的價值。

2. 報酬率為exp(r)=(1+r/m)^m，不同於年利率r。因而在此次作業中我們必須要將使用者輸入的無風險年利率轉為無風險報酬率。

3. 我原本想要用pandas當中儲存一維陣列的Series來儲存計算結果，在第一個element儲存第一期的payoff、第二期儲存第二期兩種情況的payoff...以此類推，但遇到一個問題是Series沒辦法儲存維度不同的物件，因而改使用pandas當中儲存二維陣列的Dataframe，將列向量設定為期數，行向量設定為下跌次數(也就是可能發生的不同情境)，將計算出來的結果存入相對應的cell當中，而表格當中不存在的情境則用NA表示。