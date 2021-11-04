---
title: ELIN ゲートウェイの場所を管理Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: ELIN ゲートウェイを使用した E9-1-1 展開の場所情報データベースまたは類似の外部データベースを計画するために必要なSkype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: f8440e4e125773e91850b890bb2a02c7d1312fde
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756524"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>ELIN ゲートウェイの場所を管理Skype for Business Server

ELIN ゲートウェイを使用した E9-1-1 展開の場所情報データベースまたは類似の外部データベースを計画するために必要なSkype for Business Server エンタープライズ VoIP。

ネットワーク内Skype for Business Serverの場所を自動的に指定するには、次のタスクを実行する必要があります。

- 場所情報サービス データベースにネットワーク ワイヤーマップを設定し、[CompanyName] フィールドに緊急位置情報識別番号 (ELIN) を含める。

- 場所を、ネットワーク内のクライアントが利用できるように公開します。

- ELIN を、公衆交換電話網 (PSTN) 通信業者の自動ロケーション識別 (ALI) データベースにアップロードします。

これらのタスクを実行する方法の詳細については、「展開」のドキュメントの「[Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database)」を参照してください。

> [!NOTE]
> 中央の場所データベースに追加された場所は、Skype for Business Server 管理シェル コマンドを使用して発行され、プールのローカル ストアにレプリケートされるまで、クライアントが使用できません。 詳細については、「展開」のドキュメントの「[Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database)」を参照してください。

このセクションでは、場所データベースの更新および保守の計画を立てるときに考慮する必要のある事項を説明します。

## <a name="planning-emergency-locations"></a>緊急位置の計画

ELIN ゲートウェイを使用する場合は、場所情報サービス データベースに、市民アドレス、建物内の特定の場所、および場所ごとに少なくとも 1 つの ELIN を設定します。 計画段階で、場所にどのように名前を付けるのか、どのように ELIN を割り当てるのかを決定しておくことをお勧めします。

### <a name="planning-location-names"></a>場所名の計画

建物内の特定 **の** 場所を保持する [位置情報サービスの場所] フィールドの最大長は 20 文字 (スペースを含む) です。 この制限された長さの中に、以下を含めるようにします。

- 緊急対応員が特定の住所に到着したときに緊急通報をした人の場所がすぐにわかるように、場所を具体的に特定するわかりやすい名前。この場所名には、建物の番号、階数、翼棟名、部屋番号などを含めます。従業員にしかわからないような呼称は避けます。緊急対応員がわからなければ、彼らは正しい場所に行くことができません。

- ユーザーがクライアントが正しい場所を選んだのを簡単に確認するのに役立つ場所識別子。 クライアントSkype for Business、検出された Location フィールドと **City** フィールドをヘッダーに自動的に連結して表示します。 建物の住所を各場所識別子 (たとえば"1st Floor") に追加する方法をお使 <street number> いください。 番地がないと、「1 階」のような一般的な場所 ID は、市内のすべての建物に該当します。

- 場所がワイヤレス アクセス ポイントによって決まるので近似値の場合は **、[Near]** という単語を追加できます (たとえば、「Near 1st Floor 1234」)。

### <a name="planning-elins"></a>ELIN の計画

建物のスペースをどのように場所に区切るかを決めたら、いくつの ELIN を各場所に割り当てるかを決める必要があります。たとえば、階数やテナント数が多い建物では建物内のエリアごとに別の緊急ゾーンが割り当てられる場合があります。一般的には建物の 1 つの階を 1 つの場所として指定し、さらに 1 つの場所に 1 つ以上の ELIN を割り当てます。ELIN は緊急通報の際に呼び出し元番号として使用されます。ELIN に使用できる電話番号については、各自の PSTN 通信業者にお問い合わせください。次の表には、1 つの住所に含まれる複数の場所の例を示します。

**場所と ELIN の割り当てのサンプル**

|**建物内のエリア**|**Location**|**ELIN**|
|:-----|:-----|:-----|
|1 階  <br/> |1  <br/> |425-555-0100  <br/> |
|2 階  <br/> |2  <br/> |425-555-0111  <br/> |
|3 階  <br/> |3  <br/> |425-555-0123  <br/> |

定義する場所は次の要件を満たすことが推奨されます。

- 場所ごとのエリアの最大の広さ、および番地ごとの場所の個数について、自治体、および国または地域の規制に準拠していること。

- 緊急通報をした人の場所が簡単にわかるように、十分に具体的であること。

## <a name="populating-the-location-database"></a>場所データベースの設定

場所データベースへのデータの取り込み方法を決める際は、以下の点を考慮してください。

 **場所データベースにデータを取り込むためにどんなプロセスを使用するのか。**

データがどこに存在し、そのデータを場所データベースで要求される形式に変換するためにどのようなステップを実行する必要があるのか考慮してください。また、場所を個別に追加するのか、または CSV ファイルを使用して一括追加するのか検討してください。

 **場所のマッピング情報がすでに格納されているサードパーティのデータベースを定義するのか。**

[セカンダリ位置情報サービス] オプションを使用してサードパーティ データベースに接続すると、オフライン プラットフォームを使用して場所をグループ化および管理できます。 この方法の利点は、場所をネットワーク ID に関連付けることに加えて、場所をユーザーに関連付けられることです。 つまり、位置情報サービスは、セカンダリ 位置情報サービスから発信された複数のアドレスを、特定のクライアントにSkype for Businessできます。 その後、ユーザーは最適な場所を選択できます。

位置情報サービスと統合するには、サード パーティのデータベースが場所要求/応答スキーマSkype for Business Serverに従う必要があります。 詳細については [、「Web サービス for E911 サポート プロトコル」を参照してください](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd)。 セカンダリ位置情報サービスの展開の詳細については、「[展開」の](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md)ドキュメントの「セカンダリ位置情報サービスを構成する」Skype for Business Serverを参照してください。

場所データベースへのデータの取り込みの詳細については、「展開」のドキュメントの「[Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database)」を参照してください。

## <a name="maintaining-the-location-database"></a>場所データベースの管理

場所データベースにデータを取り込んだ後は、ネットワーク構成の変更に伴ってデータベースを更新するための手段を講じる必要があります。以下の質問は、場所データベースを管理する方法を決めるのに役立ちます。

 **場所データベースをどのような方法で更新するのか。**

場所データベースの更新が必要になる場合としては、ワイヤレス アクセス ポイント (WAP) の追加、オフィスでの再配線 (別のスイッチ割り当てに変更)、サブネットの拡張など、いくつかのシナリオが考えられます。個々の場所を直接更新するのか、または CSV ファイルを使用してすべての場所の一括更新を実行するのか考慮してください。

 **SNMP アプリケーションを使用して、クライアントの MAC Skype for Businessをポートと切り替え識別子に一致しますか?**

SNMP アプリケーションを使用する場合は、SNMP アプリケーションと場所データベースの間でスイッチ シャーシおよびポート情報の整合性を維持するための手動のプロセスを作成する必要があります。 SNMP アプリケーションがデータベースに含まれていないシャーシ IP アドレスまたはポート ID を返す場合、場所情報サービスはクライアントに場所を返す事ができません。