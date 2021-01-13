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
ms.openlocfilehash: 67bb6c10bb8cc5f37d332459d8e147f4f626497d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802347"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Skype for Business ハイブリッド展開から Teams にアップグレードする

![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 続く前に、次のアクティビティを完了したと確認します。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
- [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [環境を準備した](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [組織を準備した](https://aka.ms/SkypeToTeams-UserReadiness)
- [パイロットを実施した](https://aka.ms/SkypeToTeams-Pilot)

Skype for Business または Microsoft Lync をオンプレミスに展開し、Microsoft 365 または Office 365 組織とのハイブリッド展開で構成し、組織が複数の共存モードを使用するか、すべてインを使用して Teams に選択的にアップグレードする場合は、この記事のガイダンスに従います。 どちらのアップグレードを行う場合も、ユーザーを Skype for Business Online に移動し (ユーザーがオンラインで自宅にいらない場合)、適切な共存モードとアップグレード モードを割り当てる必要があります。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>手順 1: ユーザーを Skype for Business Online に移動する

この手順は、現在オンプレミスに自宅を持っているユーザーに適用されます。 これらのユーザーを Skype for Business Online に移行する方法の詳細については、「ユーザーをオンプレミスから Skype for Business Online に [移動する」を参照してください](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>手順 2: 共存モードとアップグレード モードを割り当てる

ユーザーを Skype for Business Online に移動したら、組織が選択したアップグレードの手順に基づいて、ユーザーに適切な共存モードを割り当てできます。 詳細については、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」および「[TeamsUpgradePolicy: 移行と共存の管理](upgrade-to-teams-on-prem-tools.md)」を参照してください。

> [!NOTE]
> Skype for Business Server 2019 と今後の Skype for Business Server 2015 の累積的な更新プログラムでは、手順 1 (ユーザーを Skype for Business Online に移動) と手順 2 (ユーザーを Teams にアップグレード) を 1 つの手順で実行できます。 詳細については、Skype for Business Server 2019 のリリース後に発表されます。

## <a name="phone-system-and-teams-upgrade"></a>電話システムと Teams のアップグレード

Skype for Business ハイブリッド展開を通話プラン付きの電話システムに移行する場合、Microsoft は公衆交換電話網 (PSTN) プロバイダーになります。電話番号の移行を完了したと仮定すると、ユーザーを Teams にアップグレードすると、受信 PSTN 通話が Teams に自動的に移行されます。

通話プランが利用できない場合、または既存の PSTN 接続プロバイダーを使用する場合は、エンタープライズ 音声展開 (または既存のオンプレミス展開または Cloud Connector エディションを使用するハイブリッド音声展開) を Microsoft Phone System Direct Routing に移行する必要があります。 ユーザーを Teams にアップグレードする場合は、[電話システム ダイレクト ルーティングに関する考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。
