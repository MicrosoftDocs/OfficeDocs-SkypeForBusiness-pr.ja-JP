---
title: オンプレミスSkype for Business Microsoft Teamsにアップグレードする
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 組織をオンプレミスのSkype for BusinessデプロイからMicrosoft Teamsにアップグレードする方法について説明します。
ms.localizationpriority: medium
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
ms.openlocfilehash: d5ad5bc82771a3a8f020600a48848a074b88aec4
ms.sourcegitcommit: d3c48f0c147cf0c47d5eb4ea1128b5bca13be718
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2022
ms.locfileid: "62299062"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Skype for Business オンプレミスから Teams にアップグレードする

![デプロイと実装を重視したアップグレード体験図。](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 先に進む前に、次のアクティビティを完了していることを確認してください。

-   [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
-   [プロジェクトの対象範囲を定義した](./upgrade-define-project-scope.md)
-   [Skype for Business と Teams の共存と相互運用を理解した](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [環境を準備した](./upgrade-prepare-environment.md)
-   [組織を準備した](./upgrade-prepare-organization.md)
-   [パイロットを実施した](./pilot-essentials.md)

Skype for Business Serverまたは Microsoft Lync Server をオンプレミスに展開していて、組織がTeamsにアップグレードする場合は、この記事のガイダンスに従ってください。 Skype for Business ServerとTeams間のハイブリッド接続の計画に関する説明に従って、[Microsoft 365組織とのハイブリッド接続を設定する](/skypeforbusiness/hybrid/plan-hybrid-connectivity)必要があります。

開始する前に、この記事の後半で、[オンプレミスでSkype for Business Serverを使用する組織に関する重要な考慮事項](#important-considerations-for-organizations-with-skype-for-business-server-on-premises)についても確認する必要があります。

> [!IMPORTANT]
> Skype for Business Online は 2021 年 7 月 31 日に廃止されました。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。 アップグレードが成功すると、技術的な準備とユーザーの準備が一致するので、Microsoft Teamsへの道のりを進む際には、必ずこのガイダンスを活用してください。

## <a name="step-1-configure-hybrid-connectivity"></a>手順 1: ハイブリッド接続の構成 

オンプレミスのユーザーを Teams にアップグレードするため主な前提条件は、Skype for Business Server のオンプレミス展開にハイブリッド接続を構成することです。 

まず、 [readingPlan ハイブリッド接続](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json)から始め、ハイブリッド接続の [構成](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)に関するページで説明されているタスクに従います。


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>手順 2: 移行中の共存モードを設定する (省略可能)

Skype for BusinessとTeamsのクライアントとユーザーの共存と相互運用性は、[共存モード](migration-interop-guidance-for-teams-with-skype.md)によって定義されます。 ハイブリッド組織は、既定ではアイランド モードです。 アイランド モードでは、ユーザーはTeamsとSkype for Businessの両方のクライアントを同時に使用できます。 組織は必要に応じて、他の共存モードを使用して、組織がSkype for BusinessからTeamsに移行する際に、エンド ユーザーに予測可能なエクスペリエンスを提供できます。 組織がオンプレミス ユーザーに対して使用するモードが何であれ、それらのユーザーがオンプレミスからクラウドに移動されると、TeamsOnly になります (また、他のモードを使用することはできません)。  ユーザーがまだSkype for Business Serverを使用している限り、TeamsOnly 以外の任意のモードを割り当てることができます。 必要に応じて、TeamsOnly ユーザーをオンプレミスに戻すことができるため、テナントの TeamsUpgradePolicy のグローバル ポリシーを受け取ります。

ユーザーがいずれかのSkype for Business モードの場合、すべての着信チャットと通話がユーザーのSkype for Business クライアントにルーティングされます。 エンド ユーザーの混乱を回避し、適切なルーティングを確保するために、Teams クライアントの呼び出しおよびチャット機能 *は、Skype for Business モードのいずれかを割り当てられているユーザーに対して* 無効になります。 Teamsでの会議スケジュールは、ユーザーが SfBOnly モードまたは SfBWithTeamsCollab モードの場合は無効になり、ユーザーが SfBWithTeamsCollabAndMeetings モードの場合に *有効になります*。

組織の要件によりますが、組織が選択したアップグレード パスに基づいて適切な共存モードを割り当てることができます。 詳細については、「[Migration and interoperability guidance for organizations using Teams together with Skype for Business (Teams を Skype for Business と併用する組織向けの移行と相互運用に関するガイダンス)](migration-interop-guidance-for-teams-with-skype.md)」および「[共存およびアップグレードの設定 (Setting your coexistence and upgrade settings)](./setting-your-coexistence-and-upgrade-settings.md)」を参照してください。


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>手順 3: ユーザーを Skype for Business オンプレミスから TeamsOnly に移動する

Microsoft は最近、TeamsOnly にユーザーを移動するプロセスを簡略化しました。 使用している Skype for Business Server または Lync Server 2013 のバージョンに関係なく、このプロセスは 1 つの手順になりました。 詳細については、「 [オンプレミスとクラウドの間でユーザーを移動する](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)」と「[オンプレミスから Teams にユーザーを移動する](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)」を参照してください。 

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>手順 4: ハイブリッドを無効にしてオンプレミスのSkype for Businessを使用停止することで、クラウドへの移行を完了する

すべてのユーザーをオンプレミスからクラウドに移動したら、オンプレミスのSkype for Businessデプロイを使用停止できます。 詳細については、「[オンプレミスのSkype for Business環境の使用停止](/skypeforbusiness/hybrid/decommission-on-prem-overview)」を参照してください。


## <a name="phone-system-and-pstn-connectivity-options"></a>電話システムと PSTN 接続オプション

Teamsの電話システムは、ユーザーが TeamsOnly モードになった後でサポートされます。 (ユーザーがアイランド モードの場合、電話システムはSkype for Businessでのみサポートされます)。 

### <a name="pstn-connectivity-options"></a>PSTN 接続オプション

公衆交換電話網 (PSTN) 接続オプションを検討する場合、オンプレミスのSkype for Businessから TeamsOnly モードに移行する場合は、次の 2 つのシナリオが考えられます。

- エンタープライズ VoIP を使用している Skype for Business オンプレミスのユーザーのうち、オンラインに移行して、Microsoft 通話プランを使用するユーザー。 このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行を A) Microsoft 通話プランへのユーザーの電話番号のポートに合わせて調整するか、B) 利用可能な地域から新しいサブスクライバー番号を割り当てる必要があります。  詳細については、「オンプレミス[のSkype for Business Serverから、エンタープライズ VoIPを使用して Microsoft 通話プランに移動する」を](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)参照してください。

- エンタープライズ VoIP を使用している Skype for Business オンプレミスのユーザーのうち、オンラインに移行して、オンプレミスの PSTN 接続を維持するユーザー。 このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行をそのユーザーのダイレクト ルーティングへの移行に合わせて調整する必要があります。 詳細については、「オンプレミス[Skype for Business Serverエンタープライズ VoIPを使用したダイレクト ルーティングに関するページを](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)参照してください。


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Skype for Business Serverオンプレミスの組織に関する重要な考慮事項

- Skype for Business Hybrid のセットアップは、TeamsOnly モードへの移行の前提条件です。 オンプレミスのSkype for Business Server ユーザーは、ハイブリッドなしでアイランド モードでTeamsを使用できます。 ただし、ハイブリッド接続が必要な [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) を使用してユーザーをクラウドに移動しないと、TeamsOnly モードへの移行を行うことはできません。 詳細については、「[ハイブリッド接続を構成する](/skypeforbusiness/hybrid/configure-hybrid-connectivity)」を参照してください。 Skype for Business Online の今後の廃止により、この要件は変更されません。 組織がSkype for Business ServerからTeamsに移行するには、*廃止前とまったく* 同じツールセットを使用してハイブリッドを設定し、構成する必要があります。

- オンプレミス ユーザーをクラウドに移動するには、オンプレミス管理ツールで使用 `Move-CsUser` します。 ユーザーをオンプレミスから TeamsOnly に直接移動するスイッチを指定 `-MoveToTeams` する必要はなくなりました。 ユーザーには TeamsOnly モードが自動的に割り当てられ、スイッチが指定されているかどうかに関係なく、オンプレミスの会議は自動的にTeams会議に`-MoveToTeams`変換されます。

- 組織にSkype for Business Serverがあり、ハイブリッド接続を構成していないが、Teamsを引き続き使用する場合は、Teams機能を管理するには、.onmicrosoft.com ドメインを持つ管理アカウントを使用する必要があります。 ハイブリッド接続がない場合、管理ツールはオンプレミス ドメインを認識しません。 

- Skype for Business アカウントをオンプレミスに持つユーザー (つまり、Move-CsUser を使用してクラウドに移行していない) Teams、Skype for Business ユーザーと相互運用したり、外部ユーザーとフェデレーションしたりすることはできません。 この機能は、ユーザーがクラウドに移動され、TeamsOnly ユーザーである場合にのみ使用できます。 

- オンプレミスでSkype for Business アカウントを持つユーザーがいる場合、またはオンプレミス展開用の lyncdiscover DNS レコードが残っている場合は、テナント レベルで TeamsOnly モードを割り当てることはできません。 まず、オンプレミスのSkype for Business アカウントを持つすべてのユーザーをクラウド`Move-CsUser`に移動する必要があります。 次に、「ハイブリッドを無効にする」で説明されている手順に従って、DNS エントリの削除を含む [クラウドへの移行を完了](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)します。 `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`Office 365以外の場所を指す lyncdiscover DNS レコードが検出された場合、テナント レベルでは機能しません。

- ユーザーが適切な Skype for Business 属性を使用して Azure AD に正しく同期されていることを確認する必要があります。 これらの属性すべてには、プレフィックスとして msRTCSIP- が付きます。 ユーザーがAzure ADに正しく同期されていない場合、Teamsの管理ツールはこれらのユーザーを管理できません。 (たとえば、これらの属性を適切に同期していない限り、Teams ポリシーをオンプレミス ユーザーに割り当てることはできません)。詳細については、「[TeamsとSkype for BusinessのAzure AD Connectの構成](/SkypeForBusiness/hybrid/configure-azure-ad-connect)」を参照してください。

- ハイブリッド組織で新しい TeamsOnly を作成するには、*最初にオンプレミスでユーザー Skype for Business Server有効に* してから、Move-CsUser を使用してユーザーをオンプレミスからクラウドに移動する必要があります。  最初にオンプレミスでユーザーを作成することにより、残りのオンプレミスの Skype for Business ユーザーは新しく作成されたユーザーに確実にルーティングできるようになります。 *すべての* ユーザーがオンラインに移行されると、最初にオンプレミスのユーザーを有効にする必要はなくなりました。

- オンプレミスのユーザーに対して Skype for Business クライアントで通知を表示する場合は、オンプレミスのツールセットで TeamsUpgradePolicy を使用する必要があります。 オンプレミスのユーザーに関係があるのは、NotifySfbUsers パラメーターのみです。  オンプレミスのユーザーは、TeamsUpgradePolicy のオンライン インスタンスから自分のモードを受け取ります。 「[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)」のメモを参照してください。 

>[!NOTE]
> 2019 年 9 月 3 日以降に作成されたすべての新しいテナントは、組織に既にオンプレミスのSkype for Business Server展開がない限り、TeamsOnly テナントとして作成されます。 Microsoft では、DNS レコードを使用して、オンプレミスのSkype for Business Server組織を識別します。 詳細については、「 [ハイブリッドになるオンプレミス組織に対する DNS の影響](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid)」を参照してください。 

- 次の記事では、重要なアップグレードの概念と共存動作について説明します。
    - [Teams と Skype for Business の共存](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [共存モード - リファレンス](migration-interop-guidance-for-teams-with-skype.md)
    - [Teams のクライアント エクスペリエンスおよび共存モードへの準拠](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md) 

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[オンプレミスとクラウドの間でユーザーを移動する](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[会議移行サービス (MMS) を使用する](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
