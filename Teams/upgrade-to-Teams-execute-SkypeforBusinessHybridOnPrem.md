---
title: Skype for Business オンプレミスから Teams にアップグレードする
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business サーバーまたは Microsoft Lync オンプレミスの展開から Teams へのアップグレードを展開して実装する。
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
ms.openlocfilehash: 24ccbaa0e7f43cdf1ccc816a3839547793c65167
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139626"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Skype for Business オンプレミスから Teams にアップグレードする

![展開と実装に重点を置いた、アップグレードのフロー図](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 続行する前に、次の作業が完了していることを確認します。

-   [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
-   [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
-   [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)
-   [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [環境を準備した](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [組織を準備した](https://aka.ms/SkypeToTeams-UserReadiness)
-   [パイロットを実施した](https://aka.ms/SkypeToTeams-Pilot)

Skype for Business Server または Microsoft Lync をオンプレミスで展開していて、組織が Teams にアップグレードする必要がある場合は、この記事のガイダンスに従ってください。 Office 365 テナントでハイブリッド接続を設定する必要があり、ユーザーを Teams に段階的に移行する場合は、共存の要件を決定する必要があります。 

> [!IMPORTANT]
> Skype for Business Online は 2021 年 7 月 31 日に廃止される予定です。それ以降、アクセスとサポートが終了します。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。 アップグレードが成功すると、技術面およびユーザーの準備が整ったことになります。Microsoft Teams への移行を進める際には、必ずこのガイドを活用してください。

## <a name="step-1-configure-hybrid-connectivity"></a>手順 1: ハイブリッド接続の構成 

オンプレミスのユーザーを Teams にアップグレードするため主な前提条件は、Skype for Business Server のオンプレミス展開にハイブリッド接続を構成することです。 

まず、「 [ハイブリッド接続のプラン](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)」をご覧になり、「[ハイブリッド接続の構成](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)」で説明されているタスクを実行します。


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>手順 2: 移行中の共存モードを設定する (省略可能)

Skype for Business、Teams クライアント、およびユーザーの間の共存と相互運用性は、Teams のアップグレード モードによって規定されます。  既定では、組織はアイランド モードになっており、ユーザーは Teams と Skype for Business の両方を併用できます。

Teams に移行する組織にとって、最終的にはすべてのユーザーを TeamsOnly モードにすることが目標ですが、TeamsOnly (またはその他のモード) を全員に同時に割り当てる必要はありません。

ユーザーが TeamsOnly モードに到達するまでは、組織は Skype for Business 共存モードのいずれかのモードを使用するという選択肢があり、こうすることで、TeamsOnly モードのユーザーとまだこのモードに設定されていないユーザーの間で、安定した通信を確保できます。  Skype for Business 共存モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) の目的は、組織が Skype for Business から Teams に移行する際に、シンプルで予測可能なエクスペリエンスをエンド ユーザーに提供することです。 

ユーザーが Skype for Business モードのいずれかに入っている場合、着信するすべてのチャットと通話はユーザーの Skype for Business クライアントにルーティングされます。 ユーザーがいずれかの Skype for Business モードに設定されている場合、エンド ユーザーを混乱させない適切なルーティングを確保するために、Teams クライアントの通話とチャット機能は無効化されます。 同様に、Teams での会議のスケジュールも、ユーザーが SfBOnly または SfBWithTeamsCollab モードの場合は明示的に無効化され、ユーザーが SfBWithTeamsCollabAndMeetings の場合には明示的に有効化されます。

組織の要件によりますが、組織が選択したアップグレード パスに基づいて適切な共存モードを割り当てることができます。 詳細については、「[Migration and interoperability guidance for organizations using Teams together with Skype for Business (Teams を Skype for Business と併用する組織向けの移行と相互運用に関するガイダンス)](migration-interop-guidance-for-teams-with-skype.md)」および「[共存およびアップグレードの設定 (Setting your coexistence and upgrade settings)](https://aka.ms/SkypeToTeams-SetCoexistence)」を参照してください。


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>手順 3: ユーザーを Skype for Business オンプレミスから TeamsOnly に移動する

最終的には、ユーザーを TeamsOnly モードに移動します。 現在のオンプレミス環境によっては、追加の手順がいくつか必要になる場合があります。  

詳細については、「 [オンプレミスとクラウドの間でユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)」と「[オンプレミスから Teams にユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)」を参照してください。 



## <a name="phone-system-and-teams-upgrade"></a>電話システムと Teams のアップグレード

Skype for Business の展開を通話プランを備えた電話システムに移行する場合、Microsoft は公衆交換電話網 (PSTN) プロバイダーになります。 電話番号の移植を完了したことを前提としています。ユーザーを Teams にアップグレードすると、着信 PSTN 通話が Teams に自動的に移行されます。

Skype for Business の展開を電話システムに移行しているが、通話プランを使用していない場合は、エンタープライズ VoIP 展開を Microsoft 電話システムのダイレクト ルーティングに移行する必要があります。 詳細については、「[電話システムのダイレクト ルーティング](direct-routing-landing-page.md)」を参照してください。
