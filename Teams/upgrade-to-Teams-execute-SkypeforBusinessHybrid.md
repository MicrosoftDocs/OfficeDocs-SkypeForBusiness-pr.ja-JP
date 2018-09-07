---
title: ビジネスのハイブリッド展開するため、Skype からチームのチームで Microsoft にアップグレードします。
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: ビジネスのハイブリッド展開するため、Skype からチームへのアップグレードに関する考慮事項
localization_priority: Priority
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8519f9fd79d15e7b1ebc5cc3fc5aa05b7e9e9112
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23868174"
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

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>ビジネスのハイブリッド展開するため、Skype からチームへのアップグレードします。

Skype のビジネスを展開しているや Microsoft Lync の設置型と、Office 365 のテナントのハイブリッド展開を構成して、組織がアップグレードのチームにするか、選択的にする場合この資料の指示に従います: 複数を使用して、共存モード、またはオールインワン。 いずれかのアップグレードの旅 (それらは既にホーム サーバーの場合オンライン) は、オンライン ビジネスの Skype にユーザーを移動し、それらの適切な共存およびアップグレード モードが必要です。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>手順 1: Skype をオンライン ビジネスのユーザーを移動します。

この手順は、オンプレミスで現在のホーム ユーザーに適用されます。 ビジネス オンラインの Skype にこれらのユーザーを移動する方法の詳細については、[上の Skype ビジネスをオンラインにするには、社内設置型からユーザーを移動](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)を参照してください。

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>手順 2: は、共存を割り当てるし、モードのアップグレード

Skype をオンライン ビジネスのユーザーに移動した、割り当てることができます、組織が選択したアップグレードの旅に基づく適切な共存モードです。 詳細についてを参照してください[、共存を設定および設定をアップグレード](https://aka.ms/SkypeToTeams-SetCoexistence)し、 [TeamsUpgradePolicy: 移行と共存を管理する](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

> [!NOTE]
> ビジネス サーバー 2019 およびビジネス サーバー 2015 の Skype の今後の累積的な更新プログラムの Skype でことができます (ユーザーの Skype をオンライン ビジネスの移動) ステップ 1 とステップ 2 (チームへのアップグレードのユーザー) を 1 ステップで実行します。 詳細については、ビジネス サーバー 2019 の Skype のリリース後に提供されます。

## <a name="phone-system-and-teams-upgrade"></a>電話システムとチームのアップグレード

ビジネスのハイブリッド展開計画を呼び出すと、電話システムには、Skype に移行しているし、Microsoft は、公衆交換電話網 (PSTN) プロバイダーになる場合、電話番号の移植が完了したことを前提として、-にユーザーをアップグレードします。チームは、チームを呼び出す受信の PSTN と自動的に遷移させます。

計画を呼び出すことがない、または、既存の PSTN 接続のプロバイダーを使用する、エンタープライズ ボイス展開に移行する必要があります- または、既存を使用するハイブリッド ボイスの展開設置型展開またはクラウド コネクタ エディション-にマイクロソフトの電話システムでは、ルーティングを指示します。 チームにユーザーをアップグレードするには、[電話システムの直接のルーティングのための追加の考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。
