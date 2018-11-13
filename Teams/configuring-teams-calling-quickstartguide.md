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
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a1fb82f57035f238ce222bf7f21b72983d21075
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295915"
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

## <a name="teams-interop-policy-configuration"></a>Teams の相互運用ポリシーの設定
呼び出しの受信を開始するチームを有効にするには、する必要がありますチーム アップグレード ポリシーおよびポリシーの相互運用機能チームを更新するのには[マイクロソフトのチームとビジネス管理センターの Skype](https://aka.ms/teamsadmincenter)を使用するか、Skype でリモートの Windows PowerShell セッションを使用してビジネス[`*-CsTeamsUpgradePolicy`と`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype)コマンドレットは、チームへの呼び出しをリダイレクトします。

アップグレードのポリシーをチームとチームの相互運用機能のポリシーの詳細については、[移行とビジネス用の Skype とチームを使用する組織の相互運用性ガイド](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)を参照してください。

> [!TIP]
> 必要がある PowerShell コマンドレットを検索するには、 [Skype](https://docs.microsoft.com/powershell/module/skype)で [CsTeamsUpgradePolicy] または [**フィルター** ] ボックスには、"CsTeamsInteropPolicy"を入力します。

### <a name="default-teams-upgrade-and-interop-policies"></a>既定のチームのアップグレードと相互運用機能のポリシー
Teams の既定のポリシーは、Teams の展開時に既存のビジネス ワークフローが中断されることがないよう設定されています。 既定では、ユーザーへの VoIP 通話、PSTN 通話、フェデレーション通話は、ポリシーを更新して Teams への着信通話を有効にするまで、Skype for Business にルーティングされます。 このメカニズムにより、Teams のパイロットや展開を開始したときに発生する可能性のある意図しない中断が回避されます。

チームの既定のアップグレードのポリシーが保たれ、以前のバージョンのモードを確認するのに、チャットや通話をルーティングするには - チームの相互運用ポリシーを優先するチームやビジネス用の Skype です。

> [!NOTE]
> チームの動作ポリシーのアップグレードおよび[移行とビジネス用の Skype とチームを使用する組織の相互運用性ガイド](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)で説明するよう、チームの相互運用機能のポリシーは変更すぐに

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

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>PSTN 着信通話を受信するように Teams を設定する
チームで PSTN 通話の着信を受信する既定のポリシーを使用して、対応するチーム相互運用機能を設定するチームのアップグレード ポリシーを適用することでアプリケーションの呼び出しとして、チームを構成する必要があります`CallingDefaultClient`チームのパラメーターです。

> [!IMPORTANT]
> 広い範囲または組織レベルで変更を実施する前に、この設定を特定のユーザーのみに適用して、Teams のこの新しい通話機能を試してみることをお勧めします。

チームの従来のアップグレード ポリシーを使用して続行する場合は、チームへのインバウンドの PSTN 通話をルーティングする構成済みのチーム相互運用ポリシーは以下を使用します。

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

チームの最新のアップグレード ポリシーを使用することを選択した場合は、TeamsOnly モードをユーザーに割り当てる必要があります。

このポリシーの動作を次に示します。
* **Skype for Business をすでに利用しているお客様の場合**、このポリシーは着信通話を Teams にリダイレクトするように設定されています。 この場合、着信通話には VoIP (Teams と Skype for Business からの通話) と PSTN 通話が含まれます。 
* **Skype for Business を利用していないお客様の場合**、このポリシーが有効であるときに、PSTN 通話は Teams で受信されます。

> [!WARNING]
> 現時点では、`CallingDefaultClient` を Teams に変更すると、Skype for Business IP 電話への通話にも影響を及ぼします。 Skype for Business IP 電話で着信通話を受信できなくなり、Teams クライアントでのみ着信音が鳴ります。 既存の認定済み SIP 電話のサポートについては、「[Skype for Business から Microsoft Teams へ: 機能のロードマップ](https://aka.ms/skype2teamsroadmap)」をご覧ください。

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a>チームでの呼び出しの PSTN を受信するユーザーを構成する方法
チームの従来のアップグレード ポリシーを使用して、チームへの呼び出しをリダイレクトするのにはリモートの Windows PowerShell セッションをビジネス用の Skype を使用して上記で説明したチームの相互運用機能のポリシーが適用されます。

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

TeamsOnly モードを使用する場合は、マイクロソフトのチームのビジネス管理センターでは、Skype 経由で、またはチームへの呼び出しをリダイレクトするのにはリモートの Windows PowerShell セッションをビジネス用の Skype 経由での TeamsOnly にユーザーの共存モードを変更できます。

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a>関連項目
[通話プランの設定](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[ビジネスのチームとは、Skype を使用する組織の移行と相互運用性のガイド](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Microsoft Teams の通話プランが設定された電話システムの実践的なガイダンス](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Skype for Business PowerShell cmdlet reference (英語)](https://docs.microsoft.com/powershell/module/skype)

[Teams PowerShell cmdlet reference](https://docs.microsoft.com/powershell/module/teams) (英語)
