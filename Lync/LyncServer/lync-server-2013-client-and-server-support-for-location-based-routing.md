---
title: 'Lync Server 2013: 場所に基づくルーティングに対するクライアントとサーバーのサポート'
TOCTitle: 場所に基づくルーティングに対するクライアントとサーバーのサポート
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994024(v=OCS.15)
ms:contentKeyID: 52056560
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での場所に基づくルーティングに対するクライアントとサーバーのサポート

 

_**トピックの最終更新日:** 2015-03-09_

場所に基づくルーティングは Lync Server によって適用されます。 Lync Server は、企業ネットワークの中のユーザーの接続元ネットワーク サイトを特定できます。リモート ユーザーは企業ネットワークの外部に存在するため、リモート ユーザーの場所は不明と見なされます。

## Lync Server サポート

場所に基づくルーティングでは、Lync Server 2013 CU1 が、ある特定のトポロジのすべての フロント エンド プールと Standard Edition サーバーに展開されている必要があります。 Lync Server 2013 CU1 がそのトポロジの特定の Lync コンポーネントにインストールされていない場合、場所に基づくルーティングの制約は完全には適用できません。

次の表は、場所に基づくルーティングでサポートされるサーバーの役割とバージョンの組み合わせを示しています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>プールのバージョン</th>
<th>仲介サーバー のバージョン</th>
<th>サポート対象</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 2013 年 2 月の累積更新プログラム</p></td>
<td><p>Lync Server 2013 2013 年 2 月の累積更新プログラム</p></td>
<td><p>はい</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 2013 年 2 月の累積更新プログラム</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 2013 年 2 月の累積更新プログラム</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 2013 年 2 月の累積更新プログラム</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>任意</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>任意</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>任意</p></td>
<td><p>いいえ</p></td>
</tr>
</tbody>
</table>


## Lync クライアント サポート

次の表は、場所に基づくルーティングでサポートされるクライアントを示しています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアントの種類</th>
<th>サポート対象</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>はい</p></td>
<td><p>Lync 2013 2013 年 2 月の累積更新プログラムを含む</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>はい</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>いいえ</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>はい</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Attendant</p></td>
<td><p>はい</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync for Windows 8</p></td>
<td><p>いいえ</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>いいえ</p></td>
<td><p>場所に基づくルーティングを有効にしたユーザーによって VoIP が使用される場合、VoIP を Lync Mobile 2013 クライアントに対して無効にする必要があります。</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>はい</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

> [!NOTE]
> Lync Mobile 2013 クライアントに対して VoIP を無効にするには、場所に基づくルーティングが有効なすべてのユーザーに対して、IP オーディオ/ビデオを設定を無効にしたモビリティ ポリシーを割り当てます。モビリティ ポリシーの詳細については、「<a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</a>」を参照してください。


## 関連項目

#### その他のリソース

[Lync Server 2013 での場所に基づくルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)

