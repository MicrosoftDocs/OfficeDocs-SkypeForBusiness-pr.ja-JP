---
title: チームのチームで Microsoft に Skype のオンライン ビジネスからのアップグレード
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 12/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: ビジネス オンラインの Skype からチームへのアップグレードに関する考慮事項
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f454b3c6e7ae41e87c9d44c02cd76b995313fc7
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2019
ms.locfileid: "27789332"
---
![展開に重点を置いて、アップグレードの旅の段階や実装段階](media/upgrade-banner-deployment.png "展開に重点を置いて、アップグレードの旅の段階や実装段階")

この資料は、アップグレード、旅の導入と展開の段階の一部です。 進む前に、次のアクティビティを完了したしたことを確認します。

-   [プロジェクトの利害関係者が参加しています。](upgrade-enlist-stakeholders.md)
-   [プロジェクト スコープの定義](https://aka.ms/SkypetoTeams-Scope)
-   [ビジネスとチームの共存と Skype の相互運用性を理解します。](https://aka.ms/SkypeToTeams-Coexist)
-   [アップグレード、旅を選択](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [環境を準備](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [組織の準備](https://aka.ms/SkypeToTeams-UserReadiness)
-   [パイロットを実施しました。](https://aka.ms/SkypeToTeams-Pilot)


# <a name="upgrade-from-skype-for-business-online-to-teams"></a>チームをオンラインでビジネス用の Skype からのアップグレード

完全 Skype をオンライン ビジネスを展開しているし、ビジネスの Skype からのチームにユーザーをアップグレードする場合のこの資料の指示に従います。 ユーザーを選択的にアップグレードすることができますまたはアップグレードをに基づいて、オールインワンの旅を適切な共存およびアップグレード モードをユーザーに割り当てることにより、組織が選択されます。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>共存およびアップグレード モードを割り当てる

ビジネス管理センターまたは、Skype のビジネス リモートの Windows Powershell セッションでマイクロソフトのチームと Skype を使用して実行することができる TeamsUpgradePolicy の TeamsOnly モードを割り当てることによって、チームがユーザーをアップグレードできます。

詳細についてを参照してください[、共存を設定および設定をアップグレード](https://aka.ms/SkypeToTeams-SetCoexistence)し、 [TeamsUpgradePolicy: 移行と共存を管理する](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>チームにすべてのユーザーを同時にアップグレードします。

この手順では、一度に 1 つのチームにすべてのユーザーをアップグレードします。

### <a name="step-1-notify-the-users-of-the-change"></a>手順 1: ユーザーに変更を通知します。 

1. マイクロソフトのチームと Skype ビジネス管理センターは、**組織全体の設定**を選択します > **のチームをアップグレード**します。 
2. **共存モード**では、[**上**に**チームへのアップグレードが利用可能なビジネス ・ ユーザーの通知の Skype**のスイッチを変更します。

### <a name="step-2-set-the-coexistence-mode-for-the-users"></a>ステップ 2: ユーザーの共存モードを設定します。 

1. マイクロソフトのチームと Skype ビジネス管理センターは、**組織全体の設定**を選択します。 
2. **共存モード**」ドロップ ダウン リストから**チームのみ**のモードを選択します。
 
## <a name="upgrade-users-in-stages"></a>ユーザーを段階的にアップグレードします。

チームにユーザーを段階的にアップグレードする場合は、以下の手順を実行します。

### <a name="step-1-create-your-user-cohorts-for-the-upgrade"></a>手順 1: アップグレードのため、ユーザーの cohorts を作成します。 

Cohorts のユーザーは、同時にチームのみのモードに移動するユーザーのグループです。  

ユーザーの cohorts (追加のユーザーの選択] ページへのリンク) を作成するには
 
### <a name="step-2-set-the-user-mode-to-islands"></a>ステップ 2: 島へのユーザー モードを設定します。 

1. マイクロソフト チーム/Skype のビジネス管理センターで、**ユーザー**を選択し、ユーザーの cohort します。
2. **チームのアップグレード**をするには、横の**編集**を選択します。
3. **共存モード**では、下の**チームのアップグレード**ウィンドウのドロップ ダウン リストから**島**を選択します。 

### <a name="step-3-set-notification-for-the-user-optional"></a>ユーザーの通知を設定 (省略可能) 手順 3。 

1. マイクロソフト チームとビジネス管理センターの Skype では、**ユーザー**を選択し、ユーザー cohort を選択します。
2. **チームのアップグレード**をするには、横の**編集**を選択します。
3. **共存モード**では、下の**チームのアップグレード**ウィンドウの**上**に**通知 Skype ビジネス ユーザーの**スイッチを変更します。

### <a name="step-4-set-the-user-mode-to-teams-only"></a>手順 4: チームのみに、ユーザー モードを設定します。 

唯一のアプリケーションとして、チームを使用するユーザーをアップグレードする準備ができたら、チームだけにユーザーの共存モードを設定します。  

1. マイクロソフト チーム/Skype のビジネス管理センターで、**ユーザー**を選択し、ユーザーの cohort します。
2. **チームのアップグレード**をするには、横の**編集**を選択します。
3. **チームのアップグレード**ウィンドウの [、**共存モード**では、ドロップ ダウン リストからの**チームのみ**を選択します。 

## <a name="phone-system-and-teams-upgrade"></a>電話システムとチームのアップグレード

場合は、オンライン ビジネスの展開、Skype には、計画を呼び出すと、電話システムが含まれています、、公衆交換電話網 (PSTN) プロバイダーが、チームにユーザーをアップグレードするは自動的に移行チームを呼び出す PSTN を受信します。

オンライン ビジネス展開するため、Skype には、クラウドのコネクタのエディションでの電話システムが含まれている場合は、[電話システムの直接のルーティングのための追加の考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。