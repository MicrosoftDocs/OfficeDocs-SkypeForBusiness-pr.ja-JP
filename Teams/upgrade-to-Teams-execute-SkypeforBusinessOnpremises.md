---
title: ビジネス設置型展開で、Skype からチームのチームで Microsoft にアップグレードします。
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: ビジネス上の設置型展開チームに、Skype のアップグレードに関する考慮事項
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd0d0f1536f509f2cdc9e379e398168f86d9b514
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016782"
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


# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>ビジネス設置型展開で、Skype からチームへのアップグレードします。

Skype のビジネスを展開している Microsoft Lync の設置型や組織がアップグレードのチームにするか、選択的にする場合この資料の指示に従います: 複数の共存モードを使用して- またはオールインワン。 最初の手順は、Office 365 のテナントとのハイブリッド接続の設定し Skype をオンライン ビジネスのユーザーを移動し、適切な共存を割り当てるし、モードのアップグレードには。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>手順 1: ハイブリッド接続を展開します。

チームにユーザーをアップグレードするためのキーの必要条件では、ハイブリッドの接続を展開します。 既存の Skype ビジネスまたは Lync の展開用の新しい外部接続を展開するか、Office 365 テナントにハイブリッドの関係を構成するだけ、この関数が含まれます。

詳細については、[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間のハイブリッド接続の展開](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)を参照してください。

## <a name="step-2-move-users-to-skype-for-business-online"></a>手順 2: Skype をオンライン ビジネスのユーザーを移動します。

ハイブリッドの設定が完了したら後、は、オンライン ビジネスの Skype にユーザーを移動します。 

詳細については、[ビジネス オンラインの Skype を施設内でのユーザーの移動](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)を参照してください。

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>手順 3: は、共存を割り当てるし、モードのアップグレード

Skype をオンライン ビジネスのユーザーに移動した、割り当てることができます、組織が選択したアップグレードの旅に基づく適切な共存モードです。 詳細についてを参照してください[、共存を設定および設定をアップグレード](https://aka.ms/SkypeToTeams-SetCoexistence)し、 [TeamsUpgradePolicy: 移行と共存を管理する](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

> [!NOTE]
> ビジネス サーバー 2019 およびビジネス サーバー 2015 の Skype の今後の累積的な更新プログラムの Skype でことができます (ユーザーの Skype をオンライン ビジネスの移動)、ステップ 2 とステップ 3 (チームへのアップグレードのユーザー) を 1 ステップで実行します。 詳細については、ビジネス サーバー 2019 の Skype のリリース後に提供されます。

## <a name="phone-system-and-teams-upgrade"></a>電話システムとチームのアップグレード

エンタープライズ ボイスの計画を呼び出すと、電話システムにビジネスの設置を展開するため、Skype に移行しているし、Microsoft は、公衆交換電話網 (PSTN) プロバイダーになる場合、電話番号を完了したことを前提として、移植-チームにユーザーをアップグレードすると、チームへのインバウンドの PSTN 通話は自動的に移行します。

計画を呼び出すことがない場合は、マイクロソフト電話システム直接ルーティングするのには、エンタープライズ ボイスの展開に移行する必要があります。 チームにユーザーをアップグレードするには、[電話システムの直接のルーティングのための追加の考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。