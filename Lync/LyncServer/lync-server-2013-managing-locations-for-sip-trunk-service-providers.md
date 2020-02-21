---
title: 'Lync Server 2013: SIP トランクサービスプロバイダーの場所の管理'
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
ms.openlocfilehash: f27eeac11006eab2209bb5491d991a677e3a2887
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a>Lync Server 2013 での SIP トランクサービスプロバイダーの場所の管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

ネットワーク内のクライアントを自動的に検索するように Lync Server を構成するには、場所情報サービスデータベースにネットワークのワイヤマップを設定し、場所を公開するか、または既に正しい内容が含まれている外部データベースにリンクする必要があります。関連付け. このプロセスの一環として、E9-1-1 サービスのサービス プロバイダーで場所の公的アドレスを確認する必要があります。 詳細については、「展開」のドキュメントの「 [Configure the location database In Lync Server 2013](lync-server-2013-configure-the-location-database.md) 」を参照してください。

場所情報サービス データベースに、公的アドレスと建物内の特定のアドレスで構成される緊急応答ロケーション (ERL) を取り込みます。 場所情報サービスの**場所**フィールド (建物内の特定の場所) の最大長は20文字 (スペースを含む) です。 この制限された長さの中に、以下を含めるようにします。

  - 緊急対応員が公的アドレスにたどり着いたときに特定の場所をすぐに特定するように、緊急電話の発信者の場所を特定するわかりやすい名前。この場所名には建物番号、階数、ウイング名、部屋番号などを含めることができます。従業員にしかわからないニックネームは避けてください。そのようなニックネームになっていると、緊急対応員が間違った場所へ行ってしまう可能性があります。

  - Lync クライアントが正しい場所を取得したことを、ユーザーが簡単に判別するのに役立つ場所の ID。 Lync クライアントは、検出したヘッダ内の [**Location**] フィールドと [**City**] フィールドを自動的に連結し、表示します。 建物の番地を各場所の識別子 (たとえば、"1 階\<のストリート番号\>") に追加することをお勧めします。 番地がないと、「1 階」のような一般的な場所 ID は、市内のすべての建物に該当します。

  - 場所がワイヤレス アクセス ポイントで決定されるために近似となる場合、「Near」という単語を追加することができます。たとえば、「Near 1 階 1234」です。

<div>


> [!NOTE]  
> 中央の場所のデータベースに追加された場所は、Lync Server 管理シェルコマンドを使用して発行され、プールのローカルストアにレプリケートされるまでクライアントで使用できません。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-publish-the-location-database.md">Lync Server 2013 からの場所データベースの発行</A>」を参照してください。



</div>

以降のセクションでは、場所データベースへのデータの取り込みおよび管理で考慮する必要がある事項について検討します。

<div>

## <a name="populating-the-location-database"></a>場所データベースの設定

以下の質問は、場所データベースにデータを取り込む方法を決めるのに役立ちます。

  - **場所データベースにデータを取り込むためにどんなプロセスを使用するのか。**  
    データがどこに存在し、そのデータを場所データベースで要求される形式に変換するためにどのようなステップを実行する必要があるのか考慮してください。また、場所を個別に追加するのか、または CSV ファイルを使用して一括追加するのか検討してください。

<!-- end list -->

  - **場所のマッピング情報がすでに格納されているサードパーティのデータベースを定義するのか。**  
    Lync Server のセカンダリの場所情報サービスオプションを使用してサードパーティのデータベースに接続することにより、オフラインプラットフォームを使用して場所をグループ化および管理できます。 この方法の利点は、場所をネットワーク ID に関連付けることに加えて、場所をユーザーに関連付けられることです。 これは、場所情報サービスが、セカンダリ場所情報サービスから Lync Server クライアントに送信された複数のアドレスを返すことができることを意味します。 その後、ユーザーは最適な場所を選択できます。
    
    場所情報サービスと統合するには、サードパーティのデータベースが Lync Server の場所の要求/応答スキーマに従う必要があります。 詳細については\[、「Ms-e911ws\]: Web Service For E911 Support Protocol Specification」を<https://go.microsoft.com/fwlink/p/?linkid=213819>参照してください。 セカンダリ場所情報サービスの展開の詳細については、「展開」のドキュメントの「 [Configure a Secondary Location information service In Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) 」を参照してください。

場所データベースの設定の詳細については、「展開」のドキュメントの「 [Configure the location database In Lync Server 2013](lync-server-2013-configure-the-location-database.md) 」を参照してください。

</div>

<div>

## <a name="maintaining-the-location-database"></a>場所データベースの管理

場所データベースにデータを取り込んだ後は、ネットワーク構成の変更に伴ってデータベースを更新するための手段を講じる必要があります。以下の質問は、場所データベースを管理する方法を決めるのに役立ちます。

  - **場所データベースをどのような方法で更新するのか。**  
    場所データベースの更新が必要になる場合としては、WAP の追加、オフィスでの再配線 (別のスイッチ割り当てに変更)、サブネットの拡張など、いくつかのシナリオが考えられます。個々の場所を直接更新するのか、または CSV ファイルを使用してすべての場所の一括更新を実行するのか考慮してください。

<!-- end list -->

  - **SNMP アプリケーションを使用して、Lync クライアントの MAC アドレスをポートおよびスイッチ ID と照合するのか。**  
    SNMP アプリケーションを使用する場合は、SNMP アプリケーションと場所データベースの間でスイッチ シャーシおよびポート情報の整合性を維持するための手動のプロセスを作成する必要があります。 SNMP アプリケーションがデータベースに含まれていないシャーシの IP アドレスまたはポート ID を返した場合、Location Information service はクライアントに場所を返すことができません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

