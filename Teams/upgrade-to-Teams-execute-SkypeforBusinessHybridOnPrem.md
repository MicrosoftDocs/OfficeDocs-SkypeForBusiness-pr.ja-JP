---
title: Skype for Business のハイブリッド環境またはオンプレミス環境から Teams にアップグレードする - Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Skype for Business のハイブリッド環境またはオンプレミス環境から Teams にアップグレードする際の考慮事項。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 873e15e5b1f64e82889bfda6fa30c5b9394dcf3a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235875"
---
![展開と実装を強調したアップグレードの図](media/upgrade-banner-deployment.png "展開と実装のステージに重点を置いたアップグレードの段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 先に進む前に、次のアクティビティを完了していることを確認してください。

-   [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
-   [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
-   [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)
-   [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [環境を準備した](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [組織を準備した](https://aka.ms/SkypeToTeams-UserReadiness)
-   [パイロットを実施した](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a>Skype for Business のハイブリッド環境またはオンプレミス環境から Teams にアップグレードする

オンプレミス環境の Skype for Business または Microsoft Lync を展開していて、組織が選択的 (複数の共存モードを使用) または全体的に Teams にアップグレードする場合は、この記事のガイダンスに従ってください。 最初の手順では、Office 365 テナントとのハイブリッド接続を設定して、ユーザーを Skype for Business Online に移動し、適切な共存およびアップグレード モードをユーザーに割り当てます。 

> [!IMPORTANT]
> Skype for Business Online は、2021年7月31日に廃止されます。その後、アクセスまたはサポートされなくなります。 給付金を最大限に活用し、組織がアップグレードを実装するための適切な時間を確保するために、Microsoft Teams の現在の旅を開始することをお勧めします。 アップグレードが正常に完了した場合は、技術的かつユーザーの準備ができていることに注意してください。このガイドは、Microsoft Teams への旅に進むときに必ずご利用ください。

## <a name="step-1-deploy-hybrid-connectivity"></a>手順 1: ハイブリッド接続の展開 

ユーザーを Teams にアップグレードする際の重要な前提条件は、ハイブリッド接続を展開することです。 このために、既存の Skype for Business または Lync の展開環境に新しい外部接続を展開するか、単に Office 365 テナントとのハイブリッド リレーションシップを構成する必要があります。 

詳細については、「 [Skype for Business Server と Skype for Business Online 間でハイブリッド接続を展開する](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)」を参照してください。

## <a name="step-2-move-users-to-skype-for-business-online"></a>手順 2: Skype for Business Online にユーザーを移動する 

ハイブリッドの設定が完了したら、Skype for Business Online にユーザーを移動します。 

詳細については、「 [ユーザーをオンプレミスから Skype for Business Online に移動する](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)」を参照してください。 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>手順 3: 共存およびアップグレード モードを割り当てる

Skype for Business Online にユーザーを移動したら、組織が選択したアップグレードの手順に応じて、ユーザーに適切な共存モードを割り当てます。 詳細については、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」および「[TeamsUpgradePolicy: 移行と共存の管理](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)」を参照してください。

> [!NOTE]
> Business Server 2019 および Skype for Business Server 2015 の将来の累積的な更新プログラムでは、手順 2 (Skype for Business Online にユーザーを移動する) と手順 3 (ユーザーを Teams にアップグレードする) を 1 つの手順で実行できます。 詳細については、Skype for Business Server 2019 のリリース後に発表されます。

## <a name="phone-system-and-teams-upgrade"></a>電話システムと Teams のアップグレード

Skype for Business のハイブリッド展開を通話プラン付きの電話システムに移行して、Microsoft が公衆交換電話網 (PSTN) プロバイダーになる場合、電話番号持ち運びの手続きを完了していれば、ユーザーを Teams にアップグレードすることで、着信 PSTN 通話は自動的に Teams に移行されます。

通話プランが利用できない場合は、エンタープライズ ボイスを Microsoft 電話システム ダイレクト ルーティングに移行する必要があります。 ユーザーを Teams にアップグレードする場合は、[電話システム ダイレクト ルーティングに関する考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。
