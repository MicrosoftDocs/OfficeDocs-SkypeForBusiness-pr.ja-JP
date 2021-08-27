---
title: クラウド通話キューを計画する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: 2019 年にクラウド自動応答を使用するSkype for Business Server。
ms.openlocfilehash: 1dffa2e0b92f9888fc9b24323c7fa638468c8b1b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578171"
---
# <a name="plan-cloud-call-queues"></a>クラウド通話キューの計画

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

クラウド通話キューは、顧客の呼び出しを受け入れ、案内応答メッセージを再生し、これらの呼び出しに応答するために事前に構成されたエージェントのリストを検索しながら、これらの呼び出しを待機キューに入れるサービスです。 メールが有効な配布リストまたはセキュリティ グループでエージェントのセットを定義できます。 組織には、1 つ以上の呼び出しキューを設定できます。 通話キューは、通常、自動応答と組み合わせて使用されます。

さらに、クラウド通話キューは次の機能を提供できます。

- 発信者が保留を待っている間の音楽
- 通話キューの最大サイズ、タイムアウト、通話処理オプションのカスタマイズされた設定

各通話キューには、Skype for Business Server 2019 システムのリソース アカウント **(「** リソース アカウントの構成」を [参照)](configure-onprem-ra.md)が割り当てられます。このアカウントは、Microsoft Teams 管理センターの通話キューに直接リンクされます。 通話 [キューの種類と](/MicrosoftTeams/create-a-phone-system-call-queue) 、通話キューに存在するオプションと機能の詳細については、「Create a Cloud call queue」を参照してください。

> [!NOTE]
> 複数の電話番号を通話キューに割り当てできますが、Microsoft サービス番号、ダイレクト ルーティング番号、またはハイブリッド番号である必要があります。

## <a name="requirements"></a>要件

次の要件では、サポートされているトポロジSkype for Business Server 2019 を既に展開していることを前提とします。  要件はシナリオによって異なります。

- クラウド通話キューの新しい構成については、「リソース アカウントの構成」で説明されている [手順に従います](configure-onprem-ra.md)。 2019 年 2019 年にオンラインまたは Skype for Business Server でリソース アカウントを作成する必要があります。また、電話番号を通話キューに関連付ける必要がある場合があります。

上記の要件に加えて、Microsoft Cloud 通話キュー サービスに接続するように以下の要件を構成する必要があります。

- ハイブリッド接続。 Skype for Business Serverが既に展開済みで、オンプレミスユーザーに対してクラウド通話キューを有効にする場合は、オンプレミス環境とオンライン環境の間にハイブリッド接続がセットアップされている必要があります。 これは、分割ドメイン構成と呼ばれる場合があります。

   詳細については、「Skype for Business Server と Microsoft 365 または Office 365 のハイブリッド接続を計画する」および[「Skype for Business Server](plan-hybrid-connectivity.md)と Microsoft 365 または Office 365 のハイブリッド接続を構成する」[を参照してください](configure-hybrid-connectivity.md)。

- 電話番号をリソース アカウントに割り当てる場合は、無料の仮想ユーザー ライセンス電話システム使用できます。 これにより、組織電話システム電話番号に対応する機能を提供し、自動応答機能と通話キュー機能を作成できます。

- 各通話キューのオンプレミス [リソース アカウント](configure-onprem-ra.md) を作成し、必要に応じてライセンスと電話番号を割り当てる。  

ニーズを満たす堅実な構造と、顧客を効率的に導くスクリプトがある場合は、「リソース アカウントの構成」に  [進んでください](configure-onprem-ra.md)。

## <a name="see-also"></a>関連項目

[リソース アカウントの構成](configure-onprem-ra.md)

[電話ユーザー インターフェイスでカスタム プロンプト録音を有効にする](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[クラウドの自動応答とは](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Skype for Business Server と Microsoft 365 または Office 365 の間のハイブリッド接続を計画する](plan-hybrid-connectivity.md)

[ハイブリッド接続を構成するには、Skype for Business ServerとMicrosoft 365またはOffice 365](configure-hybrid-connectivity.md)

[Microsoft Teams のリソースのアカウントの管理](/MicrosoftTeams/manage-resource-accounts)