---
title: オンプレミスSkype for BusinessにアップグレードMicrosoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 組織をアップグレードして、オンプレミスのMicrosoft TeamsからSkype for Businessする方法について説明します。
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

![デプロイと実装を強調したアップグレード体験図。](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 先に進む前に、次のアクティビティを完了していることを確認してください。

-   [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
-   [プロジェクトの対象範囲を定義した](./upgrade-define-project-scope.md)
-   [Skype for Business と Teams の共存と相互運用を理解した](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [環境を準備した](./upgrade-prepare-environment.md)
-   [組織を準備した](./upgrade-prepare-organization.md)
-   [パイロットを実施した](./pilot-essentials.md)

オンプレミスに Skype for Business Server または Microsoft Lync Server を展開し、組織が Teams にアップグレードする場合は、この記事のガイダンスに従います。 「ハイブリッド接続を計画する」の説明に従って、Microsoft 365 組織とのハイブリッド接続をSkype for Business Server[必要Teams](/skypeforbusiness/hybrid/plan-hybrid-connectivity)。

開始する前に、この記事の後半で、オンプレミスの組織Skype for Business Server[に関](#important-considerations-for-organizations-with-skype-for-business-server-on-premises)する重要な考慮事項も確認する必要があります。

> [!IMPORTANT]
> Skype for Business Online は 2021 年 7 月 31 日に廃止されました。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。 アップグレードが成功すると、技術的な準備とユーザーの準備が揃うので、このガイダンスを活用して、アップグレードの準備をMicrosoft Teams。

## <a name="step-1-configure-hybrid-connectivity"></a>手順 1: ハイブリッド接続の構成 

オンプレミスのユーザーを Teams にアップグレードするため主な前提条件は、Skype for Business Server のオンプレミス展開にハイブリッド接続を構成することです。 

最初に「 [ハイブリッド接続を計画](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json)する」を読み、ハイブリッド接続の構成に関する記事に示 [されているタスクに従います](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)。


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>手順 2: 移行中の共存モードを設定する (省略可能)

クライアントとユーザーの間の共存Skype for Business相互Teamsは、共存モード[によって定義されます](migration-interop-guidance-for-teams-with-skype.md)。 ハイブリッド組織は、既定では諸島モードです。 Islands モードでは、ユーザーはクライアントとTeamsとSkype for Businessの両方を使用できます。 組織は、必要に応じて、他の共存モードを使用して、組織の移行時にエンド ユーザーに予測可能なエクスペリエンスを提供Skype for Business Teams。 組織がオンプレミス ユーザーに使用するモードが何であれ、それらのユーザーをオンプレミスからクラウドに移動すると、そのユーザーは TeamsOnly になります (他のモードを使用できません)。  ユーザーが引き続きアプリケーションを使用しているSkype for Business Server、TeamsOnly 以外の任意のモードを割り当てることができます。 必要に応じて、TeamsOnly ユーザーをオンプレミスに戻し、その結果、TeamsUpgradePolicy のテナントのグローバル ポリシーを受け取る可能性があります。

ユーザーが任意のモードでSkype for Business、すべての着信チャットと通話がユーザーのクライアントにSkype for Businessされます。 エンド ユーザーの混乱を避け、適切なルーティングを確保するために、Teams クライアントの呼び出しとチャット機能は、Skype for Business モードが割り当てられているユーザーに対 *して無効になります*。 Teams での会議のスケジュール設定は、ユーザーが SfBOnly モードまたは SfBWithTeamsCollab モードのときに無効になり、ユーザーが SfBWithTeamsCollabAndMeetings モードのときに有効になります。

組織の要件によりますが、組織が選択したアップグレード パスに基づいて適切な共存モードを割り当てることができます。 詳細については、「[Migration and interoperability guidance for organizations using Teams together with Skype for Business (Teams を Skype for Business と併用する組織向けの移行と相互運用に関するガイダンス)](migration-interop-guidance-for-teams-with-skype.md)」および「[共存およびアップグレードの設定 (Setting your coexistence and upgrade settings)](./setting-your-coexistence-and-upgrade-settings.md)」を参照してください。


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>手順 3: ユーザーを Skype for Business オンプレミスから TeamsOnly に移動する

Microsoft は最近、ユーザーを TeamsOnly に移行するプロセスを簡略化しました。 このプロセスは、使用している Lync Server 2013 Skype for Business Serverバージョンに関係なく、1 つの手順になります。 詳細については、「 [オンプレミスとクラウドの間でユーザーを移動する](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)」と「[オンプレミスから Teams にユーザーを移動する](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)」を参照してください。 

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>手順 4: ハイブリッドを無効にし、オンプレミスのアプリケーションを使用停止して、クラウドへの移行を完了Skype for Business

すべてのユーザーをオンプレミスからクラウドに移動した後は、オンプレミスのデプロイを使用Skype for Businessできます。 詳細については、「オンプレミス環境の使用[停止」をSkype for Businessしてください](/skypeforbusiness/hybrid/decommission-on-prem-overview)。


## <a name="phone-system-and-pstn-connectivity-options"></a>電話システム PSTN 接続オプション

電話システムのTeamsは、ユーザーが TeamsOnly モードの場合にサポートされます。 (ユーザーが Islands モードの場合電話システムは、Skype for Business。 

### <a name="pstn-connectivity-options"></a>PSTN 接続オプション

公衆交換電話網 (PSTN) 接続オプションを検討する場合、オンプレミスから TeamsOnly モードに移行する場合、次の 2 Skype for Businessシナリオが考えられます。

- エンタープライズ VoIP を使用している Skype for Business オンプレミスのユーザーのうち、オンラインに移行して、Microsoft 通話プランを使用するユーザー。 このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行を A) Microsoft 通話プランへのユーザーの電話番号のポートに合わせて調整するか、B) 利用可能な地域から新しいサブスクライバー番号を割り当てる必要があります。  詳細については、「オンプレミスからオンプレミスSkype for Business Server、Microsoft 通話プラン[エンタープライズ VoIP」を参照してください](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)。

- エンタープライズ VoIP を使用している Skype for Business オンプレミスのユーザーのうち、オンラインに移行して、オンプレミスの PSTN 接続を維持するユーザー。 このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行をそのユーザーのダイレクト ルーティングへの移行に合わせて調整する必要があります。 詳細については、「オンプレミスから、Skype for Business Serverを使用した直接ルーティング[エンタープライズ VoIP」を参照してください](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>オンプレミスの組織に関するSkype for Business Server考慮事項

- Skype for Business Hybrid のセットアップは、TeamsOnly モードへの移行の前提条件です。 オンプレミスのユーザーは、ハイブリッドなしでSkype for Business ServerモードTeamsを使用できます。 ただし、ハイブリッド接続が必要な [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) を使用してユーザーをクラウドに移動しない場合、TeamsOnly モードへの移行は実行できません。 詳細については、「[ハイブリッド接続を構成する](/skypeforbusiness/hybrid/configure-hybrid-connectivity)」を参照してください。 Skype for Business Online の提供が近日提供が予定されている場合、この要件は変更されません。 組織を Skype for Business Server から Teams に移行するには、引き続き同じツールセットを使用してハイブリッドをセットアップし、構成する必要があります。この設定は、提供が開始される前とまったく同 *じです*。

- オンプレミス ユーザーをクラウドに移動するには、オンプレミスの `Move-CsUser` 管理ツールで を使用します。 オンプレミスから TeamsOnly に `-MoveToTeams` ユーザーを直接移動するスイッチを指定する必要がなくなりました。 ユーザーには TeamsOnly `-MoveToTeams` モードが自動的に割り当てられるので、スイッチが指定されているかどうかに関係なく、オンプレミスの会議は Teams 会議に自動的に変換されます。

- 組織に Skype for Business Server が存在し、ハイブリッド接続を構成していないが、引き続き Teams を使用する場合は、Teams 機能を管理するには、.onmicrosoft.com ドメインを持つ管理アカウントを使用する必要があります。 ハイブリッド接続を使用しない場合、管理ツールはオンプレミス ドメインを認識します。 

- Teams Skype for Business アカウントを持つユーザー (つまり、Move-CsUser を使用してクラウドにまだ移動されていない) は、Skype for Business ユーザーと相互運用したり、外部ユーザーとフェデレーションしたりすることはできません。 この機能は、ユーザーがクラウドに移動され、TeamsOnly ユーザーである場合にのみ使用できます。 

- Skype for Business アカウントを持つユーザーがオンプレミスにある場合、またはオンプレミスデプロイの lyncdiscover DNS レコードがまだある場合は、テナント レベルで TeamsOnly モードを割り当てできません。 まず、 を使用して、オンプレミスのアカウントを持つSkype for Businessをクラウドに移動する必要があります`Move-CsUser`。 次に、「ハイブリッドを無効にする」で [説明されている](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)手順に従って、DNS エントリの削除を含むクラウドへの移行を完了します。 `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`lyncdiscover DNS レコードが検出された場合、テナント レベルでは機能しません。これは、テナント レベル以外の場所Office 365。

- ユーザーが適切な Skype for Business 属性を使用して Azure AD に正しく同期されていることを確認する必要があります。 これらの属性すべてには、プレフィックスとして msRTCSIP- が付きます。 ユーザーがアプリケーションに適切に同期Azure AD場合、Teamsの管理ツールは、これらのユーザーを管理できません。 (たとえば、これらの属性を適切に同期しない限り、Teams ポリシーをオンプレミスユーザーに割り当てできません)。詳細については、「Configure [Azure AD Connect for Teams and Skype for Business」を参照してください](/SkypeForBusiness/hybrid/configure-azure-ad-connect)。

- ハイブリッド組織で新しい TeamsOnly を作成するには、まず *オンプレミスの Skype for Business Server* でユーザーを有効にしてから、Move-CsUser を使用してオンプレミスからクラウドにユーザーを移動する必要があります。  最初にオンプレミスでユーザーを作成することにより、残りのオンプレミスの Skype for Business ユーザーは新しく作成されたユーザーに確実にルーティングできるようになります。 すべての *ユーザー* がオンラインに移動された後は、最初にオンプレミスのユーザーを有効にする必要がなくなりました。

- オンプレミスのユーザーに対して Skype for Business クライアントで通知を表示する場合は、オンプレミスのツールセットで TeamsUpgradePolicy を使用する必要があります。 オンプレミスのユーザーに関係があるのは、NotifySfbUsers パラメーターのみです。  オンプレミスのユーザーは、TeamsUpgradePolicy のオンライン インスタンスから自分のモードを受け取ります。 「[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)」のメモを参照してください。 

>[!NOTE]
> 2019 年 9 月 3 日より後に作成された新しいテナントは、組織に既に Skype for Business Server のオンプレミス デプロイがない限り、TeamsOnly テナントとして作成されます。 Microsoft では、DNS レコードを使用して、オンプレミスの組織Skype for Business Serverします。 詳細については、「ハイブリッドになる [オンプレミス組織の DNS への影響」を参照してください](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid)。 

- 次の記事では、アップグレードの重要な概念と共存動作について説明します。
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
