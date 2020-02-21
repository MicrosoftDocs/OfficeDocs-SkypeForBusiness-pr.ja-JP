---
title: 'Lync Server 2013: ELIN ゲートウェイの場所の管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88b27e325ba8990cf239548c689d4e021397858a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a>Lync Server 2013 での ELIN ゲートウェイの場所の管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

Lync Server でネットワーク内のクライアントの場所を自動的に提供するには、次のタスクを実行する必要があります。

  - 場所情報サービスデータベースにネットワーク wiremap を設定し、緊急位置識別番号 (ELINs) を CompanyName フィールドに含めます。

  - 場所を、ネットワーク内のクライアントが利用できるように公開します。

  - ELIN を、公衆交換電話網 (PSTN) 通信業者の自動ロケーション識別 (ALI) データベースにアップロードします。

これらのタスクを実行する方法の詳細については、「展開」のドキュメントの「 [Configure the location database In Lync Server 2013](lync-server-2013-configure-the-location-database.md) 」を参照してください。

<div>


> [!NOTE]  
> 中央の場所のデータベースに追加された場所は、Lync Server 管理シェルコマンドを使用して公開され、プールのローカルストアにレプリケートされるまでクライアントで使用できません。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-publish-the-location-database.md">Lync Server 2013 からの場所データベースの発行</A>」を参照してください。



</div>

このセクションでは、場所データベースの更新および保守の計画を立てるときに考慮する必要のある事項を説明します。

<div>

## <a name="planning-emergency-locations"></a>緊急位置の計画

ELIN ゲートウェイを使用する場合は、場所情報サービスデータベースに、都市の住所、建物内の特定の場所、および場所ごとに少なくとも1つの ELIN を設定します。 計画段階で、場所にどのように名前を付けるのか、どのように ELIN を割り当てるのかを決定しておくことをお勧めします。

<div>

## <a name="planning-location-names"></a>場所名の計画

場所情報サービスの**場所**フィールドは、建物内の特定の位置を保持します。最大長は20文字 (スペースを含む) です。 この制限された長さの中に、以下を含めるようにします。

  - 緊急対応員が特定の住所に到着したときに緊急通報をした人の場所がすぐにわかるように、場所を具体的に特定するわかりやすい名前。この場所名には、建物の番号、階数、翼棟名、部屋番号などを含めます。従業員にしかわからないような呼称は避けます。緊急対応員がわからなければ、彼らは正しい場所に行くことができません。

  - Lync クライアントが正しい場所を取得したことを、ユーザーが簡単に判別するのに役立つ場所の ID。 Lync クライアントは、検出したヘッダ内の [**Location**] フィールドと [**City**] フィールドを自動的に連結し、表示します。 建物の番地を各場所の識別子 (たとえば、"1 階\<のストリート番号\>") に追加することをお勧めします。 番地がないと、「1 階」のような一般的な場所 ID は、市内のすべての建物に該当します。

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
<td><p>1-d</p></td>
<td><p>425-555-0100</p></td>
</tr>
<tr class="even">
<td><p>2 階</p></td>
<td><p>pbm-2</p></td>
<td><p>425-555-0111</p></td>
</tr>
<tr class="odd">
<td><p>3 階</p></td>
<td><p>1/3</p></td>
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

  - **場所のマッピング情報がすでに格納されているサードパーティのデータベースを定義するのか。**  
    Lync Server のセカンダリの場所情報サービスオプションを使用してサードパーティのデータベースに接続することにより、オフラインプラットフォームを使用して場所をグループ化および管理できます。 この方法の利点は、場所をネットワーク ID に関連付けることに加えて、場所をユーザーに関連付けられることです。 これは、場所情報サービスが、セカンダリ場所情報サービスから Lync Server クライアントに送信された複数のアドレスを返すことができることを意味します。 その後、ユーザーは最適な場所を選択できます。
    
    場所情報サービスと統合するには、サードパーティのデータベースが Lync Server の場所の要求/応答スキーマに従う必要があります。 詳細について<https://go.microsoft.com/fwlink/p/?linkid=213819>は、「」を参照してください。 セカンダリ場所情報サービスの展開の詳細については、「展開」のドキュメントの「 [Configure a Secondary Location information service In Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) 」を参照してください。

場所データベースの設定の詳細については、「展開」のドキュメントの「 [Configure the location database In Lync Server 2013](lync-server-2013-configure-the-location-database.md) 」を参照してください。

</div>

<div>

## <a name="maintaining-the-location-database"></a>場所データベースの管理

場所データベースにデータを取り込んだ後は、ネットワーク構成の変更に伴ってデータベースを更新するための手段を講じる必要があります。以下の質問は、場所データベースを管理する方法を決めるのに役立ちます。

  - **場所データベースをどのような方法で更新するのか。**  
    場所データベースの更新が必要になる場合としては、ワイヤレス アクセス ポイント (WAP) の追加、オフィスでの再配線 (別のスイッチ割り当てに変更)、サブネットの拡張など、いくつかのシナリオが考えられます。個々の場所を直接更新するのか、または CSV ファイルを使用してすべての場所の一括更新を実行するのか考慮してください。

<!-- end list -->

  - **SNMP アプリケーションを使用して、Lync クライアントの MAC アドレスをポートおよびスイッチ ID と照合するのか。**  
    SNMP アプリケーションを使用する場合は、SNMP アプリケーションと場所データベースの間でスイッチ シャーシおよびポート情報の整合性を維持するための手動のプロセスを作成する必要があります。 SNMP アプリケーションがデータベースに含まれていないシャーシの IP アドレスまたはポート ID を返した場合、Location Information service はクライアントに場所を返すことができません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

