---
title: オンプレミスの Skype for Business を Microsoft Teams にアップグレードする |展開 |Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Skype for Business のオンプレミス環境から Teams にアップグレードする際の考慮事項。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb6815c805c9f5bcf47d6ee88a6c43c559b932d3
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706647"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Skype for Business オンプレミスの展開から Teams にアップグレードする

![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、アップグレード過程の展開と実装の段階に含まれています。 続行する前に、次の作業が完了していることを確認します。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
- [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [環境を準備した](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [組織を準備した](https://aka.ms/SkypeToTeams-UserReadiness)
- [パイロットを実施した](https://aka.ms/SkypeToTeams-Pilot)

オンプレミスの Skype for Business または Microsoft Lync を展開していて、組織が複数の共存モード (またはすべて) を使用して、選択的に Microsoft Teams にアップグレードする場合は、この記事のガイダンスに従ってください。 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>手順 1: ハイブリッド接続の展開

ユーザーを Teams にアップグレードする際の重要な前提条件は、ハイブリッド接続を展開することです。

詳細については、「 [skype For Business Server と skype For Business Online の間にハイブリッド接続を展開](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)する」を参照してください。

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>手順 2: 組織に対して選択したアップグレードを実装する

ハイブリッドセットアップが完了したら、Office 365 にユーザーを移動することを計画できます。

詳細については、以下を参照してください。

- [TeamsUpgradePolicy: 移行と共存を管理](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)します。

- [オンプレミスから Skype For Business Online にユーザーを移動](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)します。

## <a name="phone-system-and-teams-upgrade"></a>電話システムと Teams のアップグレード

オンプレミスの電話システムから Teams への移行では、電話システムのダイレクトルーティング ("直接ルーティング") または Microsoft から提供されている Office 365 の通話プランを利用できます。

Office 365 で通話プランを使用していない場合は、チームへのアップグレードの一環として、エンタープライズボイスの展開を電話システムのダイレクトルーティングに切り替える必要があります。

詳細については、「[電話システムのダイレクトルーティングに関するその他の考慮事項](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing)」を参照してください。 Office 365 での通話プランの使用を計画している場合は、「[チームに電話番号を移行](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)する」のガイダンスを参照してください。