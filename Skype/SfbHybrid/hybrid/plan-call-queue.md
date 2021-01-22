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
localization_priority: Normal
ms.collection: ''
description: Skype for Business Server 2019 でのクラウド自動応答の使用の概要。
ms.openlocfilehash: 629c28e752b7316a3d2e7fda0acf7f457788d6a8
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918743"
---
# <a name="plan-cloud-call-queues"></a>クラウド通話キューの計画

クラウド通話キューは、顧客の呼び出しを受け付け、案内応答メッセージを再生した後、これらの通話に応答するために事前に構成されたエージェントの一覧を検索しながら、これらの通話を待機キューに入れるサービスです。 メールが有効な配布リストまたはセキュリティ グループでエージェントのセットを定義できます。 組織は、1 つ以上の通話キューを持つ可能性があります。 通話キューは、通常、自動応答と組み合わせて使用されます。

さらに、クラウド通話キューは次の機能を提供できます。

- 発信者が保留音を待っている間の音楽
- 通話キューの最大サイズ、タイムアウト、通話処理オプションのカスタマイズされた設定

各通話キューには、Microsoft Teams 管理センターの通話キューに直接リンクされるリソース アカウント **(「** リソース アカウントの構成」を [参照)](configure-onprem-ra.md)が Skype for Business Server 2019 システムに割り当てられます。 通話 [キューの種類と、](/MicrosoftTeams/create-a-phone-system-call-queue) 通話キューのオプションと機能の詳細については、「クラウド通話キューを作成する」を参照してください。

> [!NOTE]
> 複数の電話番号を通話キューに割り当てできますが、Microsoft サービス番号、ダイレクト ルーティング番号、またはハイブリッド番号である必要があります。

## <a name="requirements"></a>要件

次の要件は、サポートされているトポロジに Skype for Business Server 2019 が既に展開済みである必要があります。  要件はシナリオによって異なります。

- クラウド通話キューの新しい構成については、「リソース アカウントの構成」で説明されている [手順に従います](configure-onprem-ra.md)。 オンラインまたは Skype for Business Server 2019 でリソース アカウントを作成する必要があります。また、電話番号を通話キューに関連付ける必要がある場合があります。

上記の要件に加えて、Microsoft Cloud 通話キュー サービスに接続するには、次の要件を構成する必要があります。

- ハイブリッド接続。 Skype for Business Server を既に展開済みで、オンプレミス ユーザーに対してクラウド通話キューを有効にする場合は、オンプレミス環境とオンライン環境の間にハイブリッド接続が設定されている必要があります。 これは、分割ドメイン構成とも呼ばれる場合があります。

   詳細については [、「Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).

- 電話番号をリソース アカウントに割り当てる場合は、無料の電話システム仮想ユーザー ライセンスを使用できます。 これにより、組織レベルの電話番号に電話システム機能が提供され、自動応答と通話キューの機能を作成できます。

- 各通話キューのオンプレミス [リソース アカウント](configure-onprem-ra.md) を作成し、必要に応じてライセンスと電話番号を割り当てる。  

ニーズを満たす構造と、顧客を効率的にガイドするスクリプトがある場合は、「リソース アカウントを構成する」に  [進んでください](configure-onprem-ra.md)。

## <a name="see-also"></a>関連項目

[リソース アカウントの構成](configure-onprem-ra.md)

[電話ユーザー インターフェイスでカスタム プロンプト録音を有効にする](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[クラウドの自動応答とは](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Skype for Business Server と Microsoft 365 または Office 365 の間のハイブリッド接続を計画する](plan-hybrid-connectivity.md)

[Skype for Business Server と Microsoft 365 または Office 365 の間のハイブリッド接続を構成する](configure-hybrid-connectivity.md)

[Microsoft Teams のリソースのアカウントの管理](/MicrosoftTeams/manage-resource-accounts)
