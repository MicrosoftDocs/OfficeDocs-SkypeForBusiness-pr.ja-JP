---
title: Skype for Business Online から Microsoft Teams にアップグレードする
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 組織をアップグレードして、Microsoft Teams Online 展開Skype for Business説明します。
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
ms.openlocfilehash: 7c35909bf7787242a07f89d1442a25365348c91a
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282104"
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

Skype for Business Online を完全にデプロイし、ユーザーを Skype for Business から Teams にアップグレードする場合は、この記事のガイダンスに従います。 適切な共存モードとアップグレード モードをユーザーに割り当てると、組織が選択したアップグレード体験に基づいて、ユーザーを選択的またはすべてアップグレードできます。

> [!IMPORTANT]
> Skype for Business Online は 2021 年 7 月 31 日に廃止される予定です。それ以降、アクセスとサポートが終了します。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。 アップグレードが成功すると、技術面およびユーザーの準備が整ったことになります。Microsoft Teams への移行を進める際には、必ずこのガイドを活用してください。

## <a name="assign-the-coexistence-and-upgrade-mode"></a>共存モードとアップグレード モードを割り当てる

TeamsUpgradePolicy の UpgradeToTeams インスタンスを割り当てると、ユーザーを TeamsOnly モードにアップグレードできます。このインスタンスは、Microsoft Teams 管理センターまたは Skype for Business リモート Windows PowerShell セッションを使用して実行できます。 これを行うには、ユーザーごとに、またはテナント全体を 1 つの手順でアップグレードする場合は、テナント全体で行います。 

詳細については、「[共存およびアップグレードを設定する](./setting-your-coexistence-and-upgrade-settings.md)」および「[TeamsUpgradePolicy: 移行と共存の管理](upgrade-to-teams-on-prem-tools.md)」を参照してください。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>すべてのユーザーを一度Teamsにアップグレードする

次の手順に従って、すべてのユーザーを一度にTeamsアップグレードします。

### <a name="step-1-notify-the-users-of-the-change-optional"></a>手順 1: 変更をユーザーに通知する (省略可能)

1. 管理センター Microsoft Teamsで、[アップグレード] で **[組織全体の設定**  >  **] Teams選択します**。
2. [**共存モード] で**、[アップグレードが利用可能Skype for Businessユーザーに通知する] Teams **を**[オン] に **変更します**。

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>手順 2: 組織の共存モードを TeamsOnly に設定する

1. 管理センター Microsoft Teams、組織全体の設定 **を選択します**。
2. [Teams **モード] ドロップダウン** リストから **[モード** のみ] を選択します。

## <a name="upgrade-users-in-stages"></a>ユーザーをステージにアップグレードする

ユーザーを TeamsOnly に段階的にアップグレードする場合は、次の手順に従います。

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>手順 1: アップグレードするユーザーのグループを識別する

多くの場合、組織はユーザーの成功の波で組織をアップグレードすることができます。  これらのユーザーを最初に特定して、管理センターで簡単に検索Microsoft Teams必要があります。 または、PowerShell を使用して、より効率的に行う必要がある場合があります。 特定のアップグレード ウェーブの一連のユーザーを特定したら、残りの手順に進みます。

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>手順 2: 現在のアップグレード ウェーブのユーザーに通知を設定する (省略可能)

管理センター Microsoft Teams場合、最大 20 人のユーザーに対して TeamsUpgradePolicy を一度に構成できます。
1. 管理センター Microsoft Teams[ユーザー] を選択し、アップグレードする必要がある最大 20 人のユーザーのチェック ボックスを見つけて複数選択します。 
2. リスト **ビューの左上** 隅にある [設定の編集] を選択します。 
3. 右側の **[設定の編集**] ウィンドウの [アップグレード] で、[Teams **通知**] を [ユーザーに通知 **Skype for Business]** スイッチを [オン] に **変更します**。 注: 共存モードの値が "組織全体の設定を使用" の場合、このスイッチは表示されません。そのため、これらのユーザーの共存モードを組織の既定値に明示的に設定する必要があります。

または、PowerShell を使用して一度にユーザー のグループに対する通知を有効にする方が簡単な場合があります。 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>手順 3: ユーザーの共存モードを [共有のみ] Teamsする

現在のウェーブのユーザーをアップグレードして、Teams を唯一のアプリケーションとして使用する準備ができたら、ユーザーの共存モードを [Teams のみ] に設定します。

管理センター Microsoft Teams場合、最大 20 人のユーザーに対して TeamsUpgradePolicy を一度に構成できます。
1. 管理センター Microsoft Teams、[ユーザー]**を選択** し、最大 20 人のユーザーのチェック ボックスをオンにします。
2. リスト **ビューの左上** 隅にある [設定の編集] を選択します。
3. 右側の **[設定** の編集] ウィンドウの [Teams **アップグレード**] セクションで、共存モードをドロップダウン リストの [Teams **のみ**] に設定します。

または、PowerShell を使用してユーザーのグループを一度にアップグレードする方が簡単な場合があります。 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>手順 4: 連続するユーザーのウェーブに対して手順 1 ~ 3 を繰り返す

Teams モードへのアップグレードを検証し、展開する準備ができたら、前の手順を繰り返して TeamsOnly を他のユーザーに適用します。  


## <a name="phone-system-and-pstn-connectivity-options"></a>電話システム PSTN 接続オプション

電話システムのTeamsは、ユーザーが TeamsOnly モードの場合にサポートされます。 (ユーザーが Islands モードの場合電話システムは、Skype for Business。  

### <a name="pstn-connectivity-options"></a>PSTN 接続オプション

公衆交換電話網 (PSTN) 接続オプションを検討する場合、Skype for Business Online から TeamsOnly モードに移行する場合、次の 2 つのシナリオが考えられます。

- Microsoft 通話プランを使用している Skype for Business Online のユーザー。 アップグレードすると、このユーザーは Microsoft 通話プランを引き続き使用します。 これは、いくつかの手順のみを必要とする最も簡単なシナリオです。 詳細については、「Microsoft 通話プランを[使用Skype for Businessオンラインから」を参照してください](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。

- Skype for Business Online のユーザー。オンプレミスまたは Cloud Connector Edition を介してSkype for Business音声機能を使用します。 このユーザーの Teams へのアップグレードは、その TeamsOnly ユーザーが確実に PSTN 機能を持てるようにするため、ユーザーのダイレクト ルーティングへの移行に合わせた調整が必要になります。  詳細については、「オンプレミス音声を使用[した Skype for Business Online から」を参照してください](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)。