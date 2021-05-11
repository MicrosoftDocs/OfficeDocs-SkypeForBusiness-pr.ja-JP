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
ms.openlocfilehash: d323760d4187730b0ae83d45021df44230a982cd
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306051"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Skype for Business オンプレミスから Teams にアップグレードする

![展開と実装に重点を置いた、アップグレードのフロー図](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 先に進む前に、次のアクティビティを完了していることを確認してください。

-   [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
-   [プロジェクトの対象範囲を定義した](./upgrade-define-project-scope.md)
-   [Skype for Business と Teams の共存と相互運用を理解した](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [環境を準備した](./upgrade-prepare-environment.md)
-   [組織を準備した](./upgrade-prepare-organization.md)
-   [パイロットを実施した](./pilot-essentials.md)

オンプレミスに Skype for Business Server または Microsoft Lync を展開し、組織が Teams にアップグレードする場合は、この記事のガイダンスに従います。 Microsoft 365 または Office 365 組織とのハイブリッド接続を設定し、ユーザーを複数のフェーズで Teams に移行する場合は、共存要件を決定する必要があります。

開始する前に、IT 管理者は、この記事の[](#important-considerations-for-organizations-with-skype-for-business-server-on-premises)後半で、オンプレミスの Skype for Business Serverに関する重要な考慮事項を確認する必要があります。

> [!IMPORTANT]
> Skype for Business Online は 2021 年 7 月 31 日に廃止される予定です。それ以降、アクセスとサポートが終了します。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。 アップグレードが成功すると、技術面およびユーザーの準備が整ったことになります。Microsoft Teams への移行を進める際には、必ずこのガイドを活用してください。

## <a name="step-1-configure-hybrid-connectivity"></a>手順 1: ハイブリッド接続の構成 

オンプレミスのユーザーを Teams にアップグレードするため主な前提条件は、Skype for Business Server のオンプレミス展開にハイブリッド接続を構成することです。 

まず、「 [ハイブリッド接続のプラン](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json)」をご覧になり、「[ハイブリッド接続の構成](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)」で説明されているタスクを実行します。


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>手順 2: 移行中の共存モードを設定する (省略可能)

Skype for Business、Teams クライアント、およびユーザーの間の共存と相互運用性は、Teams のアップグレード モードによって規定されます。  既定では、組織はアイランド モードになっており、ユーザーは Teams と Skype for Business の両方を併用できます。

Teams に移行する組織にとって、最終的にはすべてのユーザーを TeamsOnly モードにすることが目標ですが、TeamsOnly (またはその他のモード) を全員に同時に割り当てる必要はありません。

ユーザーが TeamsOnly モードに到達するまでは、組織は Skype for Business 共存モードのいずれかのモードを使用するという選択肢があり、こうすることで、TeamsOnly モードのユーザーとまだこのモードに設定されていないユーザーの間で、安定した通信を確保できます。  Skype for Business 共存モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) の目的は、組織が Skype for Business から Teams に移行する際に、シンプルで予測可能なエクスペリエンスをエンド ユーザーに提供することです。 

ユーザーが任意のモードでSkype for Business、すべての着信チャットと通話がユーザーのクライアントにSkype for Businessされます。 ユーザーがいずれかの Skype for Business モードに設定されている場合、エンド ユーザーを混乱させない適切なルーティングを確保するために、Teams クライアントの通話とチャット機能は無効化されます。 同様に、Teams での会議のスケジュールも、ユーザーが SfBOnly または SfBWithTeamsCollab モードの場合は明示的に無効化され、ユーザーが SfBWithTeamsCollabAndMeetings の場合には明示的に有効化されます。

組織の要件によりますが、組織が選択したアップグレード パスに基づいて適切な共存モードを割り当てることができます。 詳細については、「[Migration and interoperability guidance for organizations using Teams together with Skype for Business (Teams を Skype for Business と併用する組織向けの移行と相互運用に関するガイダンス)](migration-interop-guidance-for-teams-with-skype.md)」および「[共存およびアップグレードの設定 (Setting your coexistence and upgrade settings)](./setting-your-coexistence-and-upgrade-settings.md)」を参照してください。


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>手順 3: ユーザーを Skype for Business オンプレミスから TeamsOnly に移動する

最終的には、ユーザーを TeamsOnly モードに移動します。 これには、オンプレミス環境に応じて 1 ~ 2 つの手順が必要になる場合があります。  

詳細については、「 [オンプレミスとクラウドの間でユーザーを移動する](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)」と「[オンプレミスから Teams にユーザーを移動する](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)」を参照してください。 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>手順 4: ハイブリッドを無効にしてクラウドへの移行を完了する

すべてのユーザーをオンプレミスからクラウドに移動した後は、オンプレミスのデプロイをSkype for Businessできます。 詳細については、「ハイブリッドを無効 [にしてクラウドへの移行を完了する」を参照してください](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)。


## <a name="phone-system-and-pstn-connectivity-options"></a>電話システム PSTN 接続オプション

電話システムのTeamsは、ユーザーが TeamsOnly モードの場合にサポートされます。 (ユーザーが Islands モードの場合電話システムは、Skype for Business。 

### <a name="pstn-connectivity-options"></a>PSTN 接続オプション

公衆交換電話網 (PSTN) 接続オプションを検討する場合、オンプレミスの電話から TeamsOnly モードに移行する場合Skype for Business 2 つのシナリオが考えられます。

- エンタープライズ VoIP を使用している Skype for Business オンプレミスのユーザーのうち、オンラインに移行して、Microsoft 通話プランを使用するユーザー。 このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行を A) Microsoft 通話プランへのユーザーの電話番号のポートに合わせて調整するか、B) 利用可能な地域から新しいサブスクライバー番号を割り当てる必要があります。  詳細については、「オンプレミスから Skype for Business Serverオンプレミスから、エンタープライズ VoIP Microsoft 通話プラン」[を参照してください](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)。

- エンタープライズ VoIP を使用している Skype for Business オンプレミスのユーザーのうち、オンラインに移行して、オンプレミスの PSTN 接続を維持するユーザー。 このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行をそのユーザーのダイレクト ルーティングへの移行に合わせて調整する必要があります。 詳細については、「オンプレミスから、Skype for Business Serverを使用した直接ルーティング[エンタープライズ VoIP」を参照してください](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>オンプレミスの組織に関するSkype for Business Server考慮事項

- 次の記事では、アップグレードの重要な概念と共存動作について説明します。
    - [Teams と Skype for Business の共存](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [共存モード - リファレンス](migration-interop-guidance-for-teams-with-skype.md)
    - [Teams のクライアント エクスペリエンスおよび共存モードへの準拠](teams-client-experience-and-conformance-to-coexistence-modes.md)

- Skype for Business Hybrid のセットアップは、TeamsOnly モードへの移行の前提条件です。 オンプレミスの Skype for Business Server ユーザーがハイブリッドなしで Teams を使用できる一方で、ハイブリッド接続が必要な[Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)を使用してユーザーをクラウドに移動しない限り、TeamsOnly モードへの切り替えは実行できません。 詳細については、「[ハイブリッド接続を構成する](/skypeforbusiness/hybrid/configure-hybrid-connectivity)」を参照してください。 また、Skype for Business Online の提供が近日提供される予定で、この要件は変更されません。 組織が Skype for Business Server から Teams に移行するには、引き続き同じツールセットを使用してハイブリッドをセットアップして構成する必要があります。この設定は、提供が開始される前とまったく同 *じです*。

- オンプレミス ユーザーをクラウドに移動するには、オンプレミスの管理 `Move-CsUser` ツールで を使用します。 現在、このスイッチが指定されていない場合、ユーザーはオンプレミスの Skype for Business Server にホームから Skype for Business Online に移行し、モードは変更されず、Skype for Business Server で開催された会議は Skype for Business Online に移行されます。 Skype for Business Online が提供終了される予定のため、ユーザーをオンプレミスから `-MoveToTeams` TeamsOnly に直接移動する切り替えの指定は間もなく不要になります `Move-CsUser` 。  提供終了後に、 を使用してユーザーをオンプレミスからクラウドに移動すると、ユーザーには TeamsOnly モードが自動的に割り当てられます。また、オンプレミスからの会議は、スイッチが実際に指定されているかどうかに関係なく、 と同様に、自動的に Teams 会議に変換されます。 `Move-CsUser` `-MoveToTeams switch had been specified` この機能は、2021 年 7 月 31 日の実際の提供が解除される前にリリースされる予定です。

- 組織に Skype for Business Server が存在し、ハイブリッド接続を構成していないが、引き続き Teams を使用する場合は、Teams 機能を管理するには、.onmicrosoft.com ドメインを持つ管理アカウントを使用する必要があります。 ハイブリッド接続を使用しない場合、管理ツールはオンプレミス ドメインを認識します。 

- オンプレミスの Skype for Business アカウントを所有している Teams ユーザー (つまり、Move-CsUser を使用してクラウドにまだ移行していないユーザー) は、Skype for Business ユーザーとの相互運用や、外部ユーザーとのフェデレーションを行うことができません。 この機能は、ユーザーがクラウドに移動され、TeamsOnly ユーザーである場合にのみ使用できます。 

- Skype for Business アカウントを持つユーザーがオンプレミスにある場合、またはオンプレミス展開の lyncdiscover DNS レコードがまだある場合は、テナント レベルで TeamsOnly モードを割り当てできません。 最初に、 を使用してオンプレミスの Skype for Business アカウントを持つすべてのユーザーをクラウドに移動し、「ハイブリッドを無効にする」に記載されている手順に従って、DNS エントリの削除を含むクラウドへの移行を完了する必要があります。 `Move-CsUser` [](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`lyncdiscover DNS レコードが検出された場合、テナント レベルでは機能しません。このレコードは、Office 365。

- ユーザーが適切な Skype for Business 属性を使用して Azure AD に正しく同期されていることを確認する必要があります。 これらの属性すべてには、プレフィックスとして msRTCSIP- が付きます。 ユーザーが Azure AD に正しく同期されていない場合、Teams の管理ツールでそのユーザーを管理できなくなります。 (たとえば、これらの属性を適切に同期しない限り、Teams ポリシーをオンプレミス ユーザーに割り当てできません)。詳細については、「Azure azure [AD Connect for Teams」を](/SkypeForBusiness/hybrid/configure-azure-ad-connect)Skype for Business。

- ハイブリッド組織で新しい TeamsOnly ユーザーや Skype for Business Online のユーザーを作成するには、*最初にユーザーを Skype for Business Server オンプレミスで有効にしてから*、その後に、そのユーザーを Move-CsUser を使用してオンプレミスからクラウドに移行する必要があります。  最初にオンプレミスでユーザーを作成することにより、残りのオンプレミスの Skype for Business ユーザーは新しく作成されたユーザーに確実にルーティングできるようになります。 すべてのユーザーのオンラインへの移行が完了しているなら、最初にオンプレミスでユーザーを有効にする必要はありません。

- オンプレミスのユーザーに対して Skype for Business クライアントで通知を表示する場合は、オンプレミスのツールセットで TeamsUpgradePolicy を使用する必要があります。 オンプレミスのユーザーに関係があるのは、NotifySfbUsers パラメーターのみです。  オンプレミスのユーザーは、TeamsUpgradePolicy のオンライン インスタンスから自分のモードを受け取ります。 「[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)」のメモを参照してください。 

>[!NOTE]
> 2019 年 9 月 3 日より後に作成された新しいテナントは、組織に既に Skype for Business Server のオンプレミス デプロイがない限り、TeamsOnly テナントとして作成されます。 Microsoft では、DNS レコードを使用して、オンプレミスの組織Skype for Business Serverします。 組織にパブリック DNS エントリがないSkype for Business Serverオンプレミスのドメインがある場合は、Microsoft サポートに連絡して、新しいテナントをダウングレードする必要があります。 

## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md) 

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[オンプレミスとクラウドの間でユーザーを移動する](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[会議移行サービス (MMS) を使用する](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
