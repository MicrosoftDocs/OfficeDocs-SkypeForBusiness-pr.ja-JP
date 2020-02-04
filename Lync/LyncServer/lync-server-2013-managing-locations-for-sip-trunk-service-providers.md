---
title: 'Lync Server 2013: SIP トランクサービスプロバイダーの場所を管理する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9ebc471459c8e406914f5a075d7e4cf8b69fadd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a>Lync Server 2013 で SIP トランクサービスプロバイダーの場所を管理する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

ネットワーク内でクライアントが自動的に検索されるように Lync Server を構成するには、場所情報サービスデータベースに network wiremap を設定して、場所を公開するか、既に正しいものが含まれている外部データベースにリンクする必要があります。関連付け. このプロセスの一環として、E9-1-1 サービスのサービス プロバイダーで場所の公的アドレスを確認する必要があります。 詳細については、「展開ドキュメントの[Lync Server 2013 で場所データベースを構成する](lync-server-2013-configure-the-location-database.md)」を参照してください。

場所情報サービス データベースに、公的アドレスと建物内の特定のアドレスで構成される緊急応答ロケーション (ERL) を取り込みます。 建物内の特定の場所である "位置情報サービス**の場所"** フィールドには、最大20文字 (スペースを含む) が使用されます。 この制限された長さの中に、以下を含めるようにします。

  - 緊急対応員が公的アドレスにたどり着いたときに特定の場所をすぐに特定するように、緊急電話の発信者の場所を特定するわかりやすい名前。この場所名には建物番号、階数、ウイング名、部屋番号などを含めることができます。従業員にしかわからないニックネームは避けてください。そのようなニックネームになっていると、緊急対応員が間違った場所へ行ってしまう可能性があります。

  - Lync クライアントが適切な場所を取得したことをユーザーが簡単に確認できる場所識別子。 Lync クライアントは、[検出された**場所**] フィールドと [**市区町村**] フィールドを自動的に連結し、ヘッダーに表示します。 適切な方法としては、建物の番地を各場所の識別子 (たとえば、"第1階\<町村番号\>" など) に追加することをお勧めします。 番地がないと、「1 階」のような一般的な場所 ID は、市内のすべての建物に該当します。

  - 場所がワイヤレス アクセス ポイントで決定されるために近似となる場合、「Near」という単語を追加することができます。たとえば、「Near 1 階 1234」です。

<div>


> [!NOTE]  
> 中央の場所のデータベースに追加された場所は、Lync Server 管理シェルコマンドを使用して公開され、プールのローカルストアにレプリケートされるまで、クライアントでは利用できません。 詳細については、展開ドキュメントの「 <A href="lync-server-2013-publish-the-location-database.md">Lync Server 2013 からロケーションデータベースを発行</A>する」を参照してください。



</div>

以降のセクションでは、場所データベースへのデータの取り込みおよび管理で考慮する必要がある事項について検討します。

<div>

## <a name="populating-the-location-database"></a>場所データベースの設定

以下の質問は、場所データベースにデータを取り込む方法を決めるのに役立ちます。

  - **場所データベースにデータを取り込むためにどんなプロセスを使用するのか。**  
    データがどこに存在し、そのデータを場所データベースで要求される形式に変換するためにどのようなステップを実行する必要があるのか考慮してください。また、場所を個別に追加するのか、または CSV ファイルを使用して一括追加するのか検討してください。

<!-- end list -->

  - **場所のマッピング情報が既に格納されているサードパーティのデータベースを定義するのか。**  
    Lync Server の [Secondary Location Information service] オプションを使ってサードパーティのデータベースに接続すると、オフラインプラットフォームを使用して場所をグループ化して管理できます。 この方法の利点は、場所をネットワーク ID に関連付けることに加えて、場所をユーザーに関連付けられることです。 つまり、位置情報サービスは、セカンダリの場所情報サービスからの複数のアドレスを Lync Server クライアントに返すことができます。 その後、ユーザーは最適な場所を選択できます。
    
    位置情報サービスと統合するには、サードパーティのデータベースが Lync Server の場所要求/応答スキーマに従う必要があります。 詳細については\[、「MS\]-E911WS: E911 サポートプロトコル仕様」を参照<http://go.microsoft.com/fwlink/p/?linkid=213819>してください。 セカンダリ位置情報サービスの展開の詳細については、展開ドキュメントの「 [Lync Server 2013 でセカンダリ場所情報サービスを構成](lync-server-2013-configure-a-secondary-location-information-service.md)する」を参照してください。

場所データベースの設定の詳細については、展開ドキュメントの「 [Lync Server 2013 で場所データベースを構成する](lync-server-2013-configure-the-location-database.md)」を参照してください。

</div>

<div>

## <a name="maintaining-the-location-database"></a>場所データベースの管理

場所データベースにデータを取り込んだ後は、ネットワーク構成の変更に伴ってデータベースを更新するための手段を講じる必要があります。以下の質問は、場所データベースを管理する方法を決めるのに役立ちます。

  - **場所データベースをどのような方法で更新するのか。**  
    場所データベースの更新が必要になる場合としては、WAP の追加、オフィスでの再配線 (別のスイッチ割り当てに変更)、サブネットの拡張など、いくつかのシナリオが考えられます。個々の場所を直接更新するのか、または CSV ファイルを使用してすべての場所の一括更新を実行するのか考慮してください。

<!-- end list -->

  - **SNMP アプリケーションを使用して、Lync クライアントの MAC アドレスをポートおよびスイッチ ID と照合するのか。**  
    SNMP アプリケーションを使用する場合は、SNMP アプリケーションと場所データベースの間でスイッチ シャーシおよびポート情報の整合性を維持するための手動のプロセスを作成する必要があります。 SNMP アプリケーションが、データベースに含まれていないシャーシの IP アドレスまたはポート ID を返す場合、位置情報サービスは位置情報をクライアントに返すことができません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

