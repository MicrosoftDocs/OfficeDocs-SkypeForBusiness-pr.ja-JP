---
title: "クイック スタート ガイド: Microsoft Teams での通話プランの設定"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams で通話プランを設定するためのクイック スタート ガイドです。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: e38317132190b3035f37509d1fa7b2da5e4785c7
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2017
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>クイック スタート ガイド: Microsoft Teams での通話プランの設定
==============================================================

このガイドでは、ユーザーが Teams で通話プランを利用できるように設定する手順について説明します。

Teams の通話プランに関する 2017 年 12 月 12 日付けの発表「[Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)」(英語) をお読みください。

> [!NOTE]
> ロールアウトを成功させるため、このクイック スタート ガイドとともに、[実践的なガイダンス](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)と [FastTrack](https://aka.ms/cloudvoice) をご覧になることをお勧めします。

Skype for Business が提供する Office 365 の機能の 1 つである通話プランを追加することで、Teams で公衆交換電話網 (PSTN) を介して固定電話や携帯電話に対する通話の発信および受信を行えるようになります。

![Teams での通話](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Teams の [**通話**] タブを有効にするための前提条件
Teams の [**通話**] タブを有効にして、ユーザーが PSTN 通話の発信と受信を行えるようにするには、電話システムと通話プランの利用に向けてユーザーをプロビジョニングする必要があります。 この設定方法については、「[通話プランの設定](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)」をご覧ください。

> [!IMPORTANT]
> Teams で通話プランを設定する前に、以下の制限に注意してください。
> * **Teams では Hybrid Voice がサポートされない**: Teams では Hybrid Voice は現在サポートされていません。 Hybrid Voice をご利用のお客様は、Teams で通話を受信するためのポリシーをそのまま変更しないことをお勧めします。変更するとサービス中断の原因となる場合があります。
> * **Teams ではフェデレーション通話はサポートされない**: Teams ではフェデレーション通話 (テナント/会社間の通話) は現在サポートされていません。 フェデレーション通話は、Teams でサポートされるようになるまで、通話の設定に関係なく常に Skype for Business にルーティングされます。

## <a name="teams-interop-policy-configuration"></a>Teams の相互運用ポリシーの設定
Teams で通話を受信できるようにするには、Skype for Business [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) コマンドレットを使用して Windows PowerShell のリモート セッションを開いて、Teams に通話をリダイレクトするように Teams  の相互運用ポリシーを更新する必要があります。 Teams の相互運用ポリシーの詳細については、「[Microsoft Teams と Skype for Business の相互運用性](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)」をご覧ください。

> [!TIP]
> 必要な PowerShell コマンドレットを検索するには、[Skype for Business PowerShell コマンドレットに関するドキュメント](https://docs.microsoft.com/powershell/module/skype)で [**フィルター**] ボックスに「CsTeamsInteropPolicy」と入力します。

### <a name="default-teams-interop-policy"></a>Teams の既定の相互運用ポリシー
Teams の既定のポリシーは、Teams の展開時に既存のビジネス ワークフローが中断されることがないよう設定されています。 既定では、ユーザーへの VoIP 通話、PSTN 通話、フェデレーション通話は、ポリシーを更新して Teams への着信通話を有効にするまで、Skype for Business にルーティングされます。 このメカニズムにより、Teams のパイロットや展開を開始したときに発生する可能性のある意図しない中断が回避されます。

Teams の相互運用ポリシーでは次の既定の設定が指定されています。

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

既定の設定の動作を次に示します。
* **Skype for Business をすでに利用しているお客様の場合**、このポリシーは Skype for Business の通話を Skype for Business に移動させ、Teams の通話を Teams に移動させるように設定されています。 このポリシーが有効な場合、PSTN 通話とフェデレーション通話は Skype for Business に移動されます。
* **Skype for Business を利用していないお客様の場合**、このポリシーが有効であるときに、Teams では Teams ユーザー間の通話に加えて、PSTN 発信通話のみを利用できます。 Teams で PSTN 通話を受信するには、ユーザーに割り当てられている Teams の相互運用ポリシーを変更する必要があります。

> [!NOTE]
> Skype for Business Online で使用する電話システムと通話プランのライセンスでプロビジョニングされ、Teams の相互運用のグローバル ポリシーが設定されているユーザーには、Teams で [通話] タブが有効化されます。こうしたユーザーは、管理者による管理操作なしで Teams から PSTN 通話の発信を行うことができます。

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a>既定のポリシーを使用するように Teams を設定する方法
既定では、Teams の相互運用のグローバル ポリシーは、テナントのすべてのユーザーに適用されます。このポリシーは上記の既定の設定で構成されます。 何らかの理由により、ユーザーにこれとは異なるポリシーを割り当てている場合に既定の設定に戻すには、Teams の相互運用のグローバル ポリシーを Skype for Business の Windows PowerShell  リモート セッションを介して適用する必要があります。

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> Teams の相互運用のグローバル ポリシーで既定の値を変更することもできますが、これらの値は変更しないことを強くお勧めします。 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>PSTN 着信通話を受信するように Teams を設定する
Teams で PSTN 着信通話を受信するには、`CallingDefaultClient` パラメーターを Teams に設定してある Teams の相互運用ポリシーを適用して、Teams を既定の通話アプリケーションとして設定する必要があります。

> [!IMPORTANT]
> 広い範囲または組織レベルで変更を実施する前に、この設定を特定のユーザーのみに適用して、Teams のこの新しい通話機能を試してみることをお勧めします。

PSTN 着信通話を Teams にルーティングするには、次に示す事前に設定された Teams の相互運用ポリシーを使用することができます。

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

このポリシーの動作を次に示します。
* **Skype for Business をすでに利用しているお客様の場合**、このポリシーは着信通話を Teams にリダイレクトするように設定されています。 この場合、着信通話には VoIP (Teams と Skype for Business からの通話) と PSTN 通話が含まれます。 フェデレーション通話はこれまでどおり Skype for Business で受信されます。 
* **Skype for Business を利用していないお客様の場合**、このポリシーが有効であるときに、PSTN 通話は Teams で受信されます。 現時点では、フェデレーション通話は Teams で**サポートされていません**。

> [!WARNING]
> 現時点では、`CallingDefaultClient` を Teams に変更すると、Skype for Business IP 電話への通話にも影響を及ぼします。 Skype for Business IP 電話で着信通話を受信できなくなり、Teams クライアントでのみ着信音が鳴ります。 既存の認定済み SIP 電話のサポートについては、「[Skype for Business から Microsoft Teams へ: 機能のロードマップ](https://aka.ms/skype2teamsroadmap)」をご覧ください。

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a>PSTN 通話を受信するように Teams を設定する方法
Teams に通話をリダイレクトするには、上記の説明に従って Skype for Business の Windows PowerShell リモート セッションを介して Teams の相互運用ポリシーを適用します。

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a>通話の優先操作をユーザーが変更できるように Teams を設定する
通話を Teams または Skype for Business のどちらで受信するかといった通話の優先操作をユーザーが自分で決定できるようにするには、`AllowEndUserClientOverride` パラメーターが有効になっている Teams のカスタムの相互運用ポリシーを作成する必要があります。

ユーザーが通話の優先操作を選択できるようにする Teams の相互運用ポリシーの例を次に示します。

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

このカスタム ポリシーをユーザーに適用すると、Teams クライアントのユーザーは通話の優先アプリケーションを自ら変更するためのオプションを利用できるようになります。

![優先する通話アプリケーションのオプション](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> 広い範囲または組織レベルで変更を実施する前に、この設定を特定のユーザーのみに適用することをお勧めします。

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a>Teams のカスタムの相互運用ポリシーを作成、適用する方法
上記に示した Teams のカスタムの相互運用ポリシーを作成するには、Skype for Business の Windows PowerShell リモート セッションを介して次の操作を行います。

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a>関連項目
[通話プランの設定](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[Microsoft Teams と Skype for Business の相互運用性](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[Microsoft Teams の通話プランが設定された電話システムの実践的なガイダンス](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Skype for Business PowerShell cmdlet reference (英語)](https://docs.microsoft.com/powershell/module/skype)

[Teams PowerShell cmdlet reference](https://docs.microsoft.com/powershell/module/teams) (英語)
