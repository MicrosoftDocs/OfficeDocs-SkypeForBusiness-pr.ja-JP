---
title: Skype for Business ハイブリッド展開を Microsoft Teams にアップグレードする |SIP-PSTN
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Skype for Business ハイブリッド展開から Teams にアップグレードする場合の考慮事項
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
ms.openlocfilehash: ca9ebc7a28e07eec9b24c0628ade4941c0fd2fa2
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706697"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Skype for Business ハイブリッド展開から Teams にアップグレードする

![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 続行する前に、次の作業が完了していることを確認します。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
- [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [環境を準備した](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [組織を準備した](https://aka.ms/SkypeToTeams-UserReadiness)
- [パイロットを実施した](https://aka.ms/SkypeToTeams-Pilot)

この記事のガイダンスに従って、Skype for Business または Microsoft Lync をオンプレミスで展開し、Office 365 テナントでハイブリッド展開で構成している場合は、複数のユーザーを使用して、組織で選択的にチームにアップグレードすることを希望しています。共存モード (またはすべて) アップグレードの過程では、ユーザーを Skype for Business Online に移行する必要があり (まだオンラインになっていない場合)、適切な共存とアップグレードモードを割り当てます。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>手順 1: ユーザーを Skype for Business Online に移動する

この手順は、現在オンプレミスのホームユーザーに適用されます。 これらのユーザーを Skype for Business Online に移行する方法の詳細については、「[オンプレミスから skype For Business online にユーザーを移行する](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)」を参照してください。

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>手順 2: 共存とアップグレードモードを割り当てる

ユーザーを Skype for Business Online に移行した後は、組織が選択したアップグレードの過程に基づいて適切な共存モードを割り当てることができます。 詳細については、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」および「[TeamsUpgradePolicy: 移行と共存の管理](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)」を参照してください。

> [!NOTE]
> Skype for Business Server 2019 および今後の Skype for Business Server 2015 の累積的な更新プログラムでは、手順 1 (ユーザーを Skype for Business Online に移行する) と手順 2 (ユーザーを Teams にアップグレードする) を1つの手順で実行できます。 詳細については、Skype for Business Server 2019 のリリース後に発表されます。

## <a name="phone-system-and-teams-upgrade"></a>電話システムと Teams のアップグレード

Skype for Business ハイブリッド展開を電話システムに移行している場合に、Microsoft が PSTN (公衆交換電話網) プロバイダーとなり、電話番号の移行が完了したことを前提としています。チームは着信 PSTN 通話を Teams に自動的に切り替えます。

通話プランを利用できない場合、または既存の PSTN 接続プロバイダーを使用する場合は、エンタープライズ voip 展開 (または既存のオンプレミス展開またはクラウドコネクタエディションを使用するハイブリッド音声の展開) に移行する必要があります。Microsoft Phone システムのダイレクトルーティング。 ユーザーを Teams にアップグレードする場合は、[電話システム ダイレクト ルーティングに関する考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。
