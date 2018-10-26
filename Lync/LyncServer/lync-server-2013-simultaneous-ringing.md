---
title: 'Lync Server 2013: 同時呼び出し'
TOCTitle: 同時呼び出し
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994079(v=OCS.15)
ms:contentKeyID: 52056721
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での同時呼び出し

 

_**トピックの最終更新日:** 2015-03-09_

呼び出し先で同時呼び出しが有効な場合、場所に基づくルーティングは呼び出し元の場所と呼び出し先のエンドポイントを分析し、呼び出しをルーティングするかどうかを決めます。

次の表は、同時呼び出しが構成されたユーザーを示します。同時呼び出しのターゲット ユーザーは、同じネットワーク サイトのユーザー、異なるネットワーク サイトのユーザー、または不明なネットワーク サイトのユーザーです。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>PSTN 着信の対象</th>
<th>呼び出し先と同じネットワーク サイトにある</th>
<th>呼び出し先とは別のネットワーク サイトにある</th>
<th>不明なネットワーク サイトにあるか、場所に基づくルーティングが有効になっていないネットワーク サイトにある</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー</p></td>
<td><p>同時呼び出しが許可される</p></td>
<td><p>同時呼び出しは許可されない</p></td>
<td><p>同時呼び出しは許可されない</p></td>
</tr>
</tbody>
</table>

  
次の表は、同じネットワーク サイト、異なるネットワーク サイト、不明なネットワーク サイトの Lync ユーザー (Lync の呼び出し元) からの呼び出しを示します。呼び出し先には、同時呼び出しのターゲット ユーザーとして、PSTN エンドポイント (携帯電話) が構成されています。このシナリオでは、呼び出し先の同時呼び出しのターゲット ユーザー (携帯電話) に呼び出しがルーティングされるかどうかを、場所に基づくルーティングで決定します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>同時呼び出しのターゲット ユーザー</th>
<th>呼び出し先と同じネットワーク サイトにある</th>
<th>呼び出し先とは別のネットワーク サイトにある</th>
<th>不明なネットワーク サイトにあるか、場所に基づくルーティングが有効になっていないネットワーク サイトにある</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN エンドポイント</p></td>
<td><p>呼び出し元のサイトの音声ルーティング ポリシーによって同時呼び出しが許可される</p></td>
<td><p>呼び出し元のサイトの音声ルーティング ポリシーによって同時呼び出しが許可される</p></td>
<td><p>場所に基づくルーティングが有効になっていないトランクへの呼び出し元の音声ポリシーによって同時呼び出しが許可される</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### その他のリソース

[Lync Server 2013 の場所に基づくルーティングのシナリオ](lync-server-2013-scenarios-for-location-based-routing.md)

