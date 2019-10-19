---
title: Skype for Business オンプレミス展開から Teams にアップグレードする-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business オンプレミスの展開から Teams にアップグレードする場合の考慮事項
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b41e716bb115d84b38aa5f2ead25d6347e2e0f1a
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "37396423"
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

# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>オンプレミスの Skype for Business から Teams へのアップグレード

Skype for Business Server または Microsoft Lync をオンプレミスで展開していて、組織が Teams にアップグレードする必要がある場合は、この記事のガイダンスに従ってください。 ユーザーを段階的にチームに移行する場合は、Office 365 テナントとのハイブリッド接続をセットアップして、共存の要件を特定する必要があります。 

> [!IMPORTANT]
> Skype for Business Online は、2021年7月31日に廃止されます。その後、アクセスまたはサポートされなくなります。 給付金を最大限に活用し、組織がアップグレードを実装するための適切な時間を確保するために、Microsoft Teams の現在の旅を開始することをお勧めします。 アップグレードが正常に完了した場合は、技術的かつユーザーの準備ができていることに注意してください。このガイドは、Microsoft Teams への旅に進むときに必ずご利用ください。

## <a name="step-1-configure-hybrid-connectivity"></a>手順 1: ハイブリッド接続を構成する 

オンプレミスのユーザーを Teams にアップグレードするために必要な重要なポイントは、Skype for Business Server のオンプレミス展開のハイブリッド接続を構成することです。 

まず、 [ハイブリッド接続のプラン](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)を読み、「[ハイブリッド接続を構成する](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)」に記載されているタスクを実行します。


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>手順 2: 移行後の共存モードを設定する (省略可能)

Skype for Business と Teams のクライアント間の共存と相互運用性、およびユーザーは Teams のアップグレードモードによって定義されます。  既定では、組織は諸島モードになっています。これにより、ユーザーは Teams と Skype for Business クライアントの両方を並行して使用できます。

Teams に移動する組織の場合、TeamsOnly モードは各ユーザーの最終的な送信先ですが、すべてのユーザーが同時に Teams Sonly (または他のモード) を割り当てる必要はありません。

ユーザーが teams の唯一のモードに到達する前に、必要に応じて、Skype for Business の共存モードのいずれかを使用して、TeamsOnly モードのユーザーとまだ存在しないユーザーとの間で一貫した通信を行うことができます。  Skype for Business の共存モード (SfBOnly、Sfbwithteams での共同作業、SfBWithTeamsCollabAndMeetings) の目的は、エンドユーザーが Skype for Business からチームに移行するときに、簡単で予測可能なエクスペリエンスを提供することです。 

ユーザーが Skype for Business モードのいずれかに入っている場合、着信するすべてのチャットと通話はユーザーの Skype for Business クライアントにルーティングされます。 ユーザーが Skype for Business モードを使用している場合、エンドユーザーの混乱を回避して、適切なルーティング、チームクライアントの通話、チャット機能を無効にすることができます。 同様に、Teams での会議のスケジュール設定は、ユーザーが SfBOnly または Sfbwithteams・ SfBWithTeamsCollabAndMeetings モードになっているときに明示的に無効にし、ユーザーがモードにあるときに明示的に有効にします。

要件に応じて、組織が選択したアップグレードパスに基づいて適切な共存モードを割り当てることができます。 詳細については、「[チームと Skype For business を組み合わせて使用する組織向けの移行と相互運用性](migration-interop-guidance-for-teams-with-skype.md)に関するガイダンス」および「[共存とアップグレードの設定](https://aka.ms/SkypeToTeams-SetCoexistence)」を参照してください。


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>手順 3: Skype for Business のオンプレミスからチームのみにユーザーを移動する

最終的には、ユーザーを TeamsOnly モードに移動することができます。 これには、現在のオンプレミス環境に応じて、1つまたは2つの手順が含まれている場合があります。  

詳細については、「 [オンプレミスとクラウドの間でユーザーを移動](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)する」および「[オンプレミスからチームへのユーザーの移動](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)」を参照してください。 



## <a name="phone-system-and-teams-upgrade"></a>電話システムと Teams のアップグレード

通話プランを使用して Skype for Business の展開を電話システムに移行している場合は、Microsoft が公衆交換電話網 (PSTN) プロバイダーになります。 電話番号の移植を完了したことを前提としています。ユーザーを Teams にアップグレードすると、着信 PSTN 通話が Teams に自動的に移行されます。

Skype for Business の展開を電話システムに移行していて、通話プランを使用していない場合は、エンタープライズ voip 展開を Microsoft Phone システムのダイレクトルーティングに切り替える必要があります。 詳細については、「[電話システムのダイレクトルーティング](direct-routing-landing-page.md)」を参照してください。
