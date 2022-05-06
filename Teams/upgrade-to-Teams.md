---
title: Microsoft Teamsへのアップグレードの実装の概要
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 現在のSkype for Businessデプロイに基づいて、Microsoft Teamsへの最適なアップグレード パスを決定します。
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
ms.openlocfilehash: 2501c113eb3589ba26d4a9a6932e103f913c9239
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730156"
---
# <a name="overview-of-implementing-your-upgrade"></a>アップグレードの実装の概要

![「展開と実装」段階が強調表示された、アップグレード行程の各段階。](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、アップグレード体験のデプロイと実装の段階の一部です。 



## <a name="prerequisite-planning-activities"></a>前提条件計画アクティビティ

> [!IMPORTANT]
> アップグレードの実装に進む前に、アップグレードの計画から始まる計画の内容 [を](upgrade-plan-journey.md) 読んで、すべての前提条件の計画アクティビティが完了していることを確認してください。


- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](./upgrade-define-project-scope.md)
- [Skype for Business と Teams の共存と相互運用を理解した](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [ユーザー パイロットを計画しました](pilot-essentials.md)
- [環境を準備した](./upgrade-prepare-environment.md)
- [組織を準備した](./upgrade-prepare-organization.md)

## <a name="choose-your-upgrade-starting-point"></a>アップグレードの開始点を選択する

Teamsへのアップグレードを実行するために実行する手順は、Skype for Businessの現在のデプロイによって異なります。

現在の環境に基づいて、開始点を選択します。  

- **Skype for Business Online から Teams にアップグレードする場合は**、「[Skype for Business Online から Teamsへのアップグレード](./upgrade-to-teams-execute-skypeforbusinessonline.md)」の手順に従います。

-  **Skype for Businessオンプレミス環境からアップグレードする場合は**、ユーザーをTeamsに移動する前に、オンプレミス環境とオンライン環境の間の接続を設定するための追加の手順をいくつか実行する必要があります。 詳細については、「[オンプレミスSkype for Business Teamsにアップグレードする」を](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)参照してください。





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]