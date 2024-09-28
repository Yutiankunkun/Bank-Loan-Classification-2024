## MUFG Data Science Basic Ship 2024

### テーマ概要
タスク内容として、ある架空のローン契約者の信用情報や過去の返済情報などから、ローンが完済できない確率（not.fully.paid）を予測するモデルを作成しました。

### 評価方法
ROC AUC (Area Under the Curve) を使用します。

### データ概要
学習用：年収、ローン返済額、信用スコアなど<br>
評価用：ローンが返済できない確率

### 最終成績
LB：0.8022754<br>
PB：0.7923454<br>
Ranking：26/266<br>

### 分析方法
前処理：imputation, creating new feature(eg.installment_annual_inc_interaction)<br>
モデル：catboost + voting model<br>
**Feature：**'int.rate', 'installment', 'annual.inc', 'dti', 'fico',
       'days.with.cr.line', 'revol.bal', 'revol.util', 'inq.last.6mths',
       'delinq.2yrs', 'pub.rec',  'purpose_all_other',
       'purpose_credit_card', 'purpose_debt_consolidation',
       'purpose_educational', 'purpose_home_improvement',
       'purpose_major_purchase', 'purpose_small_business', 'installment_annual_inc_interaction'<br>
**Target：**'not.fully.paid'
