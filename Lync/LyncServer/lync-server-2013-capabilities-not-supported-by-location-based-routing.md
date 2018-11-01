---
title: 'Lync Server 2013: 場所に基づくルーティングでサポートされていない機能'
TOCTitle: 場所に基づくルーティングでサポートされていない機能
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994071(v=OCS.15)
ms:contentKeyID: 52056697
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の場所に基づくルーティングでサポートされていない機能

 

_**トピックの最終更新日:** 2014-03-12_

場所に基づくルーティングは、次の種類の操作には適用されません。場所に基づくルーティングは、Lync エンドポイントが次の機能を使って PSTN エンドポイントとやり取りするときには実行されません。

  - 会議への PSTN ダイヤルイン

  - 応答グループによる PSTN 通話の着信および発信

  - 通話保留による PSTN 通話の保留または再開

  - アナウンス サービスへの PSTN 通話の着信

  - 着信 PSTN 通話のグループ通話ピックアップによる再開

次のリストにある種類の操作に場所に基づくルーティング規則を施行するには、会議の場所に基づくルーティングを有効にする必要があります。

  - 会議からの PSTN ダイヤルアウト

  - ピアツーピアの音声会話から PSTN エンドポイントを利用する会議へのエスカレーション

  - PSTN エンドポイントを利用する取次転送

会議の場所に基づくルーティングを有効にする方法の詳細については、「[会議の場所に基づくルーティング](lync-server-2013-location-based-routing-for-conferencing.md)」を参照してください。

## 関連項目

#### その他のリソース

[Lync Server 2013 での場所に基づくルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)

