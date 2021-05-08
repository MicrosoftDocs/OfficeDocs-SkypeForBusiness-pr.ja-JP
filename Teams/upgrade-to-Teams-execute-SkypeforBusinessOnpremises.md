---
title: Skype for Business オンプレミスから Teams にアップグレードする
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 組織をオンプレミスのデプロイからMicrosoft Teams移行Skype for Business方法について説明します。
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
ms.openlocfilehash: 0585f0ad829f19334d5a970461f1f3248a107e9d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115555"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>オンプレミスのデプロイSkype for BusinessからオンプレミスデプロイにアップグレードTeams

![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、アップグレード体験のデプロイと実装のステージの一部です。 先に進む前に、次のアクティビティを完了していることを確認してください。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](./upgrade-define-project-scope.md)
- [Skype for Business と Teams の共存と相互運用を理解した](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [環境を準備した](./upgrade-prepare-environment.md)
- [組織を準備した](./upgrade-prepare-organization.md)
- [パイロットを実施した](./pilot-essentials.md)

Skype for Business または Microsoft Lync をオンプレミスに展開し、組織が複数の共存モードを使用して選択的に Microsoft Teams にアップグレードする場合、またはすべて使用する場合は、この記事のガイダンスに従います。 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>手順 1: ハイブリッド接続の展開

ユーザーを Teams にアップグレードする際の重要な前提条件は、ハイブリッド接続を展開することです。

詳細については、「Deploy [hybrid connectivity between Skype for Business Server and Skype for Business Online 」を参照してください。](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>手順 2: 選択したアップグレード体験を組織に実装する

ハイブリッドセットアップが完了したら、ユーザーを別のユーザーに移行Microsoft 365またはOffice 365。

詳細については、以下を参照してください。

- [TeamsUpgradePolicy: 移行と共存の管理](upgrade-to-teams-on-prem-tools.md)。

- [オンプレミスからオンライン にユーザーをSkype for Businessします](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="phone-system-and-teams-upgrade"></a>電話システムと Teams のアップグレード

オンプレミスの電話システムから Teams に移行すると、電話システム ダイレクト ルーティング ("ダイレクト ルーティング") または Microsoft が提供する Microsoft 365 または Office 365 の通話プランを利用できます。

通話プランを使用していない場合は、アップグレードの一環として、エンタープライズ音声展開を 電話システム 直接ルーティングに移行する必要Teams。

詳細については、「ダイレクト ルーティング[の追加の考慮事項」電話システム参照してください](./direct-routing-landing-page.md)。 通話プランを使用する予定の場合は、電話番号を通話プランに移行する場合のガイダンス[をTeams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)