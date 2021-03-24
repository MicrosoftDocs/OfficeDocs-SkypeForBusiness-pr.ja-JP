---
title: Skype for Business ハイブリッド展開を Teams にアップグレードする
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Skype for Business ハイブリッド展開から組織を Microsoft Teams にアップグレードする方法について説明します。
localization_priority: Normal
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
ms.openlocfilehash: 97725e7a9790f47f9789366567981f0167fdd806
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104023"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Skype for Business ハイブリッド展開から Teams にアップグレードする

![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 先に進む前に、次のアクティビティを完了していることを確認してください。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](./upgrade-define-project-scope.md)
- [Skype for Business と Teams の共存と相互運用を理解した](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [環境を準備した](./upgrade-prepare-environment.md)
- [組織を準備した](./upgrade-prepare-organization.md)
- [パイロットを実施した](./pilot-essentials.md)

Skype for Business または Microsoft Lync をオンプレミスに展開し、Microsoft 365 または Office 365 組織とのハイブリッド展開で構成し、組織が複数の共存モードを使用するか、すべてインを使用して Teams に選択的にアップグレードする場合は、この記事のガイダンスに従います。 どちらのアップグレードを行う場合も、ユーザーを Skype for Business Online に移動し (ユーザーがオンラインで自宅にいらない場合)、適切な共存モードとアップグレード モードを割り当てる必要があります。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>手順 1: ユーザーを Skype for Business Online に移動する

この手順は、現在オンプレミスに自宅を持っているユーザーに適用されます。 これらのユーザーを Skype for Business Online に移行する方法の詳細については、「ユーザーをオンプレミスから Skype for Business Online に [移動する」を参照してください](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>手順 2: 共存モードとアップグレード モードを割り当てる

ユーザーを Skype for Business Online に移動した後は、組織が選択したアップグレードの手順に基づいて、ユーザーに適切な共存モードを割り当てできます。 詳細については、「[共存およびアップグレードを設定する](./setting-your-coexistence-and-upgrade-settings.md)」および「[TeamsUpgradePolicy: 移行と共存の管理](upgrade-to-teams-on-prem-tools.md)」を参照してください。

> [!NOTE]
> Skype for Business Server 2019 と今後の Skype for Business Server 2015 の累積的な更新プログラムでは、手順 1 (ユーザーを Skype for Business Online に移動) と手順 2 (ユーザーを Teams にアップグレード) を 1 つの手順で実行できます。 詳細については、Skype for Business Server 2019 のリリース後に発表されます。

## <a name="phone-system-and-teams-upgrade"></a>電話システムと Teams のアップグレード

Skype for Business ハイブリッド展開を通話プラン付きの電話システムに移行する場合、Microsoft は公衆交換電話網 (PSTN) プロバイダーになります。電話番号の移行を完了したと仮定すると、ユーザーを Teams にアップグレードすると、受信 PSTN 通話が Teams に自動的に移行されます。

通話プランが利用できない場合、または既存の PSTN 接続プロバイダーを使用する場合は、エンタープライズ 音声展開 (または既存のオンプレミス展開または Cloud Connector エディションを使用するハイブリッド音声展開) を Microsoft Phone System Direct Routing に移行する必要があります。 ユーザーを Teams にアップグレードする場合は、[電話システム ダイレクト ルーティングに関する考慮事項](./direct-routing-landing-page.md)を参照してください。