---
title: Skype for Business オンプレミスから Teams にアップグレードする
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Skype for Businessのオンプレミス展開から組織をMicrosoft Teamsに移行する方法について説明します。
ms.localizationpriority: medium
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
ms.openlocfilehash: ff82f4e36332f138e67156ca450fc6071c28d234
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62419320"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Skype for BusinessのオンプレミスデプロイからTeamsにアップグレードする

![「展開と実装」段階が強調表示された、アップグレード行程の各段階。](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、アップグレード体験のデプロイと実装の段階の一部です。 先に進む前に、次のアクティビティを完了していることを確認してください。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](./upgrade-define-project-scope.md)
- [Skype for Business と Teams の共存と相互運用を理解した](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [環境を準備した](./upgrade-prepare-environment.md)
- [組織を準備した](./upgrade-prepare-organization.md)
- [パイロットを実施した](./pilot-essentials.md)

Skype for Businessまたは Microsoft Lync をオンプレミスに展開し、組織が複数の共存モードを使用して選択的にMicrosoft Teamsにアップグレードする場合は、この記事のガイダンスに従ってください。 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>手順 1: ハイブリッド接続の展開

ユーザーを Teams にアップグレードする際の重要な前提条件は、ハイブリッド接続を展開することです。

詳細については、「[Skype for Business Serverと Skype for Business Online の間のハイブリッド接続のデプロイ](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)」を参照してください。

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>手順 2: 選択したアップグレード体験を組織に実装する

ハイブリッドセットアップが完了したら、ユーザーをMicrosoft 365またはOffice 365に移動することを計画できます。

詳細については、次を参照してください:

- [TeamsUpgradePolicy: 移行と共存の管理](upgrade-to-teams-on-prem-tools.md)。

- [オンプレミスから Skype for Business Online にユーザーを移動します](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="phone-system-and-teams-upgrade"></a>電話システムと Teams のアップグレード

オンプレミスの電話システムからTeamsに移行すると、電話システムダイレクト ルーティング ("ダイレクト ルーティング") またはMicrosoft 365またはOffice 365用の Microsoft 提供の通話プランを利用できます。

通話プランを使用していない場合は、Teamsへのアップグレードの一環として、エンタープライズ音声展開を電話システムダイレクト ルーティングに移行する必要があります。

詳細については、[電話システム ダイレクト ルーティングに関するその他の考慮事項を](./direct-routing-landing-page.md)参照してください。 通話プランを使用する予定の場合は、[電話番号をTeamsに転送するためのガイダンスを](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)参照してください。