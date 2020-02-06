---
title: Skype for Business Server で SIP トランクサービスプロバイダーの場所を管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for Business Server Enterprise Voice で、SIP トランキングプロバイダーを使用する E9 展開用の位置情報データベースまたは類似の外部データベースの計画に必要な決定。
ms.openlocfilehash: 81ec257b30d2916bb4df2a4590b9abfc1b270375
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802727"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Skype for Business Server で SIP トランクサービスプロバイダーの場所を管理する

Skype for Business Server Enterprise Voice で、SIP トランキングプロバイダーを使用する E9 展開用の位置情報データベースまたは類似の外部データベースの計画に必要な決定。

Skype for Business Server を構成してネットワーク内でクライアントが自動的に検索されるようにするには、場所情報サービスデータベースを network wiremap と共に設定して、場所を公開するか、既に含まれている外部データベースにリンクする必要があります。適切なマッピング。 このプロセスの一環として、E9-1-1 サービスのサービス プロバイダーで場所の公的アドレスを確認する必要があります。 詳細については、「展開」のドキュメントの「[Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)」を参照してください。

場所情報サービス データベースに、公的アドレスと建物内の特定のアドレスで構成される緊急応答ロケーション (ERL) を取り込みます。 建物内の特定の場所である "位置情報サービス**の場所"** フィールドには、最大20文字 (スペースを含む) が使用されます。 この制限された長さの中に、以下を含めるようにします。

- 緊急対応員が公的アドレスにたどり着いたときに特定の場所をすぐに特定するように、緊急電話の発信者の場所を特定するわかりやすい名前。この場所名には建物番号、階数、ウイング名、部屋番号などを含めることができます。従業員にしかわからないニックネームは避けてください。そのようなニックネームになっていると、緊急対応員が間違った場所へ行ってしまう可能性があります。

- ユーザーが Skype for Business クライアントが適切な場所を選択したことを簡単に確認できる場所識別子。 Skype for Business クライアントは、自動的にそのヘッダーの [検出された**場所**] フィールドと [**市区町村**] フィールドを連結して表示します。 適切な方法は、建物の住所を各場所の識別子 (たとえば、"第1階<street number>" など) に追加することです。 番地がないと、「1 階」のような一般的な場所 ID は、市内のすべての建物に該当します。

- ワイヤレスアクセスポイントによって決定されているため、場所が概数である場合は、" **near** " (たとえば、「第1階1234」など) という単語を追加できます。

> [!NOTE]
> 中央の場所のデータベースに追加された場所は、Skype for Business Server 管理シェルコマンドを使用して公開され、プールのローカルストアにレプリケートされるまで、クライアントでは利用できません。 詳細については、「展開」のドキュメントの「[Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx)」を参照してください。

以降のセクションでは、場所データベースへのデータの取り込みおよび管理で考慮する必要がある事項について検討します。

## <a name="populating-the-location-database"></a>場所データベースの設定

以下の質問は、場所データベースにデータを取り込む方法を決めるのに役立ちます。

 **場所データベースにデータを取り込むためにどんなプロセスを使用するのか。**

データがどこに存在し、そのデータを場所データベースで要求される形式に変換するためにどのようなステップを実行する必要があるのか考慮してください。また、場所を個別に追加するのか、または CSV ファイルを使用して一括追加するのか検討してください。

 **場所のマッピング情報が既に格納されているサードパーティのデータベースを定義するのか。**

[Secondary Location Information] サービスオプションを使ってサードパーティのデータベースに接続すると、オフラインプラットフォームを使用して場所をグループ化して管理できます。 この方法の利点は、場所をネットワーク ID に関連付けることに加えて、場所をユーザーに関連付けられることです。 つまり、位置情報サービスは、セカンダリ位置情報サービスから Skype for Business クライアントに送信された複数のアドレスを返すことができます。 その後、ユーザーは最適な場所を選択できます。

位置情報サービスと統合するには、サードパーティのデータベースが Lync Server の場所要求/応答スキーマに従う必要があります。 詳細については、「 [[MS-E911WS]: E911 Support Protocol Specification の Web サービス」](https://go.microsoft.com/fwlink/p/?linkid=213819)を参照してください。 セカンダリロケーション情報サービスの展開の詳細については、展開ドキュメントの「 [Skype For Business Server でセカンダリロケーション情報サービスを設定](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md)する」を参照してください。

場所データベースへのデータの取り込みの詳細については、「展開」のドキュメントの「[Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)」を参照してください。

## <a name="maintaining-the-location-database"></a>場所データベースの管理

場所データベースにデータを取り込んだ後は、ネットワーク構成の変更に伴ってデータベースを更新するための手段を講じる必要があります。以下の質問は、場所データベースを管理する方法を決めるのに役立ちます。

 **場所データベースをどのような方法で更新するのか。**

場所データベースの更新が必要になる場合としては、WAP の追加、オフィスでの再配線 (別のスイッチ割り当てに変更)、サブネットの拡張など、いくつかのシナリオが考えられます。個々の場所を直接更新するのか、または CSV ファイルを使用してすべての場所の一括更新を実行するのか考慮してください。

 **SNMP アプリケーションを使用して、Lync クライアントの MAC アドレスをポートおよびスイッチ ID と照合するのか。**

SNMP アプリケーションを使用する場合は、SNMP アプリケーションと場所データベースの間でスイッチ シャーシおよびポート情報の整合性を維持するための手動のプロセスを作成する必要があります。 SNMP アプリケーションが、データベースに含まれていないシャーシの IP アドレスまたはポート ID を返す場合、位置情報サービスは位置情報をクライアントに返すことができません。


