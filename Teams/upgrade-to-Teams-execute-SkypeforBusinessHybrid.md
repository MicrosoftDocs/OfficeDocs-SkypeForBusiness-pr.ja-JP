---
title: ハイブリッド展開Skype for Business Teams にアップグレードする
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Skype for Businessハイブリッド展開から組織を Microsoft Teams にアップグレードする方法について説明します。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ea8db9f53b891002cf7fbe1f5282051e7aca7ea
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615603"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Skype for Business ハイブリッド展開から Teams へのアップグレード

![「展開と実装」段階が強調表示された、アップグレード行程の各段階。](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 先に進む前に、次のアクティビティを完了していることを確認してください。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](./upgrade-define-project-scope.md)
- [Skype for Business と Teams の共存と相互運用を理解した](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [環境を準備した](./upgrade-prepare-environment.md)
- [組織を準備した](./upgrade-prepare-organization.md)
- [パイロットを実施した](./pilot-essentials.md)

オンプレミスでSkype for Businessまたは Microsoft Lync を展開し、Microsoft 365 またはOffice 365組織とハイブリッド展開で構成し、組織が複数の共存モードを使用して選択的に Teams にアップグレードする場合、またはオールインを使用する場合は、この記事のガイダンスに従ってください。 どちらのアップグレードの道のりでも、ユーザーを Skype for Business Online に移動し (まだオンラインでない場合)、適切な共存モードとアップグレード モードを割り当てる必要があります。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>手順 1: ユーザーを Skype for Business Online に移動する

この手順は、現在オンプレミスに所属しているユーザーに適用されます。 これらのユーザーを Skype for Business Online に移行する方法の詳細については、「[オンプレミスから Skype for Business Online にユーザーを移動する](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)」を参照してください。

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>手順 2: 共存モードとアップグレード モードを割り当てる

ユーザーを Skype for Business Online に移動した後は、組織が選択したアップグレード体験に基づいて、適切な共存モードを割り当てることができます。 詳細については、「[共存およびアップグレードを設定する](./setting-your-coexistence-and-upgrade-settings.md)」および「[TeamsUpgradePolicy: 移行と共存の管理](upgrade-to-teams-on-prem-tools.md)」を参照してください。

> [!NOTE]
> Skype for Business Server 2019 と今後の累積的な更新プログラムである Skype for Business Server 2015 では、1 つの手順で手順 1 (ユーザーをSkype for Business オンラインに移行) と手順 2 (ユーザーを Teams にアップグレード) を実行できます。 詳細については、Skype for Business Server 2019 のリリース後に発表されます。

## <a name="phone-system-and-teams-upgrade"></a>電話システムと Teams のアップグレード

通話プランを使用してSkype for Businessハイブリッド展開を電話システムに移行する場合、Microsoft は公衆交換電話ネットワーク (PSTN) プロバイダーになり、電話番号の移植が完了したと仮定すると、ユーザーを Teams にアップグレードすると、受信 PSTN 通話が Teams に自動的に移行されます。

通話プランを使用できない場合、または既存の PSTN 接続プロバイダーを使用する場合は、エンタープライズ音声展開 (既存のオンプレミス展開またはクラウド コネクタ エディションを使用するハイブリッド音声展開) を Microsoft Phone System Direct Routing に移行する必要があります。 ユーザーを Teams にアップグレードする場合は、[電話システム ダイレクト ルーティングに関する考慮事項](./direct-routing-landing-page.md)を参照してください。