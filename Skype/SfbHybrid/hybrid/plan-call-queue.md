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
description: Skype for Business Server 2019 でのクラウド自動応答の使用の概要。
ms.openlocfilehash: df8013a4abc2029d585032b3d0bce810175e04f4
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615423"
---
# <a name="plan-cloud-call-queues"></a>クラウド通話キューの計画

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

クラウド呼び出しキューは、顧客の呼び出しを受け入れ、あいさつメッセージを再生し、これらの呼び出しに応答するために事前に構成されたエージェントの一覧を検索するときに、これらの呼び出しを待機キューに配置するサービスです。 メールが有効な配布リストまたはセキュリティ グループでエージェントのセットを定義できます。 組織は、1 つまたは複数の通話キューを持つことができます。 通常、通話キューは自動応答と組み合わせて使用されます。

さらに、クラウド呼び出しキューでは、次の情報を提供できます。

- 発信者が保留状態で待機している間の音楽
- 呼び出しキューの最大サイズ、タイムアウト、および呼び出し処理オプションのカスタマイズされた設定

各通話キューには、Microsoft Teams 管理センターの通話キューに直接リンクされる、Skype for Business Server 2019 システムの **リソース アカウント** ([リソース アカウントの構成](configure-onprem-ra.md)を参照) が割り当てられます。 [呼び出しキューの種類と呼び出しキュー](/MicrosoftTeams/create-a-phone-system-call-queue)に存在するオプションと機能の詳細については、「クラウド呼び出しキューの作成」を参照してください。

> [!NOTE]
> 通話キューに複数の電話番号を割り当てることができますが、Microsoft サービス番号、ダイレクト ルーティング番号、またはハイブリッド番号である必要があります。

## <a name="requirements"></a>要件

次の要件は、Skype for Business Server 2019 がサポートされているトポロジに既にデプロイされていることを前提としています。  要件は、シナリオによって異なります。

- クラウド呼び出しキューの新しい構成については、「 [リソース アカウントの構成](configure-onprem-ra.md)」で説明されている手順に従います。 リソース アカウントは、オンラインまたは 2019 Skype for Business Serverで作成する必要があります。また、電話番号を通話キューに関連付ける必要がある場合もあります。

上記の要件に加えて、Microsoft Cloud 通話キュー サービスに接続するには、次の要件を構成する必要があります。

- ハイブリッド接続。 Skype for Business Server既にデプロイ済みで、オンプレミス ユーザーのクラウド通話キューを有効にする場合は、オンプレミス環境とオンライン環境の間にハイブリッド接続が設定されていることを確認する必要があります。 これは分割ドメイン構成と呼ばれることもあります。

   詳細については、「[Skype for Business Serverと Microsoft 365 またはOffice 365間のハイブリッド接続を計画](plan-hybrid-connectivity.md)する」と「[Skype for Business Serverと Microsoft 365 またはOffice 365間のハイブリッド接続を構成](configure-hybrid-connectivity.md)する」を参照してください。

- リソース アカウントに電話番号を割り当てる場合は、コストフリー **のMicrosoft Teams 電話リソース アカウント** ライセンスを使用できるようになりました。 これにより、組織レベルの電話番号に電話システム機能が提供され、自動応答機能と通話キュー機能を作成できます。

- 通話キューごとにオンプレミス [リソース アカウント](configure-onprem-ra.md) を作成し、必要に応じてライセンスと電話番号を割り当てます。  

ニーズを満たす強固な構造と、顧客を効率的に導くスクリプトがある場合は、  [リソース アカウントの構成](configure-onprem-ra.md)に進みます。

## <a name="see-also"></a>関連項目

[リソース アカウントの構成](configure-onprem-ra.md)

[電話ユーザー インターフェイスでカスタム プロンプト録音を有効にする](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[クラウドの自動応答とは](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[クラウドの自動応答をセットアップする](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Skype for Business Server と Microsoft 365 または Office 365 の間のハイブリッド接続を計画する](plan-hybrid-connectivity.md)

[Skype for Business Serverと Microsoft 365 またはOffice 365間のハイブリッド接続を構成する](configure-hybrid-connectivity.md)

[Microsoft Teams のリソースのアカウントの管理](/MicrosoftTeams/manage-resource-accounts)