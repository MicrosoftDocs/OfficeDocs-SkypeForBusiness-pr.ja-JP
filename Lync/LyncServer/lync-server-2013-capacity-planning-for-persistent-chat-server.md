---
title: 'Lync Server 2013: 常設チャットサーバーのキャパシティ計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af60947a1132d26d5e8ba015d54cdbea80b8b54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 の常設チャットサーバーのキャパシティ計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-05_

常設チャットサーバーでは、ユーザーがリアルタイムでリアルタイムでチャットを行うことができます。これは、今後の取得や検索のために保持されます。 ユーザーのメールボックスに保存されているグループインスタントメッセージ (IM) とは異なり、会話履歴が構成されていると、常設チャットサーバーのセッションが開かれたままになり、コンテンツはサーバーに保存され、メッセージ、ファイル、Url、その他のデータが含まれます。進行中の会話。

キャパシティプランニングは、常設チャットサーバーの展開を準備するための重要な要素です。 このトピックでは、サポートされている常設チャットサーバートポロジとキャパシティ計画の表について詳しく説明します。これを使用すると、展開に最適な構成を決定することができます。 また、ピーク時に容量を大きくする必要がある常設チャットサーバーの展開を適切に管理する方法についても説明します。

常設チャットサーバーをダウンロードするには、の「Microsoft Lync Server 13 常設チャット[http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)サーバー」を参照してください。

常設チャットサーバーのインストールの詳細については、展開ドキュメントの「lync server [2013 での](lync-server-2013-installing-persistent-chat-server.md)常設チャットサーバーのインストールと[常設チャット2013サーバーの構成](lync-server-2013-configuring-persistent-chat-server.md)」を参照してください。

Lync Server 計画ツールなどのサポートツールを利用すると、容量の計画をさらに助けることができます。 計画ツールの詳細については、計画ドキュメントの「 [Lync Server 2013 の計画プロセスの開始](lync-server-2013-beginning-the-planning-process.md)」を参照してください。

<div>

## <a name="persistent-chat-server-supported-topologies"></a>常設チャットサーバーでサポートされているトポロジ

常設チャットサーバーは、単一サーバープールまたは複数サーバープール、または単一プールトポロジまたは複数プールトポロジで展開できます。

新しい Lync Server 2013 の展開用に、Standard Edition server 上の常設チャットサーバーもサポートされるようになりました。 ただし、パフォーマンスと規模が影響を受けます。また、この新しい展開には高可用性オプションがないため、これは主に概念や評価の証明のために使用することを前提としています。

<div>


> [!NOTE]  
> 両方のトポロジの詳細については、このドキュメントの「<A href="lync-server-2013-planning-for-persistent-chat-server.md">常設チャット2013サーバーの計画</A>」を参照してください。展開ドキュメントには、「 <A href="lync-server-2013-deploying-persistent-chat-server.md">lync server 2013 での常設チャットサーバー</A>の設定と展開」が含まれます。



</div>

<div>

## <a name="single-server-topology"></a>単一サーバートポロジ

常設チャットサーバー向けの最小構成と最も簡単な展開は、1つの常設チャットサーバーのフロントエンドサーバートポロジです。 この展開を行うには、常設チャットサーバーを実行する単一のサーバー (必要に応じてコンプライアンスサービスを実行します)、SQL Server データベースをホストしているサーバー、コンプライアンスが必要な場合は、コンプライアンスデータ。

<div>


> [!IMPORTANT]  
> トポロジビルダーでシングルサーバー展開として開始された常設チャットサーバープールにサーバーを追加することはできません。 単一のサーバーを使用している場合でも、複数サーバープールトポロジの使用をお勧めします。 これは、必要に応じて後でサーバーを追加できるようにするためです。 


</div>

次の図は、コンプライアンスを備えた単一の常設チャットサーバーフロントエンドサーバーのトポロジの必須コンポーネントとオプションコンポーネントをすべて示しています。

**1つの常設チャットサーバー**

![コンプライアンスサービスを備えた単一サーバートポロジ](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "コンプライアンスサービスを備えた単一サーバートポロジ")

</div>

<div>

## <a name="multiple-server-topology"></a>複数サーバートポロジ

より多くの容量と信頼性を実現するには、「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」で説明されているように、複数サーバートポロジを展開します。 複数サーバーのトポロジには、常設チャットサーバーを実行しているアクティブなコンピューターを4つまで含めることができます (高可用性および障害回復構成では最大8個まで可能)。ただし、4つはアクティブ、残りの4つはスタンバイ状態になります。 各サーバーは、最大で2万の同時ユーザーをサポートできます。合計で8万の同時使用ユーザーは、4台のサーバーで常設チャットサーバープールに接続されています。 複数サーバーのトポロジは、複数のサーバーが常設チャットサーバーをホストしていることを除いて、単一サーバートポロジと同じで、拡大縮小できます。 常設チャットサーバーを実行している複数のコンピューターは、Lync Server とコンプライアンスサービスと同じ Active Directory ドメインサービスドメインに存在する必要があります。

次の図は、常設チャットサーバーを実行している複数のコンピューター、オプションのコンプライアンスサービス、および別のコンプライアンスデータベースの複数サーバートポロジのすべてのコンポーネントを示しています。

**複数の常設チャットサーバー**

![複数サーバートポロジ](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "複数サーバートポロジ")

4サーバーの常設チャットサーバーの展開では、8万ユーザーは同時にサインインして常設チャットを使用することができます。ロードは、サーバーあたり2万ユーザーに均等に配布されます。 1つのサーバーが利用できなくなった場合、そのサーバーに接続されているユーザーは、常設チャットサーバーにアクセスできなくなります。 切断されたユーザーは、利用できなくなったサーバーが復元されるまでは、残りのサーバーに自動的に転送されます。 ネットワーク上での常設チャットトラフィックの量によっては、この転送には数分かかる場合があります。 残りの各サーバーは、最大3万ユーザーとしてホストされている可能性があるため、パフォーマンスの問題を回避するために、使用できないサーバーをできるだけ早く復元することをお勧めします。 それ以外の場合は、Topology Builder または Windows PowerShell コマンドレット**CsPersistentChatActiveServer**を使用して、別の常設チャットサーバーを利用できるようにすることができます。

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>常設チャットサーバーのキャパシティプランニング

常設チャットサーバーの容量計画については、次の表を参照してください。 これは、常設チャットサーバー設定の変更による容量機能への影響をモデル化しています。

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>常設チャットサーバーの最大キャパシティの計画

次のサンプル表を使用して、サポートすることができるユーザー数を判断します。

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>常設チャットサーバープールの最大容量のサンプル

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>アクティブな常設チャットサービスのインスタンス</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>常設チャットサービスのインスタンス</p></td>
<td><p><em>8 (4 は非アクティブにする必要がありますが、最大値は4です)</em></p></td>
</tr>
<tr class="odd">
<td><p>アクティブな接続ユーザー数</p></td>
<td><p><em>80,000</em></p></td>
</tr>
<tr class="even">
<td><p>プロビジョニング対象ユーザーの総数</p></td>
<td><p>150,000</p></td>
</tr>
<tr class="odd">
<td><p>エンドポイント数</p></td>
<td><p>120,000</p></td>
</tr>
</tbody>
</table>


上記のサンプルでは、常設チャットサーバーで許可される最大数のユーザーをサポートしています。常設チャットサービスの4つのサーバーとインスタンス (常設チャットサーバーを実行して、高可用性のために4つ以上のパッシブサーバーを使用できます)障害回復) と2万ユーザー (合計8万のアクティブユーザー)

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>常設チャットルームへのアクセスを管理するためのキャパシティ計画

次のサンプルテーブルは、常設チャットサーバープールでの常設チャットルームへのアクセスを管理するための計画に役立ちます。

### <a name="managing-chat-room-access-sample"></a>チャットルームへのアクセスサンプルの管理

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
<td><p>32,000</p></td>
<td><p>1,067</p></td>
<td><p>常用</p></td>
<td><p>33,077</p></td>
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
<td><p>5</p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>非オープン ルーム数 (明示的なメンバーシップがある通常のルーム)</p></td>
<td><p>31,040</p></td>
<td><p>1.035</p></td>
<td><p>5</p></td>
<td><p>32,080</p></td>
</tr>
<tr class="odd">
<td><p>大会議室数 (追加の発表者エントリ)</p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
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
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>各チャット ルームのメンバーシップ一覧におけるユーザー数 (非オープン ルーム)</p></td>
<td><p>求める</p></td>
<td><p>150</p></td>
<td><p>16,000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>各チャット ルームのメンバーシップ一覧におけるユーザー グループ数 (非オープン ルーム)</p></td>
<td><p>3</p></td>
<td><p>5</p></td>
<td><p>常用</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>各チャット ルームのマネージャー一覧におけるユーザーおよびユーザー グループ数 (オープン ルームと非オープン ルーム)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>各大会議室のチャット ルームの発表者一覧におけるユーザーおよびユーザー グループ数 (オープン ルームと非オープン ルーム)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>すべての非オープン ルームにおけるユーザー ベースのメンバーシップ エンティティ数</p></td>
<td><p>465,600</p></td>
<td><p>15,520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>すべての非オープン ルームにおけるユーザー グループ ベースのメンバーシップ エンティティ数</p></td>
<td><p>46,560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>すべての大会議室のチャット ルームにおけるユーザーおよびユーザー グループ ベースのエンティティ数</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>すべてのチャット ルーム マネージャー一覧におけるユーザーおよびユーザー グループ ベースのマネージャー エンティティ数</p></td>
<td><p>192,000</p></td>
<td><p>6,400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>チャット ルームあたりのアクティブ ユーザー</p></td>
<td><p><em>求める</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16,000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>ユーザーあたりのチャット ルーム</p></td>
<td><p><em>以内</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>16</em></p></td>
</tr>
<tr class="odd">
<td><p>各チャット ルームのメンバーシップ リストのユーザー グループ</p></td>
<td><p><em>常用</em></p></td>
<td><p><em>常用</em></p></td>
<td><p><em>マート</em></p></td>
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
<td><p>155,200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>すべてのチャット ルームのユーザー ベースのメンバーシップ エンティティ</p></td>
<td><p>465,600</p></td>
<td><p>77,600</p></td>
<td><p>72,000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>各チャット ルームのマネージャーの一覧、発表者の一覧、およびスコープの一覧のユーザーおよびユーザー グループ</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>すべてのチャット ルームのマネージャーの一覧、発表者の一覧、およびスコープの一覧のユーザーおよびユーザー グループ</p></td>
<td><p>192,000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>アクセス制御エントリ</p></td>
<td><p>704,160</p></td>
<td><p>26,768</p></td>
<td><p>160</p></td>
<td><p>731,088</p></td>
</tr>
<tr class="even">
<td><p>最大アクセス制御エントリ</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2,000,000</p></td>
</tr>
</tbody>
</table>


上記のサンプルでは、推奨されるガイドラインに従って常設チャットサーバーを展開すると、コンプライアンスが有効になっている4台のサーバープールで最大8万のアクティブユーザーを処理することができます。

このサンプルは、小規模 (常時 30 のアクティブ ユーザー)、中規模 (150 のアクティブ ユーザー)、および大規模 (16,000 のアクティブ ユーザー) として分類されたチャット ルームを示しています。 特定のサイズのチャットルームの数は、次の合計数に基づいて計算されます。

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

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>招待によってチャットルームへのアクセスを管理するためのキャパシティ計画

次のキャパシティ計画の表を使用して、招待状を送信するように構成されている場合に、常設チャットサーバーによって作成および保存される招待状の数を理解することができます。 カテゴリの招待を管理するには、Lync Server コントロールパネルの [**チャットルームのカテゴリ設定**] ページを使用するか、または Windows PowerShell コマンドレット**csPersistentChatCategory**を使用します。 Lync クライアントから起動した [会議室の**管理**] ページ、または Windows PowerShell コマンドレット**csPersistentChatRoom**を使用して、チャットルームの招待を管理することができます。

次の表のサンプル データでは、[**チャット ルームの設定**] ページの [**招待**] オプションがすべてのチャット ルームの 50 パーセントで [**はい**] に設定されていることを前提としています。

<div>


> [!IMPORTANT]  
> サーバーによって生成された招待の数の計算値が 100 万を超えると、サーバーのパフォーマンスが大幅に低下する可能性があります。 この問題を回避するには、招待を送信するように構成されているチャットルームの数を最小化するか、招待状を送信するように設定されているチャットルームに参加できるユーザー数を制限してください。



</div>

### <a name="chat-room-access-by-invitation-sample"></a>招待によるチャットルームへのアクセスのサンプル

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
<td><p><em>16,000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>チャット ルームにアクセスできるユーザー</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16,000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>常設チャットサーバーによって生成された招待状</p></td>
<td><p>960,000</p></td>
<td><p>120,000</p></td>
<td><p>80,000</p></td>
<td><p>1,160,000</p></td>
</tr>
<tr class="even">
<td><p>招待の上限数</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2,000,000</p></td>
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
<td><p>マート</p></td>
<td><p>5</p></td>
<td><p>0.1</p></td>
<td><p>超える</p></td>
</tr>
<tr class="even">
<td><p>ルームあたりのチャット レート (1 日あたり)</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1,213</p></td>
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
<td><p>4</p></td>
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
<td><p>33,077</p></td>
</tr>
<tr class="odd">
<td><p>小規模チャット ルームの数</p></td>
<td><p>32,000</p></td>
</tr>
<tr class="even">
<td><p>中規模チャット ルームの数</p></td>
<td><p>1,067</p></td>
</tr>
<tr class="odd">
<td><p>大規模チャット ルームの数</p></td>
<td><p>常用</p></td>
</tr>
<tr class="even">
<td><p>ユーザーあたりのチャット ルームの合計数</p></td>
<td><p>16</p></td>
</tr>
<tr class="odd">
<td><p>ユーザーあたりの小規模チャット ルームの数</p></td>
<td><p>以内</p></td>
</tr>
<tr class="even">
<td><p>ユーザーあたりの中規模チャット ルームの数</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>ユーザーあたりの大規模チャット ルームの数</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>ユーザーあたりの参加ルーム数</p></td>
<td><p>24</p></td>
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
<td><p>~0.15/second</p></td>
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
<td><p>Active Directory ドメインサービスの親所属の平均数</p></td>
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
<td><p>6</p></td>
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

