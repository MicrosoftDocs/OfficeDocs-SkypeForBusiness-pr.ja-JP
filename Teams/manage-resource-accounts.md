---
title: Teams のリソース アカウントを管理する
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: マイクロソフトのチームでのリソースのアカウントを管理します。
ms.openlocfilehash: 22574b2045f162353c3b1154590f3cf903721cf8
ms.sourcegitcommit: d90beb625c2d12616fb9aee39b6dd1c2d4c12947
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "30408260"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>マイクロソフトのチームでのリソースのアカウントを管理します。

リソース アカウントとも呼ばれる、一般にリソースを表すために使用できます、Azure Active Directory 内の無効なユーザー オブジェクトです。 Exchange ホスト ・ エージェントを使用するには、たとえば、会議室を表すし、電話番号を許可するようにすることがあります。 Microsoft 365 またはビジネス サーバーでは、Skype を使用して社内のリソース アカウントが所属することができ、Powershell コマンドを使用してこれらのアカウントを作成します。

マイクロソフト チームまたは Skype のオンライン ビジネス、各呼び出しキュー、または自動アテンダントに関連するリソース アカウントを持っている必要があります。 リソース アカウントに、割り当てられた電話番号が必要かどうか、関連付けられている呼び出しキューの使用目的に依存しているまたは自動アテンダントです。 呼び出しキューでの記事を参照してくださいし、自動アテンダントのリソース アカウントに電話番号を割り当てる前に、この資料の下部にあるリンクされています。

> [!NOTE]
> この資料は、オンライン ビジネスは、マイクロソフトのチームと Skype の両方に適用されます。

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>リソース アカウントに電話番号を割り当てるための前提条件

開始することに注意することが重要。
  
- 組織は、エンタープライズの E3 と**電話システム**のライセンスまたはエンタープライズ E5 のライセンス (最低) が必要です。 キュー] または [自動応答の呼び出しに割り当てられているリソース アカウントに使用する利用可能なサービス番号の番号を割り当てられている**電話システム**のユーザー ライセンスの数に影響します。 リソース アカウントを持つことができますの数は、組織に割り当てられている**電話システム**および**オーディオ会議**のライセンスの数に依存します。 ライセンスに関する詳細については、[マイクロソフトのチームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。

    > [!NOTE]
    > オンラインにいる人が、組織内への呼び出しをリダイレクトするには、エンタープライズ VoIP を有効にするし、Office 365 のプランを呼び出すことがある、**電話システム**のライセンスが必要です。 [マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)を参照してください。 エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。 たとえば、次を実行します。
  
- Office 365 のプランを呼び出す方法の詳細については、 [Office 365 のプランを呼び出す](calling-plans-for-office-365.md)を参照してください。
- 有料電話番号と**マイクロソフトのチーム管理センター**でまたは別のサービス プロバイダーからリソースのアカウントに転送する電話番号をフリー ダイヤル サービスをのみ割り当てることができます。 取得し、サービスのフリー ダイヤル番号を使用して、通信のクレジットを設定する必要があります。

> [!NOTE]
> (サブスクライバー) をユーザーの電話番号は、リソース アカウントに割り当てることができません。 サービスの有料または無料の電話番号のみを使用することができます。

リソース アカウントに電話番号を割り当てる、取得、または、既存の有料または無料のサービスに転送する必要がある数値です。 有料または無料のサービスの電話番号を取得した後表示されます**マイクロソフトのチーム管理センター**の > **音声** > **の電話番号**、および記述されている**数値型**は、**サービスのフリー ダイヤル**として一覧表示されます。 サービス番号を取得するには、[サービスの電話番号の取得](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md)を参照するか、転送し、既存のサービス番号にする場合は、 [Office 365 に電話番号を転送する](transfer-phone-numbers-to-office-365.md)を参照してください。
  
> [!NOTE]
> 米国以外のユーザーは、サービス番号を取得するマイクロソフトのチームの管理センターを使うことはできません。 [組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する代わりに、米国の外側から行う方法を参照してください。

## <a name="create-a-resource-account-in-powershell"></a>Powershell でのリソース アカウントを作成します。

 (1 つまたは複数リソース アカウント用)、必要に応じて該当する Powershell コマンドレットを実行して、リソース アカウントを作成し、名前 1 つずつというようにします。 現在、マイクロソフトのチーム管理センターで、リソース アカウントを作成するためのオプションはありませんが、電話番号を編集し、呼び出しキュー] または [自動アテンダントの割り当て、リソース アカウントを変更できます。

によってかどうか、電話番号のオンラインまたは設置型で、適切な管理者特権を持つ Powershell プロンプトに接続する必要があります。

- (番号の数字が置かれている直接ルーティングでは、OPCH、CCE) ハイブリッド実装は、社内設置型のホーム サーバーがリソース アカウントを作成するのに[新規 CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)を使用します。  
- オンラインでだけは[新しい CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)を使用してオンライン ホーム サーバーは、リソース アカウントを持っています。

リソース アカウントを作成するオンライン環境例は、次のようにします。

``` Powershell
New-CsOnlineApplicationInstance -DisplayName Node1 -SipAddress sip:node1@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
```

このコマンドの詳細については、[新規 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)を参照してください。

> [!NOTE]
> 次のセクションで説明したように、マイクロソフトのチーム管理センターを使用して電話番号を設定するのには最も簡単です。 使用することも、`Set-CsOnlineApplicationInstance`コマンドを割り当てるリソース アカウントに電話番号の最初の作成にようにします。

``` Powershell
Set-CsOnlineApplicationInstance -Identity "CN={4f6c99fe-7999-4088-ac4d-e88e0b3d3820},OU=Redmond,DC=litwareinc,DC=com" -DisplayName Node1 -LineURI tel:+14255550100
```

このコマンドの詳細については、[一連の CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlineapplicationinstance?view=skype-ps)を参照してください。

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>マイクロソフトのチーム管理センターのリソース アカウントの設定を管理します。

マイクロソフトのチーム管理センターのリソース アカウントの設定を管理する**組織全体の設定**に移動  > **リソース アカウント**、リソース アカウントの設定を変更する必要があり、[**編集**] ボタンをクリックします。 **リソース アカウントの編集**画面で、ことができますを変更します。

- アカウントの**表示名**
- キューを呼び出したり、自動アテンダント アカウントを使用します。
- アカウントに割り当てられた電話番号

終了したら、**保存**をクリックします。

## <a name="related-information"></a>関連情報

ハイブリッド ビジネス サーバーの Skype では、実装。

[クラウドの自動応答を計画します。](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[クラウドの自動応答を構成します。](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

チームまたは Skype のオンライン ビジネスの実装では。

[電話システムの自動応答とは](what-are-phone-system-auto-attendants.md)

[電話システムの自動応答をセットアップする](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[小規模企業の例では、自動応答を設定](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[電話システムの呼び出しキューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[新しい-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[新しい-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
