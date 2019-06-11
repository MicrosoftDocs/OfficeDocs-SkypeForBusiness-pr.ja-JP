---
title: 'Lync Server 2013: ELIN ゲートウェイの場所を管理する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b447a150a48255a04e5a332cc5d0f56110848f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a>Lync Server 2013 での ELIN ゲートウェイの場所の管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

Lync Server でネットワーク内のクライアントの場所を自動的に提供するには、次のタスクを実行する必要があります。

  - ネットワーク wiremap を使用して位置情報サービスデータベースを設定し、緊急対応の場所の識別番号 (ELINs) を CompanyName フィールドに含めます。

  - 場所を、ネットワーク内のクライアントが利用できるように公開します。

  - ELIN を、公衆交換電話網 (PSTN) 通信業者の自動ロケーション識別 (ALI) データベースにアップロードします。

これらのタスクの実行方法の詳細については、展開ドキュメントの「 [Lync Server 2013 で場所データベースを構成](lync-server-2013-configure-the-location-database.md)する」を参照してください。

<div>


> [!NOTE]  
> 中央の場所のデータベースに追加された場所は、Lync Server 管理シェルコマンドを使用して公開され、プールのローカルストアにレプリケートされるまで、クライアントでは利用できません。 詳細については、展開ドキュメントの「 <A href="lync-server-2013-publish-the-location-database.md">Lync Server 2013 からロケーションデータベースを発行</A>する」を参照してください。



</div>

このセクションでは、場所データベースの更新および保守の計画を立てるときに考慮する必要のある事項を説明します。

<div>

## <a name="planning-emergency-locations"></a>緊急位置の計画

ELIN ゲートウェイを使用する場合、場所情報サービスデータベースに、都市の住所、建物内の特定の場所、および各場所の少なくとも1つの ELIN を設定します。 計画段階で、場所にどのように名前を付けるのか、どのように ELIN を割り当てるのかを決定しておくことをお勧めします。

<div>

## <a name="planning-location-names"></a>場所名の計画

建物内の特定の場所を保持する "位置情報サービスの**場所**" フィールドでは、最大20文字 (スペースを含む) が使用されます。 この制限された長さの中に、以下を含めるようにします。

  - 緊急対応員が特定の住所に到着したときに緊急通報をした人の場所がすぐにわかるように、場所を具体的に特定するわかりやすい名前。この場所名には、建物の番号、階数、翼棟名、部屋番号などを含めます。従業員にしかわからないような呼称は避けます。緊急対応員がわからなければ、彼らは正しい場所に行くことができません。

  - Lync クライアントが適切な場所を取得したことをユーザーが簡単に確認できる場所識別子。 Lync クライアントは、[検出された**場所**] フィールドと [**市区町村**] フィールドを自動的に連結し、ヘッダーに表示します。 適切な方法としては、建物の番地を各場所の識別子 (たとえば、"第1階\<町村番号\>" など) に追加することをお勧めします。 番地がないと、「1 階」のような一般的な場所 ID は、市内のすべての建物に該当します。

  - 場所がワイヤレス アクセス ポイントで決定されるために近似値となる場合は、「Near」という単語を追加することができます (たとえば、「Near 1 階 1234」など)。

</div>

<div>

## <a name="planning-elins"></a>ELIN の計画

建物のスペースをどのように場所に区切るかを決めたら、いくつの ELIN を各場所に割り当てるかを決める必要があります。たとえば、階数やテナント数が多い建物では建物内のエリアごとに別の緊急ゾーンが割り当てられる場合があります。一般的には建物の 1 つの階を 1 つの場所として指定し、さらに 1 つの場所に 1 つ以上の ELIN を割り当てます。ELIN は緊急通報の際に呼び出し元番号として使用されます。ELIN に使用できる電話番号については、各自の PSTN 通信業者にお問い合わせください。次の表には、1 つの住所に含まれる複数の場所の例を示します。

### <a name="sample-location-and-elin-assignments"></a>場所と ELIN の割り当てのサンプル

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>建物内のエリア</th>
<th>場所</th>
<th>ELIN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 階</p></td>
<td><p>1</p></td>
<td><p>425-555-0100</p></td>
</tr>
<tr class="even">
<td><p>2 階</p></td>
<td><p>2</p></td>
<td><p>425-555-0111</p></td>
</tr>
<tr class="odd">
<td><p>3 階</p></td>
<td><p>3</p></td>
<td><p>425-555-0123</p></td>
</tr>
</tbody>
</table>


定義する場所は次の要件を満たすことが推奨されます。

  - 場所ごとのエリアの最大の広さ、および番地ごとの場所の個数について、自治体、および国または地域の規制に準拠していること。

  - 緊急通報をした人の場所が簡単にわかるように、十分に具体的であること。

</div>

</div>

<div>

## <a name="populating-the-location-database"></a>場所データベースの設定

場所データベースへのデータの取り込み方法を決める際は、以下の点を考慮してください。

  - **場所データベースにデータを取り込むためにどんなプロセスを使用するのか。**  
    データがどこに存在し、そのデータを場所データベースで要求される形式に変換するためにどのようなステップを実行する必要があるのか考慮してください。また、場所を個別に追加するのか、または CSV ファイルを使用して一括追加するのか検討してください。

<!-- end list -->

  - **場所のマッピング情報が既に格納されているサードパーティのデータベースを定義するのか。**  
    Lync Server の [Secondary Location Information service] オプションを使ってサードパーティのデータベースに接続すると、オフラインプラットフォームを使用して場所をグループ化して管理できます。 この方法の利点は、場所をネットワーク ID に関連付けることに加えて、場所をユーザーに関連付けられることです。 つまり、位置情報サービスは、セカンダリの場所情報サービスからの複数のアドレスを Lync Server クライアントに返すことができます。 その後、ユーザーは最適な場所を選択できます。
    
    位置情報サービスと統合するには、サードパーティのデータベースが Lync Server の場所要求/応答スキーマに従う必要があります。 詳細について<http://go.microsoft.com/fwlink/p/?linkid=213819>は、を参照してください。 セカンダリ位置情報サービスの展開の詳細については、展開ドキュメントの「 [Lync Server 2013 でセカンダリ場所情報サービスを構成](lync-server-2013-configure-a-secondary-location-information-service.md)する」を参照してください。

場所データベースの設定の詳細については、展開ドキュメントの「 [Lync Server 2013 で場所データベースを構成する](lync-server-2013-configure-the-location-database.md)」を参照してください。

</div>

<div>

## <a name="maintaining-the-location-database"></a>場所データベースの管理

場所データベースにデータを取り込んだ後は、ネットワーク構成の変更に伴ってデータベースを更新するための手段を講じる必要があります。以下の質問は、場所データベースを管理する方法を決めるのに役立ちます。

  - **場所データベースをどのような方法で更新するのか。**  
    場所データベースの更新が必要になる場合としては、ワイヤレス アクセス ポイント (WAP) の追加、オフィスでの再配線 (別のスイッチ割り当てに変更)、サブネットの拡張など、いくつかのシナリオが考えられます。個々の場所を直接更新するのか、または CSV ファイルを使用してすべての場所の一括更新を実行するのか考慮してください。

<!-- end list -->

  - **SNMP アプリケーションを使用して、Lync クライアントの MAC アドレスをポートおよびスイッチ ID と照合するのか。**  
    SNMP アプリケーションを使用する場合は、SNMP アプリケーションと場所データベースの間でスイッチ シャーシおよびポート情報の整合性を維持するための手動のプロセスを作成する必要があります。 SNMP アプリケーションが、データベースに含まれていないシャーシの IP アドレスまたはポート ID を返す場合、位置情報サービスは位置情報をクライアントに返すことができません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

