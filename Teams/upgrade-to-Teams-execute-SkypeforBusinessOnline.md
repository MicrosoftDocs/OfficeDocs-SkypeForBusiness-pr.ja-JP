---
title: Skype for Business Online から Microsoft Teams にアップグレードする
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Skype for Business Online 展開から組織を Microsoft Teams にアップグレードする方法について説明します。
localization_priority: Normal
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
ms.openlocfilehash: 65b00f8e56792164ed2aa0b8240d0d131a7bdbcd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104013"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Skype for Business Online から Teams にアップグレードする

![展開と実装に重点を置いた、アップグレードのフロー図](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 先に進む前に、次のアクティビティを完了していることを確認してください。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](./upgrade-define-project-scope.md)
- [Skype for Business と Teams の共存と相互運用を理解した](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [環境を準備した](./upgrade-prepare-environment.md)
- [組織を準備した](./upgrade-prepare-organization.md)
- [パイロットを実施した](./pilot-essentials.md)

Skype for Business Online を完全に展開し、ユーザーを Skype for Business から Teams にアップグレードする場合は、この記事のガイダンスに従います。 適切な共存モードとアップグレード モードをユーザーに割り当てると、組織が選択したアップグレードの手順に基づいて、ユーザーを選択的に、またはすべてアップグレードできます。

> [!IMPORTANT]
> Skype for Business Online は 2021 年 7 月 31 日に廃止される予定です。それ以降、アクセスとサポートが終了します。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。 アップグレードが成功すると、技術面およびユーザーの準備が整ったことになります。Microsoft Teams への移行を進める際には、必ずこのガイドを活用してください。

## <a name="assign-the-coexistence-and-upgrade-mode"></a>共存モードとアップグレード モードを割り当てる

TeamsUpgradePolicy の UpgradeToTeams インスタンスを割り当てると、ユーザーを TeamsOnly モードにアップグレードできます。これは、Microsoft Teams 管理センターまたは Skype for Business リモート Windows PowerShell セッションを使用して実行できます。 1 つの手順でテナント全体をアップグレードする場合は、ユーザーごとに、またはテナント全体に基づいてこれを行います。 

詳細については、「[共存およびアップグレードを設定する](./setting-your-coexistence-and-upgrade-settings.md)」および「[TeamsUpgradePolicy: 移行と共存の管理](upgrade-to-teams-on-prem-tools.md)」を参照してください。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>すべてのユーザーを Teams に一度にアップグレードする

すべてのユーザーを Teams に一度にアップグレードするには、次の手順に従います。

### <a name="step-1-notify-the-users-of-the-change-optional"></a>手順 1: 変更をユーザーに通知する (オプション)

1. Microsoft Teams 管理センターで、組織全体の設定 Teams **のアップグレード**  >  **を選択します**。
2. 共存 **モードで、[Teams** へのアップグレードが可能な場合に Skype for Business ユーザーに **通知する** ] を [オン] に切り替 **えます**。

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>手順 2: 共存モードを組織の TeamsOnly に設定する

1. Microsoft Teams 管理センターで、組織全体 **の設定を選択します**。
2. [ **共存モード]** ドロップダウン リストから **[Teams のみ]** モードを選択します。

## <a name="upgrade-users-in-stages"></a>ユーザーをステージにアップグレードする

ユーザーを TeamsOnly に段階的にアップグレードする場合は、次の手順に従います。

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>手順 1: アップグレードするユーザーのグループを特定する

多くの場合、組織はユーザーの成功の波で組織をアップグレードする場合があります。  Microsoft Teams 管理センターで簡単に検索できるよう、これらのユーザーを最初に特定する必要があります。 または、PowerShell を使用して、より効率的にこれを行う必要がある場合があります。 特定のアップグレード ウェーブのユーザー セットを特定したら、残りの手順に進みます。

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>手順 2: 現在のアップグレード ウェーブでユーザーに通知を設定する (オプション)

Microsoft Teams 管理センターを使用している場合は、最大 20 人のユーザーに対して一度に TeamsUpgradePolicy を構成できます。
1. Microsoft Teams 管理センターで、[ユーザー] を選択し、アップグレードする必要がある最大 20 人のユーザーのチェック ボックスを見つけて複数選択します。 
2. リスト **ビューの左上** 隅にある [設定の編集] を選択します。 
3. 右側の **[設定の** 編集] ウィンドウの **[Teams のアップグレード]** で **、[Skype for Business** ユーザーに通知する] を [オン] に変更 **します**。 注: 共存モードの値が "組織全体の設定を使用する" の場合、このスイッチは表示されません。そのため、最初にこれらのユーザーの共存モードを組織の既定値に明示的に設定する必要があります。

または、PowerShell を使用して一度にユーザー のグループに対する通知を有効にする方が簡単な場合があります。 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>手順 3: ユーザーの共存モードを Teams のみに設定する

現在のウェーブでユーザーをアップグレードして Teams を唯一のアプリケーションとして使用する準備ができたら、ユーザーの共存モードを Teams のみに設定します。

Microsoft Teams 管理センターを使用している場合は、最大 20 人のユーザーに対して TeamsUpgradePolicy を一度に構成できます。
1. Microsoft Teams 管理センターで、[ユーザー] **を選択** し、最大 20 人のユーザーのチェック ボックスをオンにします。
2. リスト **ビューの左上** 隅にある [設定の編集] を選択します。
3. 右側の **[設定の** 編集] ウィンドウの **[Teams** のアップグレード] セクションで、ドロップダウン リストで共存モードを **[Teams のみ** ] に設定します。

または、PowerShell を使用してユーザーのグループを一度にアップグレードする方が簡単な場合があります。 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>手順 4: 連続するユーザーのウェーブに対して手順 1 ~ 3 を繰り返す

Teams Only モードへのアップグレードを検証し、展開する準備ができたら、前の手順を繰り返して、TeamsOnly を他のユーザーに適用します。  


## <a name="phone-system-and-pstn-connectivity-options"></a>電話システムと PSTN 接続オプション

Teams の電話システムは、ユーザーが TeamsOnly モードに切り替えた後にサポートされます。 (ユーザーが諸島モードの場合、電話システムは Skype for Business でのみサポートされます)。  

### <a name="pstn-connectivity-options"></a>PSTN 接続オプション

公衆交換電話網 (PSTN) 接続オプションを検討する場合、Skype for Business Online から TeamsOnly モードに移行する場合、次の 2 つのシナリオが考えられます。

- Microsoft 通話プランを使用している Skype for Business Online のユーザー。 アップグレードすると、このユーザーは Microsoft 通話プランを引き続き使用します。 これは、いくつかの手順のみを必要とする最も簡単なシナリオです。 詳細については [、「Skype for Business Online と Microsoft 通話プラン」を参照してください](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。

- Skype for Business Online のユーザーで、オンプレミスの Skype for Business または Cloud Connector Edition を介して、オンプレミスの音声機能を使用します。 このユーザーの Teams へのアップグレードは、その TeamsOnly ユーザーが確実に PSTN 機能を持てるようにするため、ユーザーのダイレクト ルーティングへの移行に合わせた調整が必要になります。  詳細については [、「Skype for Business Online でオンプレミスの音声を使用する場合」を参照してください](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)。