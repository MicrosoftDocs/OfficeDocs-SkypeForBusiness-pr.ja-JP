---
title: Skype for Business オンプレミスから Teams にアップグレードする
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Skype for Business オンプレミス展開から組織を Microsoft Teams に移行する方法について説明します。
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
ms.openlocfilehash: 90542f680c1d3992f5f318bfedad8a12470d282b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820947"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Skype for Business オンプレミス展開から Teams にアップグレードする

![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、アップグレードの手順の展開と実装のステージの一部です。 続く前に、次のアクティビティを完了したと確認します。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
- [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [環境を準備した](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [組織を準備した](https://aka.ms/SkypeToTeams-UserReadiness)
- [パイロットを実施した](https://aka.ms/SkypeToTeams-Pilot)

Skype for Business または Microsoft Lync をオンプレミスに展開し、組織が複数の共存モードを使用して Microsoft Teams にアップグレードする場合、またはすべてのモードを使用する場合は、この記事のガイダンスに従います。 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>手順 1: ハイブリッド接続の展開

ユーザーを Teams にアップグレードする際の重要な前提条件は、ハイブリッド接続を展開することです。

詳細については、「Skype for Business Server と Skype for Business Online の間にハイブリッド接続を展開する[」を参照してください](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)。

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>手順 2: 組織に対して選択したアップグレードの手順を実装する

ハイブリッド セットアップが完了したら、ユーザーを Microsoft 365 または Office 365 に移行することができます。

詳細については、以下を参照してください。

- [TeamsUpgradePolicy: 移行と共存の管理](upgrade-to-teams-on-prem-tools.md)。

- [オンプレミスから Skype for Business Online にユーザーを移動します](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="phone-system-and-teams-upgrade"></a>電話システムと Teams のアップグレード

オンプレミスの電話システムから Teams に移行すると、電話システムダイレクト ルーティング ("ダイレクト ルーティング") または Microsoft が提供する Microsoft 365 または Office 365 の通話プランを利用できます。

通話プランを使用していない場合は、Teams へのアップグレードの一環として、エンタープライズ 音声展開を電話システム ダイレクト ルーティングに移行する必要があります。

詳細については、電話システム ダイレクト [ルーティングに関するその他の考慮事項を参照してください](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing)。 通話プランを使用する予定の場合は、電話番号を Teams に移行する方法のガイダンス [を参照してください](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。