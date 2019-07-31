---
title: Skype for Business Online を Microsoft Teams にアップグレードする |Deploy
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Skype for Business Online から Teams にアップグレードする場合の考慮事項
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9994bb8efa862cc66cb1e081d0ca8136b4fb1871
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "35934503"
---
![展開と実装を強調したアップグレードの図](media/upgrade-banner-deployment.png "展開と実装のステージに重点を置いたアップグレードの段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 先に進む前に、次のアクティビティを完了していることを確認してください。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
- [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [環境を準備した](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [組織を準備した](https://aka.ms/SkypeToTeams-UserReadiness)
- [パイロットを実施した](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Skype for Business Online から Teams にアップグレードする

Skype for business Online を完全に展開していて、ユーザーを Skype for Business から Teams にアップグレードする場合は、この記事の指示に従ってください。 組織で選択されているアップグレードの過程に基づいて、ユーザーを選択的またはすべてのユーザーにアップグレードするには、適切な共存とアップグレードモードをユーザーに割り当てます。

> [!IMPORTANT]
> Skype for Business Online は、2021年7月31日に廃止されます。その後、アクセスまたはサポートされなくなります。 給付金を最大限に活用し、組織がアップグレードを実装するための適切な時間を確保するために、Microsoft Teams の現在の旅を開始することをお勧めします。 アップグレードが正常に完了した場合は、技術的かつユーザーの準備ができていることに注意してください。このガイドは、Microsoft Teams への旅に進むときに必ずご利用ください。

## <a name="assign-the-coexistence-and-upgrade-mode"></a>共存とアップグレードモードを割り当てる

Microsoft Teams 管理センターまたは Skype for Business リモート Windows Powershell セッションを使用して実行できる TeamsUpgradePolicy の UpgradeToTeams インスタンスを割り当てることによって、ユーザーを TeamsOnly モードにアップグレードできます。 これは、1つの手順でテナント全体をアップグレードする場合に、ユーザーごと、またはテナント全体で行うことができます。 

詳細については、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」および「[TeamsUpgradePolicy: 移行と共存の管理](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)」を参照してください。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>一度にすべてのユーザーを Teams にアップグレードする

すべてのユーザーをチームに一度にアップグレードするには、次の手順を実行します。

### <a name="step-1-notify-the-users-of-the-change-optional"></a>手順 1: ユーザーに変更を通知する (省略可能)

1. Microsoft Teams 管理センターで、[**組織全体の設定** > ]**チームのアップグレード**を選択します。
2. [**共存モード**] で、[**チームへのアップグレードが可能であることを Skype for Business ユーザーに通知**する] を **[オン**] に変更します。

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>手順 2: 組織の場合のみ、共存モードを teams に設定します。

1. Microsoft Teams 管理センターで、[**組織全体の設定**] を選択します。
2. [**共存モード**] ドロップダウンリストから [**チームのみ**] モードを選択します。

## <a name="upgrade-users-in-stages"></a>ユーザーを段階的にアップグレードする

ユーザーをチームに段階的にアップグレードする場合は、次の手順を実行します。

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>手順 1: アップグレードするユーザーグループを特定する

組織では、ユーザーの成功波で組織のアップグレードが選択されることがあります。  これらのユーザーを最初に特定して、Microsoft Teams 管理センターで簡単に検索できるようにします。 または、PowerShell を使用して、より効率的にこの操作を行うこともできます。 特定のアップグレードウェーブの一連のユーザーを特定したら、残りの手順を続行します。

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>手順 2: 現在のアップグレードウェーブでユーザーに通知を設定する (省略可能)

Microsoft Teams 管理センターを使用している場合は、一度に最大20人のユーザーに対して TeamsUpgradePolicy を構成できます。
1. Microsoft Teams 管理センターで、[**ユーザー**] を選択し、アップグレードする必要がある最大20人のユーザーのチェックボックスをオンまたは複数選択します。 
2. Listview の左上隅にある [**設定の編集**] を選択します。 
3. 右側の [**設定の編集**] ウィンドウで、[チームの**アップグレード**] の下の [ **Skype for business ユーザーの**切り替え] を **[オン**] に変更します。 注: 共存モードの値が "組織全体の設定を使用する" である場合、このスイッチは表示されません。そのため、最初に、これらのユーザーの共存モードを明示的に設定して、組織の既定値にする必要があります。

または、PowerShell を使用すると、ユーザーのグループに対して簡単に通知を有効にすることができます。 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>手順 3: ユーザーの共存モードをチームのみに設定する

現在のウェーブのユーザーをアップグレードして Teams のみをアプリケーションとして使用できるようにするには、ユーザーの [共存] モードを [チームのみ] に設定します。

Microsoft Teams 管理センターを使用している場合は、一度に最大20人のユーザーに対して TeamsUpgradePolicy を構成できます。
1. Microsoft Teams 管理センターで、[**ユーザー**] を選択し、最大20人のユーザーのチェックボックスをオンにします。
2. Listview の左上隅にある [**設定の編集**] を選択します。
3. 右側の [**編集の設定**] ウィンドウの [**チームのアップグレード**] セクションで、[共存モード] をドロップダウンリストの [**チームのみ**] に設定します。

または、PowerShell を使用すると、ユーザーのグループを簡単にアップグレードできます。 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>手順 4: 連続したユーザーのために手順1-3 を繰り返します。

チーム専用モードへのアップグレードを検証し、展開する準備ができたら、上記の手順を繰り返して、他のユーザーにのみ TeamsOnly を適用します。  


## <a name="phone-system-and-teams-upgrade"></a>電話システムと Teams のアップグレード

Skype for Business Online の展開に通話プランを含む電話システムが含まれていて、Microsoft が公衆交換電話網 (PSTN) プロバイダーである場合、ユーザーを Teams にアップグレードすると、着信する PSTN 通話は Teams に自動的に移行されます。

Skype for Business Online の展開にクラウドコネクタエディションの電話システムが含まれている場合は、「[電話システムのダイレクトルーティングに関するその他の考慮事項](2-envision-make-my-service-decisions-direct-routing.md)」を参照してください。
