---
title: Skype for Business Online から Microsoft Teams にアップグレードする
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Skype for Business Online 展開から Microsoft Teams に組織をアップグレードする方法について説明します。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5da45fcc5a9459b909e03f0d4e904b57d9a3f0fa
ms.sourcegitcommit: 9a9168d5c40bbb0cceaf3ffd11eb104c137f26b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2022
ms.locfileid: "67590214"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Skype for Business Online から Teams にアップグレードする

![デプロイと実装を重視したアップグレード体験図。](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 先に進む前に、次のアクティビティを完了していることを確認してください。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](./upgrade-define-project-scope.md)
- [Skype for Business と Teams の共存と相互運用を理解した](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [環境を準備した](./upgrade-prepare-environment.md)
- [組織を準備した](./upgrade-prepare-organization.md)
- [パイロットを実施した](./pilot-essentials.md)

Skype for Business Online を完全に展開し、ユーザーを Skype for Business から Teams にアップグレードする場合は、この記事のガイダンスに従ってください。 適切な共存モードとアップグレード モードをユーザーに割り当てることで、組織が選択したアップグレード体験に基づいて、ユーザーを選択的またはオールインでアップグレードできます。

> [!IMPORTANT]
> Skype for Business Online は 2021 年 7 月 31 日に廃止されました。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。 アップグレードが成功すると、技術面およびユーザーの準備が整ったことになります。Microsoft Teams への移行を進める際には、必ずこのガイドを活用してください。

## <a name="assign-the-coexistence-and-upgrade-mode"></a>共存モードとアップグレード モードを割り当てる

Microsoft Teams 管理センターまたはSkype for Businessリモート Windows PowerShell セッションを使用して実行できる TeamsUpgradePolicy の UpgradeToTeams インスタンスを割り当てることで、ユーザーを TeamsOnly モードにアップグレードできます。 これを行うには、ユーザーごとに行うか、テナント全体を 1 つの手順でアップグレードする場合はテナント全体で行うことができます。 

詳細については、「[共存およびアップグレードを設定する](./setting-your-coexistence-and-upgrade-settings.md)」および「[TeamsUpgradePolicy: 移行と共存の管理](upgrade-to-teams-on-prem-tools.md)」を参照してください。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>すべてのユーザーを Teams に一度にアップグレードする

すべてのユーザーを Teams に一度にアップグレードするには、次の手順に従います。

### <a name="step-1-notify-the-users-of-the-change-optional"></a>手順 1: 変更をユーザーに通知する (省略可能)

1. Microsoft Teams 管理センターで、 **Teams Teams** > **のアップグレード設定を選択します**。
2. **共存モード** で、[**Teams へのアップグレードが利用可能であることをユーザーに通知Skype for Business]** スイッチを **[オン]** に変更します。

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>手順 2: 共存モードを組織の TeamsOnly に設定する

1. Microsoft Teams 管理センターで、 **Teams Teams** > **のアップグレード設定を選択します**。
2. [共存モード] ドロップダウン リストから [**Teams のみ****] モード** を選択します。

## <a name="upgrade-users-in-stages"></a>段階的にユーザーをアップグレードする

TeamsOnly にユーザーを段階的にアップグレードする場合は、次の手順に従います。

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>手順 1: アップグレードするユーザーのグループを特定する

多くの場合、組織は、ユーザーの成功の波で組織をアップグレードすることを選択できます。  Microsoft Teams 管理センターでユーザーを簡単に検索できるように、最初にこれらのユーザーを識別する必要があります。 または、PowerShell を使用してこれをより効率的に行うこともできます。 特定のアップグレードウェーブの一連のユーザーを特定したら、残りの手順に進みます。

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>手順 2: 現在のアップグレードウェーブのユーザーに通知を設定する (省略可能)

Microsoft Teams 管理センターを使用している場合は、最大 20 人のユーザーに対して TeamsUpgradePolicy を一度に構成できます。
1. Microsoft Teams 管理センターで [ **ユーザー**] を選択し、アップグレードする必要がある最大 20 人のユーザーのチェック ボックスを見つけて複数選択します。 
2. リストビューの左上隅にある **[設定の編集]** を選択します。 
3. 右側の **[設定の編集]** ウィンドウの [**Teams のアップグレード**] で、[**Skype for Businessユーザーへの通知**] スイッチを **[オン]** に変更します。 注: 共存モードの値が "組織全体の設定を使用する" の場合、このスイッチは表示されないため、最初にこれらのユーザーの共存モードを組織の既定値に明示的に設定する必要があります。

または、PowerShell を使用してユーザーのグループの通知を一度に有効にする方が簡単な場合があります。 詳細については、「 [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)」を参照してください。

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>手順 3: ユーザーの共存モードを Teams のみに設定する

Teams を唯一のアプリケーションとして使用するように現在のウェーブのユーザーをアップグレードする準備ができたら、ユーザーの共存モードを Teams のみに設定します。

Microsoft Teams 管理センターを使用している場合は、最大 20 人のユーザーに対して TeamsUpgradePolicy を一度に構成できます。
1. Microsoft Teams 管理センターで [ **ユーザー**] を選択し、最大 20 人のユーザーのチェック ボックスをオンにします。
2. リストビューの左上隅にある **[設定の編集]** を選択します。
3. 右側の [ **設定の編集]** ウィンドウの [ **Teams のアップグレード** ] セクションで、共存モードをドロップダウン リストの **[Teams のみ** ] に設定します。

または、PowerShell を使用してユーザーのグループを一度にアップグレードする方が簡単な場合もあります。 詳細については、「 [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)」を参照してください。

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>手順 4: 連続するユーザーのウェーブに対して手順 1 ~ 3 を繰り返す

Teams Only モードへのアップグレードを検証し、展開する準備ができたら、前の手順を繰り返して TeamsOnly を他のユーザーに適用します。  


## <a name="phone-system-and-pstn-connectivity-options"></a>電話システムと PSTN の接続オプション

Teams を使用した電話システムは、ユーザーが TeamsOnly モードの後でサポートされます。 (ユーザーがアイランド モードの場合、電話システムはSkype for Businessでのみサポートされます)。  

### <a name="pstn-connectivity-options"></a>PSTN 接続オプション

公衆交換電話網 (PSTN) 接続オプションを検討する場合、Skype for Business Online モードから TeamsOnly モードに移行する場合は、次の 2 つのシナリオが考えられます。

- Microsoft 通話プランを使用している Skype for Business Online のユーザー。 アップグレードすると、このユーザーは Microsoft 通話プランを引き続き使用します。 これは、いくつかの手順のみを必要とする最も簡単なシナリオです。 詳細については、「[Microsoft 通話プランを使用したオンラインSkype for Businessから」を参照](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)してください。

- Skype for Business Online のユーザー。オンプレミスまたは Cloud Connector Edition を通じてオンプレミスの音声機能Skype for Business使用します。 このユーザーの Teams へのアップグレードは、その TeamsOnly ユーザーが確実に PSTN 機能を持てるようにするため、ユーザーのダイレクト ルーティングへの移行に合わせた調整が必要になります。  詳細については、「[オンプレミスの音声を使用したオンラインSkype for Business](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)から」を参照してください。
