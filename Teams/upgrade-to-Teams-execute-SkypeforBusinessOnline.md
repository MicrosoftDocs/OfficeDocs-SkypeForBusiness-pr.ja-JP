---
title: Skype for Business Online から Microsoft Teams にアップグレードする
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Skype for Business Online の展開から組織を Microsoft Teams にアップグレードする方法について説明します。
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
ms.openlocfilehash: ca99c193a17547943018eba75004f0ec0a1a92f3
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578260"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Skype for Business Online から Teams にアップグレードする

![展開と実装に重点を置いた、アップグレードのフロー図](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 続行する前に、次の作業が完了していることを確認します。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
- [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [環境を準備した](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [組織を準備した](https://aka.ms/SkypeToTeams-UserReadiness)
- [パイロットを実施した](https://aka.ms/SkypeToTeams-Pilot)

Skype for business Online を完全に展開していて、ユーザーを Skype for Business から Teams にアップグレードする場合は、この記事の指示に従ってください。 組織で選択されているアップグレードの過程に基づいて、ユーザーを選択的またはすべてのユーザーにアップグレードするには、適切な共存とアップグレードモードをユーザーに割り当てます。

> [!IMPORTANT]
> Skype for Business Online は 2021 年 7 月 31 日に廃止される予定です。それ以降、アクセスとサポートが終了します。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。 アップグレードが成功すると、技術面およびユーザーの準備が整ったことになります。Microsoft Teams への移行を進める際には、必ずこのガイドを活用してください。

## <a name="assign-the-coexistence-and-upgrade-mode"></a>共存とアップグレードモードを割り当てる

Microsoft Teams 管理センターまたは Skype for Business リモート Windows PowerShell セッションを使用して実行できる TeamsUpgradePolicy の UpgradeToTeams インスタンスを割り当てることによって、ユーザーを TeamsOnly モードにアップグレードできます。 これは、1つの手順でテナント全体をアップグレードする場合に、ユーザーごと、またはテナント全体で行うことができます。 

詳細については、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」および「[TeamsUpgradePolicy: 移行と共存の管理](upgrade-to-teams-on-prem-tools.md)」を参照してください。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>一度にすべてのユーザーを Teams にアップグレードする

すべてのユーザーをチームに一度にアップグレードするには、次の手順を実行します。

### <a name="step-1-notify-the-users-of-the-change-optional"></a>手順 1: ユーザーに変更を通知する (省略可能)

1. Microsoft Teams 管理センターで、[**組織全体の設定**] チームのアップグレードを選択し  >  **Teams upgrade** ます。
2. [ **共存モード**] で、[ **チームへのアップグレードが可能であることを Skype for Business ユーザーに通知** する] を **[オン**] に変更します。

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>手順 2: 組織の場合のみ、共存モードを teams に設定します。

1. Microsoft Teams 管理センターで、[ **組織全体の設定**] を選択します。
2. [**共存モード**] ドロップダウンリストから [**チームのみ**] モードを選択します。

## <a name="upgrade-users-in-stages"></a>ユーザーを段階的にアップグレードする

ユーザーをチームに段階的にアップグレードする場合は、次の手順を実行します。

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>手順 1: アップグレードするユーザーグループを特定する

組織では、ユーザーの成功波で組織のアップグレードが選択されることがあります。  これらのユーザーを最初に特定して、Microsoft Teams 管理センターで簡単に検索できるようにします。 または、PowerShell を使用して、より効率的にこの操作を行うこともできます。 特定のアップグレードウェーブの一連のユーザーを特定したら、残りの手順を続行します。

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>手順 2: 現在のアップグレードウェーブでユーザーに通知を設定する (省略可能)

Microsoft Teams 管理センターを使用している場合は、一度に最大20人のユーザーに対して TeamsUpgradePolicy を構成できます。
1. Microsoft Teams 管理センターで、[ **ユーザー**] を選択し、アップグレードする必要がある最大20人のユーザーのチェックボックスをオンまたは複数選択します。 
2. Listview の左上隅にある [ **設定の編集** ] を選択します。 
3. 右側の [ **設定の編集** ] ウィンドウで、[チームの **アップグレード**] の下の [ **Skype for business ユーザーの** 切り替え] を **[オン**] に変更します。 注: 共存モードの値が "組織全体の設定を使用する" である場合、このスイッチは表示されません。そのため、最初に、これらのユーザーの共存モードを明示的に設定して、組織の既定値にする必要があります。

または、PowerShell を使用すると、ユーザーのグループに対して簡単に通知を有効にすることができます。 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>手順 3: ユーザーの共存モードをチームのみに設定する

現在のウェーブのユーザーをアップグレードして Teams のみをアプリケーションとして使用できるようにするには、ユーザーの [共存] モードを [チームのみ] に設定します。

Microsoft Teams 管理センターを使用している場合は、一度に最大20人のユーザーに対して TeamsUpgradePolicy を構成できます。
1. Microsoft Teams 管理センターで、[ **ユーザー**] を選択し、最大20人のユーザーのチェックボックスをオンにします。
2. Listview の左上隅にある [ **設定の編集** ] を選択します。
3. 右側の [ **編集の設定** ] ウィンドウの [ **チームのアップグレード** ] セクションで、[共存モード] をドロップダウンリストの [ **チームのみ** ] に設定します。

または、PowerShell を使用すると、ユーザーのグループを簡単にアップグレードできます。 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>手順 4: 連続したユーザーのために手順1-3 を繰り返します。

チーム専用モードへのアップグレードを検証し、展開する準備ができたら、上記の手順を繰り返して、他のユーザーにのみ TeamsOnly を適用します。  


## <a name="phone-system-and-pstn-connectivity-options"></a>電話システムと PSTN の接続オプション

ユーザーが TeamsOnly モードになった後、Teams での電話システムはサポートされています。 (ユーザーが諸島モードの場合、電話システムは Skype for Business でのみサポートされています)。  

### <a name="pstn-connectivity-options"></a>PSTN 接続オプション

公衆交換電話網 (PSTN) の接続オプションを検討する場合、Skype for Business Online から TeamsOnly モードに移行すると、次の2つのシナリオが考えられます。

- Microsoft 通話プランを使用している Skype for Business Online のユーザー。 アップグレードすると、このユーザーは Microsoft 通話プランを引き続き使用します。 これは、わずかな手順しか必要としない最も簡単なシナリオです。 詳細については、「 [Skype For Business Online から Microsoft の通話プランを使用](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)する」を参照してください。

- Skype for business のオンプレミスまたはクラウドコネクタエディションによるオンプレミス音声機能を備えた Skype for Business Online のユーザー。 このユーザーの Teams へのアップグレードは、その TeamsOnly ユーザーが確実に PSTN 機能を持てるようにするため、ユーザーのダイレクト ルーティングへの移行に合わせた調整が必要になります。  詳細については、「 [Skype For Business Online からオンプレミス音声を使用](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)する」を参照してください。


