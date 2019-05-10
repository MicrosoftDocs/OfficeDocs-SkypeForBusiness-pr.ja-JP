---
title: マイクロソフト チームをオンラインでビジネス用の Skype のアップグレードします。展開
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: ビジネス オンラインの Skype からチームへのアップグレードに関する考慮事項
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc1334e019abadb030199518df15b0dde74dde52
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835336"
---
![展開と実装の段階に重点を置いた、アップグレード手順の各段階](media/upgrade-banner-deployment.png "展開と実装の段階に重点を置いた、アップグレード手順の各段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 先に進む前に、次のアクティビティを完了していることを確認してください。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
- [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [環境を準備した](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [組織を準備した](https://aka.ms/SkypeToTeams-UserReadiness)
- [パイロットを実施した](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Skype for Business Online から Teams にアップグレードする

完全 Skype をオンライン ビジネスを展開しているし、ビジネスの Skype からのチームにユーザーをアップグレードする場合のこの資料の指示に従います。 ユーザーを選択的にアップグレードすることができますまたはアップグレードをに基づいて、オールインワンの旅を適切な共存およびアップグレード モードをユーザーに割り当てることにより、組織が選択されます。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>共存およびアップグレード モードを割り当てる

ビジネス リモートの Windows Powershell セッションでマイクロソフトのチームの管理センターや、Skype を使用して実行することができる TeamsUpgradePolicy の UpgradeToTeams インスタンスを割り当てることによって、TeamsOnly モードにユーザーをアップグレードできます。 できますこれを行うユーザーごと、またはテナント単位で 1 つのステップで全体のテナントにアップグレードする場合。 

詳細については、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」および「[TeamsUpgradePolicy: 移行と共存の管理](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)」を参照してください。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>チームにすべてのユーザーを同時にアップグレードします。

この手順では、一度に 1 つのチームにすべてのユーザーをアップグレードします。

### <a name="step-1-notify-the-users-of-the-change-optional"></a>ステップ 1: (省略可能) の変更をユーザーに通知します。

1. マイクロソフトのチーム管理センターで、**組織全体の設定**を選択して > **のチームをアップグレード**します。
2. **共存モード**では、[**上**に**チームへのアップグレードが利用可能なビジネス ・ ユーザーの通知の Skype**のスイッチを変更します。

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>ステップ 2: TeamsOnly に組織で共存モードを設定します。

1. マイクロソフトのチーム管理センターでは、**組織全体の設定**を選択します。
2. **共存モード**」ドロップ ダウン リストから**チームのみ**のモードを選択します。

## <a name="upgrade-users-in-stages"></a>ユーザーを段階的にアップグレードします。

TeamsOnly にユーザーを段階的にアップグレードする場合は、以下の手順を実行します。

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>ステップ 1: アップグレードのためのユーザーのグループを識別します。

組織では多くの場合は、ユーザーの成功の波に自分の組織をアップグレードすることができます。  検索できるように簡単にそれらのマイクロソフトのチームの管理センターで最初にこれらのユーザーを識別します。 またはより効率的にこれを行うに PowerShell を使用する場合があります。 アップグレード ウェーブの特定のユーザーのセットを識別した後は、残りの手順を続行します。

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a>ステップ 2: 通知を設定、ユーザーの現在のアップグレードのウェーブで (省略可能)

マイクロソフトのチームの管理センターを使用する場合、一度に最大 20 個のユーザーの TeamsUpgradePolicy を構成できます。
1. マイクロソフトのチーム管理センターで、**ユーザー**、および検索と複数選択チェック ボックスをオンに最大 20 個のユーザーがアップグレードする必要があります。 
2. リスト ビューの左上隅で**設定を編集**を選択します。 
3. **チームのアップグレード**をするには、下、右上の**設定を編集**] ウィンドウでは、**上**に**通知 Skype ビジネス ユーザーの**スイッチを変更します。 注: 共存モードの値が使用して組織全体にわたる設定」の場合は、表示されませんこのスイッチでは、最初にこれらのユーザーに、組織の既定値は、どのような共存モードを明示的に設定する必要があります。

または、する場合がありますほうが簡単な PowerShell を使用して、一度にユーザーのグループに通知を有効にします。 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>ステップ 3: ユーザーがチームのみの共存モードを設定します。

現在の波形で、唯一のアプリケーションとして、チームを使用するユーザーをアップグレードする準備ができたら、チームだけにユーザーの共存モードを設定します。

マイクロソフトのチームの管理センターを使用する場合、一度に最大 20 個のユーザーの TeamsUpgradePolicy を構成できます。
1. マイクロソフトのチーム管理センターで、**ユーザー**を選択し、最大 20 個のユーザーのチェック ボックスを選択します。
2. リスト ビューの左上隅で**設定を編集**を選択します。
3. 右側の**チームをアップグレード**] セクションで、[**設定の編集**ウィンドウでドロップ ダウン リストで**チームのみ**に共存モードを設定します。

または、する場合がありますほうが簡単な PowerShell を使用して、一度にユーザーのグループをアップグレードします。 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>手順 4: ユーザーの連続した波の手順 1 ~ 3 を繰り返します

チームのみのモードへのアップグレードの検証を展開する準備ができているより多くのユーザーに TeamsOnly を適用する前の手順を繰り返します。  


## <a name="phone-system-and-teams-upgrade"></a>電話システムと Teams のアップグレード

場合は、オンライン ビジネスの展開、Skype には、計画を呼び出すと、電話システムが含まれています、、公衆交換電話網 (PSTN) プロバイダーが、チームにユーザーをアップグレードするは自動的に移行チームを呼び出す PSTN を受信します。

オンライン ビジネス展開するため、Skype には、クラウドのコネクタのエディションでの電話システムが含まれている場合は、[電話システムの直接のルーティングのための追加の考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。
