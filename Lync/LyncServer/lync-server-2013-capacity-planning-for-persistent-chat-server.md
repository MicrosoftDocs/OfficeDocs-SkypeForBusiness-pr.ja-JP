---
title: 'Lync Server 2013: 常設チャットサーバーの容量計画'
description: 'Lync Server 2013: 常設チャットサーバーの容量計画。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f78f9f3666fb272b808ef36da2d3010f451d0079
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544493"
---
# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 の常設チャットサーバーの容量計画

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-05_

常設チャットサーバーは、今後の取得と検索に備えて保持できる、複数ユーザーのリアルタイムチャットを実行できます。 ユーザーのメールボックスに保存されるグループインスタントメッセージング (IM) とは異なり、会話履歴が構成されている場合は、常設チャットサーバーセッションが開いたままになり、そのコンテンツがサーバーに保存されます。メッセージ、ファイル、Url、および進行中の会話の一部であるその他のデータも保存されます。

容量計画は、常設チャットサーバーを展開するための準備の重要な部分です。 このトピックでは、サポートされている常設チャットサーバートポロジと、展開に最適な構成を決定するために使用できる容量計画の表について詳しく説明します。 また、ピーク時により多くの容量を必要とする常設チャットサーバーの展開を最適に管理する方法についても説明します。

常設チャットサーバーをダウンロードするには、「」の「Microsoft Lync Server 13 常設チャットサーバー」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539) 。

常設チャットサーバーのインストールの詳細については、「展開」のドキュメントの「lync server [2013 での常設チャットサーバーのインストール](lync-server-2013-installing-persistent-chat-server.md) 」および「 [lync server 2013 での常設チャットサーバーの構成](lync-server-2013-configuring-persistent-chat-server.md) 」を参照してください。

Lync Server 計画ツールなどのサポート ツールは、容量計画の際に役に立ちます。 計画ツールの詳細については、「計画」のドキュメントの「 [Lync Server 2013 の計画プロセスの開始](lync-server-2013-beginning-the-planning-process.md) 」を参照してください。

<div>

## <a name="persistent-chat-server-supported-topologies"></a>常設チャットサーバーでサポートされているトポロジ

常設チャットサーバーは、単一サーバーまたは複数サーバーのプールに、単一プールまたは複数プールトポロジを使用して展開できます。

また、新しい Lync Server 2013 の展開用に、Standard Edition サーバー上の常設チャットサーバーもサポートしています。 ただし、パフォーマンスと規模は影響を受け、この新しい展開に高可用性オプションが存在しないため、主に、概念の実証、評価などを目的として使用することを想定しています。

<div>


> [!NOTE]  
> 両方のトポロジの詳細については、「展開」のドキュメントの「lync server <A href="lync-server-2013-planning-for-persistent-chat-server.md">2013 での常設チャットサーバーの計画</A> 」および「 <A href="lync-server-2013-deploying-persistent-chat-server.md">lync Server 2013 の常設チャットサーバーの展開</A> 」を参照してください。



</div>

<div>

## <a name="single-server-topology"></a>単一サーバー トポロジ

常設チャットサーバーの最小構成と最も簡単な展開は、1つの常設チャットサーバーのフロントエンドサーバートポロジです。 この展開では、常設チャットサーバーを実行する単一のサーバー (オプションで、コンプライアンスが有効な場合はコンプライアンスサービスを実行します)、SQL Server データベースの両方をホストするサーバー、およびコンプライアンスが必要な場合は、コンプライアンスデータを格納する SQL Server データベースを使用する必要があります。

<div>


> [!IMPORTANT]  
> トポロジビルダーでは、単一サーバー展開として開始される常設チャットサーバープールにサーバーを追加することはできません。 単一のサーバーを使用している場合でも、複数のサーバープールトポロジを使用することをお勧めします。 これにより、必要に応じて後でサーバーを追加できるようになります。 


</div>

次の図は、コンプライアンスを備えた単一の常設チャットサーバーフロントエンドサーバーのトポロジの必須およびオプションのコンポーネントを示しています。

**単一の常設チャット サーバー**

![コンプライアンスサービスを使用する単一サーバートポロジ](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "コンプライアンスサービスを使用する単一サーバートポロジ")

</div>

<div>

## <a name="multiple-server-topology"></a>複数サーバー トポロジ

容量と信頼性を高めるために、「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」に記載されているように、複数サーバートポロジを展開できます。 複数サーバートポロジには、常設チャットサーバーを実行しているアクティブなコンピューターを4台まで含めることができます (高可用性と障害復旧の構成では最大8を使用できますが、残りの4つはスタンバイ時)。 各サーバーは、最大2万の同時ユーザーをサポートできます。合計で8万同時ユーザーは、4台のサーバーがある常設チャットサーバープールに接続されます。 複数サーバートポロジは、複数のサーバーが常設チャットサーバーをホストすることを除けば、1台のサーバートポロジと同じであり、拡張性を高めることができます。 常設チャットサーバーを実行している複数のコンピューターは、Lync Server およびコンプライアンスサービスと同じ Active Directory ドメインサービスドメインに存在する必要があります。

次の図は、常設チャットサーバーを実行する複数のコンピューター、オプションのコンプライアンスサービス、および独立したコンプライアンスデータベースで構成される複数サーバートポロジのすべてのコンポーネントを示しています。

**複数の常設チャット サーバー**

![複数サーバートポロジ](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "複数サーバートポロジ")

4台のサーバーによる常設チャットサーバーの展開では、8万ユーザーが同時にサインインして常設チャットを使用できるようにすると、サーバーあたりの2万ユーザーに負荷が均等に分配されます。 1つのサーバーが使用できなくなった場合、そのサーバーに接続しているユーザーは、常設チャットサーバーへのアクセスを失います。 切断されたユーザーは、利用できなくなったサーバーが復元されるまでは、残りのサーバーに自動的に転送されます。 ネットワーク上の常設チャットトラフィックの量によっては、この転送に数分かかる場合があります。 残りの各サーバーが 30,000 ものユーザーをホストすることになる可能性があるので、パフォーマンスの問題を回避するために、利用できなくなったサーバーをできるだけ早く復元することをお勧めします。 それ以外の場合は、トポロジビルダーまたは Windows PowerShell コマンドレット **set-cspersistentchatactiveserver**を使用して、別の常設チャットサーバーを使用できるようにすることができます。

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>常設チャットサーバーの処理能力の計画

次の表は、常設チャットサーバーの容量計画に役立ちます。 これらは、さまざまな常設チャットサーバー設定の変更が容量機能に与える影響をモデル化します。

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>常設チャットサーバーの最大容量を計画する

次のサンプル表を使用して、サポートすることができるユーザー数を判断します。

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>常設チャットサーバープールの最大容量のサンプル

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>アクティブな常設チャットサービスインスタンス</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>常設チャットサービスのインスタンス</p></td>
<td><p><em>8 (4 は非アクティブである必要がありますが、最大値は4です)</em></p></td>
</tr>
<tr class="odd">
<td><p>アクティブな接続ユーザー数</p></td>
<td><p><em>80,000</em></p></td>
</tr>
<tr class="even">
<td><p>プロビジョニング対象ユーザーの総数</p></td>
<td><p>15万</p></td>
</tr>
<tr class="odd">
<td><p>エンドポイント数</p></td>
<td><p>12万</p></td>
</tr>
</tbody>
</table>


上記のサンプルでは、常設チャットサーバーが使用できる最大ユーザー数をサポートすることを計画しています。常設チャットサービスの4つのサーバーまたはインスタンス (高可用性と障害復旧のために常設チャットサーバーを実行している場合は 2万)、サーバーあたりのユーザー数は合計8万のアクティブユーザーです。

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>常設チャットルームへのアクセスを管理するための処理能力の計画

次のサンプル表は、常設チャットサーバープールでの常設チャットルームへのアクセスの管理を計画するのに役立ちます。

### <a name="managing-chat-room-access-sample"></a>チャット ルームのアクセス管理のサンプル

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>小規模チャット ルーム</th>
<th>中規模チャット ルーム</th>
<th>大規模チャット ルーム</th>
<th>合計</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>チャット ルームのサイズ (接続ユーザー数)</p></td>
<td><p>ルームあたり 30 ユーザー</p></td>
<td><p>ルームあたり 150 ユーザー</p></td>
<td><p>ルームあたり 16,000 ユーザー</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>チャット ルーム</p></td>
<td><p>32000</p></td>
<td><p>1067</p></td>
<td><p>10  </p></td>
<td><p>33077</p></td>
</tr>
<tr class="odd">
<td><p>大会議室の割合 (%)</p></td>
<td><p>1%</p></td>
<td><p>1%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>オープン ルームの割合 (%)</p></td>
<td><p>3%</p></td>
<td><p>3%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>オープン ルーム数 (明示的なメンバーシップなし)</p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>5 </p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>非オープン ルーム数 (明示的なメンバーシップがある通常のルーム)</p></td>
<td><p>31040</p></td>
<td><p>1.035</p></td>
<td><p>5 </p></td>
<td><p>32080</p></td>
</tr>
<tr class="odd">
<td><p>大会議室数 (追加の発表者エントリ)</p></td>
<td><p>.0</p></td>
<td><p>32</p></td>
<td><p>5 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>直接メンバーシップによって管理されるルーム</p></td>
<td><p>50%</p></td>
<td><p>10%</p></td>
<td><p>0%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>ユーザー グループによって管理されるルーム</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>各チャット ルームのメンバーシップ一覧におけるユーザー グループ数 (オープン ルーム (明示的には指定されていない))</p></td>
<td><p>.0</p></td>
<td><p>.0</p></td>
<td><p>.0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>各チャット ルームのメンバーシップ一覧におけるユーザー数 (非オープン ルーム)</p></td>
<td><p>31</p></td>
<td><p>150</p></td>
<td><p>16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>各チャット ルームのメンバーシップ一覧におけるユーザー グループ数 (非オープン ルーム)</p></td>
<td><p>1/3</p></td>
<td><p>5 </p></td>
<td><p>10  </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>各チャット ルームのマネージャー一覧におけるユーザーおよびユーザー グループ数 (オープン ルームと非オープン ルーム)</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>各大会議室のチャット ルームの発表者一覧におけるユーザーおよびユーザー グループ数 (オープン ルームと非オープン ルーム)</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>すべての非オープン ルームにおけるユーザー ベースのメンバーシップ エンティティ数</p></td>
<td><p>465600</p></td>
<td><p>15520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>すべての非オープン ルームにおけるユーザー グループ ベースのメンバーシップ エンティティ数</p></td>
<td><p>46560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>すべての大会議室のチャット ルームにおけるユーザーおよびユーザー グループ ベースのエンティティ数</p></td>
<td><p>.0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>すべてのチャット ルーム マネージャー一覧におけるユーザーおよびユーザー グループ ベースのマネージャー エンティティ数</p></td>
<td><p>192000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>チャット ルームあたりのアクティブ ユーザー</p></td>
<td><p><em>31</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>ユーザーあたりのチャット ルーム</p></td>
<td><p><em>個</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>16</em></p></td>
</tr>
<tr class="odd">
<td><p>各チャット ルームのメンバーシップ リストのユーザー グループ</p></td>
<td><p><em>個</em></p></td>
<td><p><em>個</em></p></td>
<td><p><em>約</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>ユーザー グループによって管理されるルーム</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>すべてのチャット ルームのユーザー グループ ベースのメンバーシップ エンティティ</p></td>
<td><p>155200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>すべてのチャット ルームのユーザー ベースのメンバーシップ エンティティ</p></td>
<td><p>465600</p></td>
<td><p>77600</p></td>
<td><p>72000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>各チャット ルームのマネージャーの一覧、発表者の一覧、およびスコープの一覧のユーザーおよびユーザー グループ</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>すべてのチャット ルームのマネージャーの一覧、発表者の一覧、およびスコープの一覧のユーザーおよびユーザー グループ</p></td>
<td><p>192000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>アクセス制御エントリ</p></td>
<td><p>704160</p></td>
<td><p>26768</p></td>
<td><p>160</p></td>
<td><p>731088</p></td>
</tr>
<tr class="even">
<td><p>最大アクセス制御エントリ</p></td>
<td></td>
<td></td>
<td></td>
<td><p>200万</p></td>
</tr>
</tbody>
</table>


前のサンプルでは、推奨ガイドラインに従って常設チャットサーバーを展開すると、コンプライアンスが有効になっている4台のサーバープールで最大8万のアクティブユーザーを処理することができます。

このサンプルは、小規模 (常時 30 のアクティブ ユーザー)、中規模 (150 のアクティブ ユーザー)、および大規模 (16,000 のアクティブ ユーザー) として分類されたチャット ルームを示しています。 特定のサイズのチャット ルームの数は、次の合計数に基づいて計算されます。

  - システム内のアクティブ ユーザー

  - 特定のサイズのチャット ルームのアクティブ ユーザー

  - 単一ユーザーが参加する特定のサイズのチャット ルーム

上記の処理能力の計画表では、各チャット ルームについて、チャット ルームに直接割り当てられたエントリなど、チャット ルームに関連付けられたアクセス制御エントリの数を示しています。アクセス制御リスト (ACL) を使用して、個々のチャット ルームへのアクセスを制御できます。また、カテゴリ レベルでアクセスを制御することもできます。ACL では、個々のアクセス制御エントリは、ユーザー グループ (セキュリティ グループ、配布リストなど) または単一ユーザーのどちらかになります。アクセス制御エントリは、チャット ルームのマネージャー、発表者、およびメンバーに対して定義できます。

<div>


> [!IMPORTANT]  
> チャット ルームの管理戦略を計画する際に、許容されるアクセス制御エントリの合計数は 200 万であることに注意してください。計算されたアクセス制御エントリが 200 万を超える場合は、サーバーのパフォーマンスが大幅に低下する可能性があります。この問題を可能な限り回避するには、アクセス制御エントリが個々のユーザーではなくユーザー グループとなるようにします。



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>チャット ルームのアクセスを招待別に管理するための処理能力の計画

次の容量計画の表を使用して、会議出席依頼を送信するように構成されている場合に常設チャットサーバーが作成して保存する招待の数を把握できます。 カテゴリの招待を管理するには、Lync Server コントロールパネルの [ **チャットルームのカテゴリ設定** ] ページを使用するか、Windows PowerShell コマンドレットを使用して **new-cspersistentchatcategory**を使用します。 チャットルームの招待を管理するには、Lync クライアントから起動されたチャットルームの **管理** ページを使用するか、または Windows PowerShell コマンドレットを使用して、 **clear-cspersistentchatroom**を行います。

次の表のサンプル データでは、[**チャット ルームの設定**] ページの [**招待**] オプションがすべてのチャット ルームの 50 パーセントで [**はい**] に設定されていることを前提としています。

<div>


> [!IMPORTANT]  
> サーバーによって生成された招待の数の計算値が 100 万を超えると、サーバーのパフォーマンスが大幅に低下する可能性があります。 この問題を回避するには、招待を送信するように構成されているチャットルームの数を最小限に抑えるか、招待状を送信するように構成されているチャットルームに参加できるユーザーの数を制限してください。



</div>

### <a name="chat-room-access-by-invitation-sample"></a>招待別のチャット ルームのアクセスのサンプル

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>小規模チャット ルーム</th>
<th>中規模チャット ルーム</th>
<th>大規模チャット ルーム</th>
<th>合計</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>チャット ルームにアクセスできるユーザー数</p></td>
<td><p>ルームあたり 30 ユーザー</p></td>
<td><p>ルームあたり 150 ユーザー</p></td>
<td><p>ルームあたり 16,000 ユーザー</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>招待があるルームの割合</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>招待を送信するように構成されているチャット ルーム</p></td>
<td><p><em>16000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>チャット ルームにアクセスできるユーザー</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>常設チャットサーバーによって生成された招待</p></td>
<td><p>96万</p></td>
<td><p>12万</p></td>
<td><p>80,000</p></td>
<td><p>116万</p></td>
</tr>
<tr class="even">
<td><p>招待の上限数</p></td>
<td></td>
<td></td>
<td></td>
<td><p>200万</p></td>
</tr>
<tr class="odd">
<td><p>モデル 1 - 1 日、1 ルームあたりの想定メッセージ数で開始</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>ルームあたりのチャット レート (1 日あたり)</p></td>
<td><p>50</p></td>
<td><p>500</p></td>
<td><p>100</p></td>
<td><p>650</p></td>
</tr>
<tr class="odd">
<td><p>すべてのチャット ルームにおけるチャット レート (1 秒あたり)</p></td>
<td><p>55.56</p></td>
<td><p>18.52</p></td>
<td><p>0.03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>モデル 2 - 1 日、1 ユーザーあたりの投稿メッセージ数で開始</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>ユーザーあたりのチャット レート (1 日あたり)</p></td>
<td><p>15 </p></td>
<td><p>5 </p></td>
<td><p>0.1</p></td>
<td><p>1280</p></td>
</tr>
<tr class="even">
<td><p>ルームあたりのチャット レート (1 日あたり)</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1213</p></td>
</tr>
<tr class="odd">
<td><p>すべてのチャット ルームにおけるチャット レート (1 秒あたり)</p></td>
<td><p>41.67</p></td>
<td><p>13.89</p></td>
<td><p>0.28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a>常設チャットサーバーのパフォーマンスユーザーモデル

次の表では、常設チャットサーバーのユーザーモデルについて説明します。 この表は、処理能力の計画の要件に関する基礎を提供し、4 台のサーバーで同時に 80,000 のユーザーに対処できる一般的な組織を表しています。

### <a name="persistent-chat-server-performance-user-model"></a>常設チャットサーバーのパフォーマンスユーザーモデル

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>アクティブな接続ユーザー数</p></td>
<td><p>80,000</p></td>
</tr>
<tr class="even">
<td><p>常設チャットサーバーサービスインスタンスの数</p></td>
<td><p>4 </p></td>
</tr>
<tr class="odd">
<td><p>小規模チャット ルームのサイズ</p></td>
<td><p>30 ユーザー</p></td>
</tr>
<tr class="even">
<td><p>中規模チャット ルームのサイズ</p></td>
<td><p>150 ユーザー</p></td>
</tr>
<tr class="odd">
<td><p>大規模チャット ルームのサイズ</p></td>
<td><p>16,000 ユーザー</p></td>
</tr>
<tr class="even">
<td><p>チャット ルームの合計数</p></td>
<td><p>33077</p></td>
</tr>
<tr class="odd">
<td><p>小規模チャット ルームの数</p></td>
<td><p>32000</p></td>
</tr>
<tr class="even">
<td><p>中規模チャット ルームの数</p></td>
<td><p>1067</p></td>
</tr>
<tr class="odd">
<td><p>大規模チャット ルームの数</p></td>
<td><p>10  </p></td>
</tr>
<tr class="even">
<td><p>ユーザーあたりのチャット ルームの合計数</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>ユーザーあたりの小規模チャット ルームの数</p></td>
<td><p>12 </p></td>
</tr>
<tr class="even">
<td><p>ユーザーあたりの中規模チャット ルームの数</p></td>
<td><p>pbm-2</p></td>
</tr>
<tr class="odd">
<td><p>ユーザーあたりの大規模チャット ルームの数</p></td>
<td><p>pbm-2</p></td>
</tr>
<tr class="even">
<td><p>ユーザーあたりの参加ルーム数</p></td>
<td><p>ソケット</p></td>
</tr>
<tr class="odd">
<td><p>ピーク時の参加レート</p></td>
<td><p>10/秒</p></td>
</tr>
<tr class="even">
<td><p>チャット レート合計</p></td>
<td><p>24/秒</p></td>
</tr>
<tr class="odd">
<td><p>小規模チャット ルームのチャット レート</p></td>
<td><p>22.22/second</p></td>
</tr>
<tr class="even">
<td><p>中規模チャット ルームのチャット レート</p></td>
<td><p>1.67/second</p></td>
</tr>
<tr class="odd">
<td><p>大規模チャット ルームのチャット レート</p></td>
<td><p>~ 0.15/秒</p></td>
</tr>
<tr class="even">
<td><p>招待が構成されているチャット ルームの割合</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>直接メンバーシップの割合</p></td>
<td><p>50%</p></td>
</tr>
<tr class="even">
<td><p>グループ メンバーシップの割合</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory ドメインサービスの先祖所属の平均数</p></td>
<td><p>100 - 200</p></td>
</tr>
<tr class="even">
<td><p>ユーザーごとの加入する連絡先の数</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>ユーザーあたりの平均エンドポイント数</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="even">
<td><p>エンドポイントあたりの表示されるチャット ルームの平均数</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="odd">
<td><p>ユーザーあたりの表示されるチャット ルームの平均数</p></td>
<td><p>2.25 (1 ルームと 2 ルームが 50% ずつ)。最大 6 ルームがオープン (1 モニターにつき 1 つ)</p></td>
</tr>
<tr class="even">
<td><p>一定間隔でポーリングされる参加者の数</p></td>
<td><p>25 (表示されるチャット ルーム 1 つあたり)</p></td>
</tr>
<tr class="odd">
<td><p>ポーリング間隔の長さ</p></td>
<td><p>5 分</p></td>
</tr>
<tr class="even">
<td><p>1 秒あたりにポーリングされる参加者の数</p></td>
<td><p>15,000</p></td>
</tr>
<tr class="odd">
<td><p>1 時間あたりのユーザーごとのプレゼンス変更の数</p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>1 秒あたりのプレゼンス変更の数</p></td>
<td><p>133.33</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

