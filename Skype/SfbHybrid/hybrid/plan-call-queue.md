---
title: Cloud call queue を計画する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Skype for Business Server 2019 でのクラウド自動応答の使用の概要。
ms.openlocfilehash: 2186909b3ec905d6ec6d387bcea172d8fb80287c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221307"
---
# <a name="plan-cloud-call-queues"></a>クラウド通話キューを計画する

Cloud call queue は、顧客からの通話を受け付け、案内応答メッセージを再生した後、これらの呼び出しを待機キューに格納し、これらの呼び出しに応答するために事前に構成されたエージェントの一覧を検索するサービスです。 メールが有効な配布リストまたはセキュリティグループでは、一連のエージェントを定義できます。 組織は、1つまたは複数の通話キューを持つことができます。 通常、通話キューは自動応答と組み合わせて使用されます。

さらに、クラウド通話キューは次の機能を提供します。

- 発信者が保留状態になっているときの音楽
- 呼び出しキューの最大サイズ、タイムアウト、および通話処理オプションのカスタマイズされた設定

各呼び出しキューには、Skype for Business Server 2019 システムの**リソースアカウント**(「リソースアカウントの[構成](configure-onprem-ra.md)」を参照) が割り当てられています。これは、Microsoft Teams 管理センターの通話キューに直接リンクされます。 呼び出しキューの詳細については「 [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) 」と、通話キューに存在するオプションと機能を参照してください。

> [!NOTE]
> 複数の電話番号を通話キューに割り当てることができますが、それらは Microsoft サービス番号、直接ルーティング番号、またはハイブリッド番号である必要があります。

## <a name="requirements"></a>要件

次の要件は、サポートされているトポロジで Skype for Business Server 2019 が既に展開されていることを前提としています。  要件は、シナリオによって異なります。

- クラウド通話キューの新しい構成については、「 [Configure resource accounts](configure-onprem-ra.md)」に記載されている手順に従ってください。 リソースアカウントは、オンラインまたは Skype for Business Server 2019 で作成する必要があります。また、電話番号を通話キューに関連付ける必要がある場合もあります。

上記の要件に加えて、次の要件を構成して、Microsoft Cloud call queue service に接続する必要があります。

- ハイブリッド接続。 Skype for Business Server を既に展開しており、オンプレミスのユーザーのためにクラウドコールキューを有効にする場合は、オンプレミスの環境とオンライン環境の間でハイブリッド接続が設定されていることを確認する必要があります。 これは、分割ドメイン構成と呼ばれることがあります。

   詳細については、「skype [for Business server と microsoft 365 または office 365 の間のハイブリッド接続を計画](plan-hybrid-connectivity.md)する」および「 [Skype for Business server と microsoft 365 または office 365 間のハイブリッド接続を構成する](configure-hybrid-connectivity.md)」を参照してください。

- リソースアカウントに電話番号を割り当てる場合は、費用がかからない電話システムの仮想ユーザーライセンスを使用できるようになります。 これにより、組織レベルで電話番号に電話システム機能が提供され、自動応答と通話キュー機能を作成できるようになります。

- 各呼び出しキューに対してオンプレミスの[リソースアカウント](configure-onprem-ra.md)を作成し、必要に応じてライセンスと電話番号を割り当てます。  

## <a name="additional-planning-resources"></a>その他の計画に関するリソース

「 [Small business の例-自動応答の設定](/microsoftteams/tutorial-org-aa)」というタイトルのチュートリアルでは、ユーザーのニーズに関する情報の収集、自動応答とユーザーの構成 (および場合によっては呼び出しキュー) の計画、メニュープロンプトの作成、オンライン管理センターでのプランの実装を行います。 チュートリアルを確認し、演習を使用してプランを作成します。

お客様のニーズを満たす堅固な構造を持っていて、顧客に効率的に対応するスクリプトを実行している場合は、「[リソースアカウントを構成](configure-onprem-ra.md)する」に進みます。

## <a name="see-also"></a>関連項目

[リソースアカウントを構成する](configure-onprem-ra.md)

[電話ユーザー インターフェイスでカスタム プロンプト録音を有効にする](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[クラウドの自動応答とは](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を計画する](plan-hybrid-connectivity.md)

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する](configure-hybrid-connectivity.md)

[Microsoft Teams のリソースのアカウントの管理](/MicrosoftTeams/manage-resource-accounts)
