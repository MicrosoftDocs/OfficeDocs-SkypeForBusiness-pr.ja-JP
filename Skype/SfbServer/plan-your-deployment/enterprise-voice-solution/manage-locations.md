---
title: Skype for Business Server の SIP トランク サービス プロバイダーの場所を管理する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Skype for Business Server エンタープライズ VoIP で、SIP トランキング プロバイダーを使用した E9-1-1 展開の場所情報データベースまたは同様の外部データベースを計画するために必要な決定。
ms.openlocfilehash: b175c2cc3d0ed02a124a365787c8cb5d7cd37d10
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101443"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Skype for Business Server の SIP トランク サービス プロバイダーの場所を管理する

Skype for Business Server エンタープライズ VoIP で、SIP トランキング プロバイダーを使用した E9-1-1 展開の場所情報データベースまたは同様の外部データベースを計画するために必要な決定。

ネットワーク内のクライアントを自動的に検索する Skype for Business Server を構成するには、場所情報サービス データベースにネットワーク ワイヤーマップを設定して場所を公開するか、または正しいマッピングが既に含まれている外部データベースへのリンクを作成する必要があります。 このプロセスの一環として、E9-1-1 サービスのサービス プロバイダーで場所の公的アドレスを確認する必要があります。 詳細については、「展開」のドキュメントの「[Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database)」を参照してください。

場所情報サービス データベースに、公的アドレスと建物内の特定のアドレスで構成される緊急応答ロケーション (ERL) を取り込みます。 建物内の特定 **の** 場所である [位置情報サービスの場所] フィールドの最大長は 20 文字 (スペースを含む) です。 この制限された長さの中に、以下を含めるようにします。

- 緊急対応員が公的アドレスにたどり着いたときに特定の場所をすぐに特定するように、緊急電話の発信者の場所を特定するわかりやすい名前。この場所名には建物番号、階数、ウイング名、部屋番号などを含めることができます。従業員にしかわからないニックネームは避けてください。そのようなニックネームになっていると、緊急対応員が間違った場所へ行ってしまう可能性があります。

- ユーザーが Skype for Business クライアントが正しい場所を選んだのをユーザーが簡単に確認するのに役立つ場所識別子。 Skype for Business クライアントは、検出された Locationフィールドと **City** フィールドをヘッダーに自動的に連結して表示します。 建物の住所を各場所識別子 (たとえば"1st Floor") に追加する方法をお使 <street number> いください。 番地がないと、「1 階」のような一般的な場所 ID は、市内のすべての建物に該当します。

- 場所がワイヤレス アクセス ポイントによって決まるので近似値の場合は **、[Near]** という単語を追加できます (たとえば、「Near 1st Floor 1234」)。

> [!NOTE]
> 中央の場所データベースに追加された場所は、Skype for Business Server 管理シェル コマンドを使用して発行され、プールのローカル ストアにレプリケートされるまで、クライアントが使用できません。 詳細については、「展開」のドキュメントの「[Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database)」を参照してください。

以降のセクションでは、場所データベースへのデータの取り込みおよび管理で考慮する必要がある事項について検討します。

## <a name="populating-the-location-database"></a>場所データベースの設定

以下の質問は、場所データベースにデータを取り込む方法を決めるのに役立ちます。

 **場所データベースにデータを取り込むためにどんなプロセスを使用するのか。**

データがどこに存在し、そのデータを場所データベースで要求される形式に変換するためにどのようなステップを実行する必要があるのか考慮してください。また、場所を個別に追加するのか、または CSV ファイルを使用して一括追加するのか検討してください。

 **場所のマッピング情報がすでに格納されているサードパーティのデータベースを定義するのか。**

[セカンダリ位置情報サービス] オプションを使用してサードパーティ データベースに接続すると、オフライン プラットフォームを使用して場所をグループ化および管理できます。 この方法の利点は、場所をネットワーク ID に関連付けることに加えて、場所をユーザーに関連付けられることです。 つまり、位置情報サービスは、セカンダリ 位置情報サービスから Skype for Business クライアントに複数のアドレスを返す可能性があります。 その後、ユーザーは最適な場所を選択できます。

位置情報サービスと統合するには、サード パーティのデータベースが Lync Server の場所要求/応答スキーマに従う必要があります。 詳細については  [、「[MS-E911WS]: E911](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd)サポート プロトコル仕様の Web サービス」を参照してください。 セカンダリ位置情報サービスの展開の詳細については、「展開」のドキュメントの [「Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) でセカンダリ位置情報サービスを構成する」を参照してください。

場所データベースへのデータの取り込みの詳細については、「展開」のドキュメントの「[Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database)」を参照してください。

## <a name="maintaining-the-location-database"></a>場所データベースの管理

場所データベースにデータを取り込んだ後は、ネットワーク構成の変更に伴ってデータベースを更新するための手段を講じる必要があります。以下の質問は、場所データベースを管理する方法を決めるのに役立ちます。

 **場所データベースをどのような方法で更新するのか。**

場所データベースの更新が必要になる場合としては、WAP の追加、オフィスでの再配線 (別のスイッチ割り当てに変更)、サブネットの拡張など、いくつかのシナリオが考えられます。個々の場所を直接更新するのか、または CSV ファイルを使用してすべての場所の一括更新を実行するのか考慮してください。

 **SNMP アプリケーションを使用して、Lync クライアントの MAC アドレスをポートおよびスイッチ ID と照合するのか。**

SNMP アプリケーションを使用する場合は、SNMP アプリケーションと場所データベースの間でスイッチ シャーシおよびポート情報の整合性を維持するための手動のプロセスを作成する必要があります。 SNMP アプリケーションがデータベースに含まれていないシャーシ IP アドレスまたはポート ID を返す場合、場所情報サービスはクライアントに場所を返す事ができません。