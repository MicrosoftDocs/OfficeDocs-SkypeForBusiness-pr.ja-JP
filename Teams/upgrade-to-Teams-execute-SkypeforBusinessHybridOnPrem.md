---
title: オンプレミスの Skype for Business を Microsoft Teams にアップグレードする
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business オンプレミス展開から組織を Microsoft Teams にアップグレードする方法について説明します。
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
ms.openlocfilehash: 7bd7d2fad4e4c35a26bcbb435caba5898dd54534
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397552"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Skype for Business オンプレミスから Teams にアップグレードする

![展開と実装に重点を置いた、アップグレードのフロー図](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 先に進む前に、次のアクティビティを完了していることを確認してください。

-   [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
-   [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
-   [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)
-   [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [環境を準備した](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [組織を準備した](https://aka.ms/SkypeToTeams-UserReadiness)
-   [パイロットを実施した](https://aka.ms/SkypeToTeams-Pilot)

Skype for Business Server または Microsoft Lync をオンプレミスに展開し、組織が Teams にアップグレードする場合は、この記事のガイダンスに従います。 Microsoft 365 または Office 365 組織とのハイブリッド接続をセットアップし、ユーザーを複数のフェーズで Teams に移行する場合は、共存要件を決定する必要があります。

始める前に、IT 管理者と IT 管理者は、この記事の後半で [Skype for Business Server](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) オンプレミスの組織に関する重要な考慮事項を確認する必要があります。

> [!IMPORTANT]
> Skype for Business Online は 2021 年 7 月 31 日に廃止される予定です。それ以降、アクセスとサポートが終了します。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。 アップグレードが成功すると、技術面およびユーザーの準備が整ったことになります。Microsoft Teams への移行を進める際には、必ずこのガイドを活用してください。

## <a name="step-1-configure-hybrid-connectivity"></a>手順 1: ハイブリッド接続の構成 

オンプレミスのユーザーを Teams にアップグレードするため主な前提条件は、Skype for Business Server のオンプレミス展開にハイブリッド接続を構成することです。 

まず、「 [ハイブリッド接続のプラン](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)」をご覧になり、「[ハイブリッド接続の構成](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)」で説明されているタスクを実行します。


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>手順 2: 移行中の共存モードを設定する (省略可能)

Skype for Business、Teams クライアント、およびユーザーの間の共存と相互運用性は、Teams のアップグレード モードによって規定されます。  既定では、組織はアイランド モードになっており、ユーザーは Teams と Skype for Business の両方を併用できます。

Teams に移行する組織にとって、最終的にはすべてのユーザーを TeamsOnly モードにすることが目標ですが、TeamsOnly (またはその他のモード) を全員に同時に割り当てる必要はありません。

ユーザーが TeamsOnly モードに到達するまでは、組織は Skype for Business 共存モードのいずれかのモードを使用するという選択肢があり、こうすることで、TeamsOnly モードのユーザーとまだこのモードに設定されていないユーザーの間で、安定した通信を確保できます。  Skype for Business 共存モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) の目的は、組織が Skype for Business から Teams に移行する際に、シンプルで予測可能なエクスペリエンスをエンド ユーザーに提供することです。 

ユーザーが Skype for Business モードの場合、すべての着信チャットと通話がユーザーの Skype for Business クライアントにルーティングされます。 ユーザーがいずれかの Skype for Business モードに設定されている場合、エンド ユーザーを混乱させない適切なルーティングを確保するために、Teams クライアントの通話とチャット機能は無効化されます。 同様に、Teams での会議のスケジュールも、ユーザーが SfBOnly または SfBWithTeamsCollab モードの場合は明示的に無効化され、ユーザーが SfBWithTeamsCollabAndMeetings の場合には明示的に有効化されます。

組織の要件によりますが、組織が選択したアップグレード パスに基づいて適切な共存モードを割り当てることができます。 詳細については、「[Migration and interoperability guidance for organizations using Teams together with Skype for Business (Teams を Skype for Business と併用する組織向けの移行と相互運用に関するガイダンス)](migration-interop-guidance-for-teams-with-skype.md)」および「[共存およびアップグレードの設定 (Setting your coexistence and upgrade settings)](https://aka.ms/SkypeToTeams-SetCoexistence)」を参照してください。


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>手順 3: ユーザーを Skype for Business オンプレミスから TeamsOnly に移動する

最終的には、ユーザーを TeamsOnly モードに移動します。 これには、オンプレミス環境によっては、1 から 2 つの手順が必要になる場合があります。  

詳細については、「 [オンプレミスとクラウドの間でユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)」と「[オンプレミスから Teams にユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)」を参照してください。 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>手順 4: ハイブリッドを無効にしてクラウドへの移行を完了する

すべてのユーザーをオンプレミスからクラウドに移行した後は、オンプレミスの Skype for Business 展開の使用を停止できます。 詳細については、「ハイブリッドを無効 [にしてクラウドへの移行を完了する」を参照してください](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)。


## <a name="phone-system-and-pstn-connectivity-options"></a>電話システムと PSTN 接続オプション

Teams の電話システムは、ユーザーが TeamsOnly モードに切り替えた後にサポートされます。 (ユーザーが諸島モードの場合、電話システムは Skype for Business でのみサポートされます)。 

### <a name="pstn-connectivity-options"></a>PSTN 接続オプション

公衆交換電話網 (PSTN) 接続オプションを検討する場合、オンプレミスの Skype for Business から TeamsOnly モードに移行する場合、次の 2 つのシナリオが考えられます。

- エンタープライズ VoIP を使用している Skype for Business オンプレミスのユーザーのうち、オンラインに移行して、Microsoft 通話プランを使用するユーザー。 このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行を A) Microsoft 通話プランへのユーザーの電話番号のポートに合わせて調整するか、B) 利用可能な地域から新しいサブスクライバー番号を割り当てる必要があります。  詳細については、オンプレミスの Skype for Business Server から microsoft 通話プラン [エンタープライズ VoIPを参照してください](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)。

- エンタープライズ VoIP を使用している Skype for Business オンプレミスのユーザーのうち、オンラインに移行して、オンプレミスの PSTN 接続を維持するユーザー。 このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行をそのユーザーのダイレクト ルーティングへの移行に合わせて調整する必要があります。 詳細については、「オンプレミスの Skype for Business Server から、オンプレミス、および直接ルーティングエンタープライズ VoIP [を参照してください](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>オンプレミスの Skype for Business Server を使用している組織に関する重要な考慮事項

- 次の記事では、アップグレードの重要な概念と共存動作について説明します。
    - [Teams と Skype for Business の共存](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [共存モード - リファレンス](migration-interop-guidance-for-teams-with-skype.md)
    - [Teams のクライアント エクスペリエンスおよび共存モードへの準拠](teams-client-experience-and-conformance-to-coexistence-modes.md)

- Skype for Business Hybrid のセットアップは、TeamsOnly モードへの移行の前提条件です。 ハイブリッドを使用せずにアイランド モードで Teams を使用することは可能ですが、そのユーザーが Skype for Business オンプレミスから Skype for Business Online に移行されるまで ([Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) を使用して) は、TeamsOnly モードには移行できません。 詳細については、「[ハイブリッド接続を構成する](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)」を参照してください。

- 組織が Skype for Business Server を使用しているが、ハイブリッド接続を構成していないが、Teams を使用する必要がある場合は、Teams の機能を管理するには、.onmicrosoft.com ドメインを持つ管理アカウントを使用する必要があります。 

- オンプレミスの Skype for Business アカウントを所有している Teams ユーザー (つまり、Move-CsUser を使用してクラウドにまだ移行していないユーザー) は、Skype for Business ユーザーとの相互運用や、外部ユーザーとのフェデレーションを行うことができません。 この機能は、そのユーザーがクラウドに移行した場合 (アイランド モードか TeamsOnly ユーザーとして) にのみ利用できます。 

- Skype for Business アカウントを持つユーザーがオンプレミスにある場合、テナント レベルで TeamsOnly モードを割り当てすることはできません。 最初にオンプレミスの Skype for Business アカウントを持つすべてのユーザーを使用してクラウドに移動し、ハイブリッドを無効にしてクラウドへの移行 `Move-CsUser` [を完了する必要があります](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)。  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` 365 以外の場所をポイントしている lyncdiscover DNS レコードが検出された場合、テナント レベルOfficeされません。

- ユーザーが適切な Skype for Business 属性を使用して Azure AD に正しく同期されていることを確認する必要があります。 これらの属性すべてには、プレフィックスとして msRTCSIP- が付きます。 ユーザーが Azure AD に正しく同期されていない場合、Teams の管理ツールでそのユーザーを管理できなくなります。 (たとえば、これらの属性を適切に同期しない限り、Teams ポリシーをオンプレミス ユーザーに割り当てできません)。詳細については、「Azure AD Teams と Skype for Business の接続 [を構成する」を参照してください](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)。

- ハイブリッド組織で新しい TeamsOnly ユーザーや Skype for Business Online のユーザーを作成するには、*最初にユーザーを Skype for Business Server オンプレミスで有効にしてから*、その後に、そのユーザーを Move-CsUser を使用してオンプレミスからクラウドに移行する必要があります。  最初にオンプレミスでユーザーを作成することにより、残りのオンプレミスの Skype for Business ユーザーは新しく作成されたユーザーに確実にルーティングできるようになります。 すべてのユーザーのオンラインへの移行が完了しているなら、最初にオンプレミスでユーザーを有効にする必要はありません。

- オンプレミスからクラウドにユーザーが移行されると、そのユーザーによって開催される会議は、-MoveToTeams スイッチが指定されているかどうかに基づいて、Skype for Business Online か Teams のいずれかに移行されます。

- オンプレミスのユーザーに対して Skype for Business クライアントで通知を表示する場合は、オンプレミスのツールセットで TeamsUpgradePolicy を使用する必要があります。 オンプレミスのユーザーに関係があるのは、NotifySfbUsers パラメーターのみです。  オンプレミスのユーザーは、TeamsUpgradePolicy のオンライン インスタンスから自分のモードを受け取ります。 「[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)」のメモを参照してください。 

>[!NOTE]
> 2019 年 9 月 3 日より後に作成された新しいテナントは、組織に Skype for Business Server のオンプレミス展開が既に存在しない限り、TeamsOnly テナントとして作成されます。 Microsoft は DNS レコードを使用して、オンプレミスの Skype for Business Server 組織を識別します。 組織にパブリック DNS エントリがないオンプレミスの Skype for Business Server がある場合は、Microsoft サポートに連絡して新しいテナントをダウングレードする必要があります。 

## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md) 

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[オンプレミスとクラウドの間でユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[会議移行サービス (MMS) を使用する](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)