---
title: アプリケーションへのアップグレードの実装のMicrosoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 現在のデプロイに基づいて、Microsoft TeamsアップグレードパスをSkype for Businessします。
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
ms.openlocfilehash: c0794e855fac3f911b028c049289beaa13a571473f32f84509c6d219d92bdd78
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282480"
---
# <a name="overview-of-implementing-your-upgrade"></a>アップグレードの実装の概要

![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、アップグレード体験のデプロイと実装のステージの一部です。 



## <a name="prerequisite-planning-activities"></a>前提条件となる計画アクティビティ

> [!IMPORTANT]
> アップグレードの実装に進む前に、「アップグレードを計画する」から始まる計画コンテンツ[](upgrade-plan-journey.md)を読んで、前提条件となる計画のすべての活動が完了されていることを確認します。


- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](./upgrade-define-project-scope.md)
- [Skype for Business と Teams の共存と相互運用を理解した](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [ユーザー パイロットの計画](pilot-essentials.md)
- [環境を準備した](./upgrade-prepare-environment.md)
- [組織を準備した](./upgrade-prepare-organization.md)

## <a name="choose-your-upgrade-starting-point"></a>アップグレードの開始点を選択する

アプリケーションへのアップグレードを実行する手順は、Teamsのデプロイによって異Skype for Business。

現在の環境に基づいて、開始点を選択します。  

- Skype for Business Online から Teams にアップグレードする場合は **、「Skype for Business Online** から Teams にアップグレードする」の手順に [従います](./upgrade-to-teams-execute-skypeforbusinessonline.md)。

-  **Skype for Business** オンプレミス環境からアップグレードする場合は、ユーザーを Teams に移動する前に、オンプレミス環境とオンライン環境間の接続を設定するための追加の手順を実行する必要があります。 詳細については、「オンプレミスからオンプレミス[へのSkype for Businessアップグレード」を参照Teams。](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]