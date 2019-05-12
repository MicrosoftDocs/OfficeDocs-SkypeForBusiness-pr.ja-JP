---
title: マイクロソフトのチームへのハイブリッド展開のビジネス用の Skype のアップグレードします。PSTN
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: ビジネスのハイブリッド展開するため、Skype からチームへのアップグレードに関する考慮事項
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c043d870c719d4427494ab24dade4f733febf5d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926116"
---
![展開と実装の段階に重点を置いた、アップグレード手順の各段階](media/upgrade-banner-deployment.png "展開と実装の段階に重点を置いた、アップグレード手順の各段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 先に進む前に、次のアクティビティを完了していることを確認してください。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
- [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [環境を準備した](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [組織を準備した](https://aka.ms/SkypeToTeams-UserReadiness)
- [パイロットを実施した](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>ビジネスのハイブリッド展開するため、Skype からチームへのアップグレードします。

Skype のビジネスを展開しているや Microsoft Lync の設置型と、Office 365 のテナントのハイブリッド展開を構成して、組織がアップグレードのチームにするか、選択的にする場合この資料の指示に従います: 複数を使用して、共存モード、またはオールインワン。 いずれかのアップグレードの旅 (それらは既にホーム サーバーの場合オンライン) は、オンライン ビジネスの Skype にユーザーを移動し、それらの適切な共存およびアップグレード モードが必要です。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>手順 1: Skype をオンライン ビジネスのユーザーを移動します。

この手順は、オンプレミスで現在のホーム ユーザーに適用されます。 ビジネス オンラインの Skype にこれらのユーザーを移動する方法の詳細については、[上の Skype ビジネスをオンラインにするには、社内設置型からユーザーを移動](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)を参照してください。

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>手順 2: は、共存を割り当てるし、モードのアップグレード

Skype for Business Online にユーザーを移動したら、組織が選択したアップグレードの手順に応じて、ユーザーに適切な共存モードを割り当てます。 詳細については、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」および「[TeamsUpgradePolicy: 移行と共存の管理](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)」を参照してください。

> [!NOTE]
> ビジネス サーバー 2019 およびビジネス サーバー 2015 の Skype の今後の累積的な更新プログラムの Skype でことができます (ユーザーの Skype をオンライン ビジネスの移動) ステップ 1 とステップ 2 (チームへのアップグレードのユーザー) を 1 ステップで実行します。 詳細については、Skype for Business Server 2019 のリリース後に発表されます。

## <a name="phone-system-and-teams-upgrade"></a>電話システムと Teams のアップグレード

Skype for Business のハイブリッド展開を通話プラン付きの電話システムに移行して、Microsoft が公衆交換電話網 (PSTN) プロバイダーになる場合、電話番号持ち運びの手続きを完了していれば、ユーザーを Teams にアップグレードすることで、着信 PSTN 通話は自動的に Teams に移行されます。

計画を呼び出すことがない、または、既存の PSTN 接続のプロバイダーを使用する、エンタープライズ ボイス展開に移行する必要があります- または、既存を使用するハイブリッド ボイスの展開設置型展開またはクラウド コネクタ エディション-にマイクロソフトの電話システムでは、ルーティングを指示します。 ユーザーを Teams にアップグレードする場合は、[電話システム ダイレクト ルーティングに関する考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。
