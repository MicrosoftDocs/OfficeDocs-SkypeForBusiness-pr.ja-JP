---
title: Microsoft Teams 電話 システム リソース アカウントを設定する
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 自動応答で使用するMicrosoft Teams 電話システム リソース アカウントを設定する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7764d6b7f7d09cd2c5065ab24e73cb0fdec9c5c6
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556548"
---
# <a name="step-4-set-up-a-teams-phone-system-resource-account"></a>手順 4: Teams 電話システム リソース アカウントを設定する

リソース アカウントは、特定のユーザーには割り当てられません。 代わりに、無料の仮想ユーザー ライセンスを使用するリソース アカウントは、Microsoft 365のデバイスとサービスによって使用されます。 Microsoft Teamsでは、リソース アカウントに電話番号が割り当てられ、自動応答と通話キューに関連付けられます。

リソース アカウントを自動応答と通話キューに関連付けることで、1 つ以上の有料電話番号またはフリーダイヤル電話番号を追加できます。 たとえば、1 つのリソース アカウントと有料電話番号をローカル発信者の自動応答に関連付けることができます。 長距離通話の場合は、別のリソース アカウントとフリーダイヤル番号を同じ自動応答に関連付けることができます。

この記事のセクションでは、リソース アカウントを設定し、電話番号を割り当てる方法について説明します。 後で、リソース アカウントを自動応答に関連付けます。

## <a name="obtain-virtual-user-licenses"></a>仮想ユーザー ライセンスを取得する

リソース アカウントでは、自動応答と呼び出しキューを操作するためにライセンスが必要です。 *無料のMicrosoft Teams 電話 Standard - Virtual User ライセンスを* 使用できます。

> [!NOTE]
> プランバンドルライセンスの試用期間を呼び出してTeams 電話にサインアップした場合にのみ、次の手順を実行する必要があります。 通話プランバンドル ライセンスでTeams 電話を購入した場合、仮想ライセンスは既にアカウントに適用されている必要があります。
>
> 仮想ライセンスが既にあるかどうかを確認するには、グローバル管理者アクセス許可を持つアカウントを使用してMicrosoft 365にログインします。 次に、[製品>請求] に移動[します。](https://admin.microsoft.com/Adminportal/Home#/subscriptions) 仮想ライセンスがある場合は、**Standard - Virtual User Microsoft Teams 電話** として表示されます。

1. Microsoft 365 管理センターを開き、グローバル管理者であるユーザーでログインします。これは通常、Microsoft 365にサインアップするために使用したアカウントです。
2. 左側のナビゲーション ウィンドウで、<a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**BillingPurchase** > </a> **servicesAdd-onsSee** >  >  **すべてのアドオン製品に** 移動します。
3. 最後までスクロールして **、Microsoft Teams 電話 Standard – Virtual User ライセンスを** 見つけます。 **[詳細**]、[**購入**] の順に選択します。
4. [ライセンスの購入] ページで、必要な仮想ユーザー ライセンスの数を選択します。 設定する自動応答と通話キューごとに 1 つの仮想ライセンスが必要です。 今後、より多くの自動応答を簡単に設定し、すぐにライセンスを購入しなくてもキューを呼び出すことができるように、少なくとも 5 つのライセンスを選択することをお勧めします。
5. [ **ライセンスのないすべてのユーザーに自動的に割り当てる**] チェック ボックスをオフにします。
6. [ **今すぐチェックアウト]** を選択します。
7. 注文を確認し、[ **次へ**] を選択して、[注文] を **選択** します。

> [!NOTE]
> ライセンスのコストが 0 であっても、ライセンスを  **購入** する必要があることに注意してください。

## <a name="create-a-resource-account"></a>リソース アカウントを作成する

*Microsoft Teams 電話 Standard - Virtual User* ライセンスを受け取ったら、リソース アカウントを作成できます。

1. Microsoft Teams管理センターを開き、グローバル管理者であるユーザー (通常はMicrosoft 365にサインアップするために使用したアカウント) でログインします。
2. 左側のナビゲーション ウィンドウで、<a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**VoiceResource** >  アカウント</a>に移動します。
3. **[追加]** を選択します。
4. [ **リソース アカウントの追加]** ウィンドウで、[ **表示名**]、[ **ユーザー名**] の順に入力します。 "メイン ライン自動応答" などのわかりやすい表示名を選択して、リソース アカウントの目的を説明します。
5. **リソース アカウントの種類** で、[**自動応答**] を選択します。
6. **[保存]** を選択します。

## <a name="assign-a-license"></a>ライセンスを割り当てる

リソース アカウントを作成したら、*Microsoft Teams 電話 Standard - Virtual User* ライセンスまたは *Teams 電話 Standard ライセンスを* 割り当てる必要があります。

1. Microsoft 365 管理センターを開き、グローバル管理者であるユーザーでログインします。これは通常、Microsoft 365にサインアップするために使用したアカウントです。
1. 左側のナビゲーション ウィンドウで、<a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**UsersActive ユーザー** > </a>に移動します。
1. リソース アカウントを選択します。
1. [**ライセンスとアプリ**] タブの [**ライセンス**] で、[**Standard - Virtual User] Microsoft Teams 電話選択します**。
1. [ **変更の保存] を** 選択し、[ **閉じる**] を選択します。

## <a name="assign-a-service-number"></a>サービス番号を割り当てる

![サービス番号の割り当てユーザー インターフェイスのスクリーンショット。](../media/resource-account-assign-phone-number.png)

1. Microsoft Teams管理センターを開き、グローバル管理者であるユーザー (通常はMicrosoft 365にサインアップするために使用したアカウント) でログインします。
1. 左側のナビゲーション ウィンドウで、<a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**VoiceResource** >  アカウント</a>に移動します。
1. 作成したリソース アカウントを選択し、[ **割り当て/割り当て解除**] をクリックします。
1. **[電話番号の種類**] ドロップダウンで、[**オンライン**] を選択します。
1. [ **割り当てられた電話番号** ] ボックスで、使用する番号を検索し、[ **追加**] をクリックします。 必ず国番号 ( **+1** 250 555 0012 など) を含めます。
1. **[保存]** をクリックします。

> [!div class="nextstepaction"]
> [次の手順: ユーザーに電話番号を割り当てる](set-up-assign-numbers.md)
