---
title: 'クイック スタート ガイド: Microsoft Teams での通話プランの設定'
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
search.appverid: MET150
description: Microsoft Teams で通話プランを設定するためのクイック スタート ガイドです。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86a4862a547df6f50d0831616a42824d9f8c3287
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882099"
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
Teams の [**通話**] タブを有効にして、ユーザーが PSTN 通話の発信と受信を行えるようにするには、電話システムと通話プランの利用に向けてユーザーをプロビジョニングする必要があります。 この設定方法については、「[通話プランの設定](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)」をご覧ください。

## <a name="teams-interop-policy-configuration"></a>Teams の相互運用ポリシーの構成
Teams を有効にして通話を受けられるようにするには、通話を Teams にリダイレクトするために、[Microsoft Teams と Skype for Business の管理センター](https://aka.ms/teamsadmincenter)を使用するか、Skype for Business [`*-CsTeamsUpgradePolicy` と `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) コマンドレットでリモートの Windows PowerShell セッションを使用して、Teams のアップグレード ポリシーと Teams の相互運用ポリシー更新する必要があります。

Teams のアップグレード ポリシーと Teams の相互運用ポリシーの詳細については、「[Migration and interoperability guidance for organizations using Teams together with Skype for Business (Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス)](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)」をご覧ください。

> [!TIP]
> 必要な PowerShell コマンドレットを検索するには、[Skype for Business PowerShell コマンドレットに関するドキュメント](https://docs.microsoft.com/powershell/module/skype)で [**フィルター**] ボックスに「CsTeamsUpgradePolicy」または「CsTeamsInteropPolicy」と入力します。

### <a name="default-teams-upgrade-and-interop-policies"></a>既定の Teams のアップグレード ポリシーと相互運用ポリシー
Teams の既定のポリシーは、Teams の展開時に既存のビジネス ワークフローが中断されることがないように構成されています。 既定では、ユーザーへの VoIP 通話、PSTN 通話、フェデレーション通話は、ポリシーを更新して Teams への着信通話を有効にするまで、Skype for Business にルーティングされます。 このメカニズムにより、Teams のパイロットや展開を開始したときに、音声サービスに意図しない中断が発生するのが回避されます。

Teams のアップグレード ポリシーは、既定では、Teams または Skype for Business のどちらにチャットや通話がルーティングされるかを決める、Teams の相互運用ポリシーを受け継ぐレガシー モードで維持されます。

> [!NOTE]
> Teams のアップグレード ポリシーと Teams の相互運用ポリシーの動作は、すぐに「[Migration and interoperability guidance for organizations using Teams together with Skype for Business (Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス)](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)」に記載されているとおりに変わります。

Teams の相互運用ポリシーでは、次のように既定の設定が構成されています。

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

既定の設定の動作を次に示します。
* **Skype for Business をすでに利用しているお客様の場合**、このポリシーは Skype for Business の通話を Skype for Business に移動させ、Teams の通話を Teams に移動させるように設定されています。 このポリシーが有効な場合、PSTN 通話とフェデレーション通話は Skype for Business に移動されます。
* **Skype for Business を利用していないお客様の場合**、このポリシーが有効であるときに、Teams では Teams ユーザー間の通話に加えて、PSTN 発信通話のみを利用できます。 Teams で PSTN 通話を受信するには、ユーザーに割り当てられている Teams の相互運用ポリシーを変更する必要があります。

> [!NOTE]
> Skype for Business Online で使用する電話システムと通話プランのライセンスでプロビジョニングされ、Teams の相互運用のグローバル ポリシーが設定されているユーザーには、Teams で [通話] タブが有効化されます。こうしたユーザーは、管理者による管理操作なしで Teams から PSTN 通話の発信を行うことができます。

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>PSTN 着信通話を受信するように Teams を設定する
Teams で PSTN 着信通話を受信するには、`CallingDefaultClient` パラメーターを Teams に設定する、対応する Teams の相互運用ポリシーとともに Teams のアップグレード ポリシーを適用して、Teams を既定の通話アプリケーションとして設定する必要があります。

> [!IMPORTANT]
> 広い範囲または組織レベルで変更を実施する前に、この設定を特定のユーザーのみに適用して、Teams のこの新しい通話機能を試してみることをお勧めします。

レガシーの Teams のアップグレード ポリシーを使い続ける選択をする場合は、次の事前設定済の Teams 相互運用ポリシーを使用して、PSTN 着信通話を Teams にルーティングします。

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

更新された Teams のアップグレード ポリシーを使うことを選んだ場合、TeamsOnly モードを自分のユーザーに割り当てる必要があります。

上記のポリシーの動作を次に示します。
* **Skype for Business をすでに利用しているお客様の場合**、このポリシーは着信通話を Teams にリダイレクトするように設定されています。 この場合、着信通話には VoIP (Teams と Skype for Business からの通話) と PSTN 通話が含まれます。 
* **Skype for Business を利用していないお客様の場合**、このポリシーが有効であるときは、PSTN 通話は Teams で受信されます。

> [!WARNING]
> 現時点では、`CallingDefaultClient` を Teams に変更すると、Skype for Business IP 電話への通話にも影響がおよびます。 Skype for Business IP 電話で着信通話を受信できなくなり、Teams クライアントでのみ着信音が鳴ります。 既存の認定済み SIP 電話のサポートについては、「[Skype for Business から Microsoft Teams へ: 機能のロードマップ](https://aka.ms/skype2teamsroadmap)」をご覧ください。

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a>Teams でユーザーが PSTN 通話を受信する用に設定する方法
レガシーの Teams のアップグレード ポリシーを使用しているときに、Teams に通話をリダイレクトするには、上記の説明に従って Skype for Business の Windows PowerShell リモート セッションを介して Teams の相互運用ポリシーを適用します。

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

TeamsOnly モードを使うことを選ぶと、Microsoft Teams と Skype for Business の管理センターを介して、または Skype for Business のリモート Windows PowerShell セッションを介して、Teams に通話をリダイレクトするためにユーザーの共存モードを TeamsOnly に変更することができます。

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a>関連項目
[通話プランの設定](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Microsoft Teams の通話プランが設定された電話システムの実践的なガイダンス](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Skype for Business PowerShell cmdlet reference (英語)](https://docs.microsoft.com/powershell/module/skype)

[Teams PowerShell cmdlet reference](https://docs.microsoft.com/powershell/module/teams) (英語)
