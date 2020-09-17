---
title: Skype for Business オンプレミス展開から Teams へのアップグレード - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business から Teams へのアップグレード
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 075960ef47f5d708a72cabc8e3c492786c2a5112
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940687"
---
# <a name="pstn-considerations-when-upgrading-to-teams-mdash-for-it-administrators"></a>IT 管理者の Teams にアップグレードするときの PSTN の考慮事項 &mdash;

この記事では、Teams にアップグレードするときの公衆交換電話網 (PSTN) に関する考慮事項について説明します。 この記事では、IT 管理者向けのアップグレードの概念と実装について説明します。  

- [概要](upgrade-to-teams-on-prem-overview.md)
- [アップグレード方法](upgrade-to-teams-on-prem-upgrade-methods.md)
- [アップグレードを管理するためのツール](upgrade-to-teams-on-prem-tools.md)
- [Skype for Business オンプレミスの組織に関するその他の考慮事項](upgrade-to-teams-on-prem-considerations.md)
- [アップグレードを実装する](upgrade-to-teams-on-prem-implement.md)
- **公衆交換電話網 (PSTN) の考慮事項** (この記事)

さらに、次の記事では、アップグレードの重要な概念と共存の動作について説明します。

- [Teams と Skype for Business の共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存モード-参照](migration-interop-guidance-for-teams-with-skype.md)
- [Teams のクライアント エクスペリエンスおよび共存モードへの準拠](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > Teams での電話システムの使用は、ユーザーが TeamsOnly モードになっている場合にのみサポートされます。  ユーザーがアイランド モードの場合、電話システムは Skype for Business でのみサポートされます。 


## <a name="pstn-calling-scenarios"></a>PSTN 通話のシナリオ

TeamsOnly モードに移行する場合は、次の4つの方法が考えられます。

- [Microsoft 通話プランを使用している Skype for Business Online のユーザー](#from-skype-for-business-online-with-microsoft-calling-plans)。 アップグレードすると、このユーザーは Microsoft 通話プランを引き続き使用します。

- Skype for business のオンプレミスまたはクラウドコネクタエディションによる[オンプレミス音声機能を備えた skype For Business Online のユーザー](#from-skype-for-business-online-with-on-premises-voice) 。 このユーザーの Teams へのアップグレードは、その TeamsOnly ユーザーが確実に PSTN 機能を持てるようにするため、ユーザーのダイレクト ルーティングへの移行に合わせた調整が必要になります。

- [エンタープライズ voip がオンプレミスの Skype For business のユーザー](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。オンラインに移行し、オンプレミスの PSTN 接続を維持します。  このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行をそのユーザーのダイレクト ルーティングへの移行に合わせて調整する必要があります。 

- [エンタープライズ VoIP を使用している Skype for Business オンプレミスのユーザー](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)のうち、オンラインに移行して、Microsoft 通話プランを使用するユーザー。  このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行を A) Microsoft 通話プランへのユーザーの電話番号のポートに合わせて調整するか、B) 利用可能な地域から新しいサブスクライバー番号を割り当てる必要があります。

この記事では、概要のみを説明します。 詳細については、「[電話システムのダイレクト ルーティング](direct-routing-landing-page.md)」および「[通話プラン](calling-plan-landing-page.md)」を参照してください。 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Microsoft 通話プランを使用している Skype for Business Online からの場合 

これは、音声が関係する最も簡単なアップグレード シナリオです。 

1. ユーザーに Teams ライセンスが割り当てられていることを確認します。 既定では、Microsoft 365 または Office 365 のライセンスを割り当てると、Teams が有効になります。これは、チームのライセンスを無効にしていない限り、操作は必要ありません。

2.  ユーザーが既に電話番号を指定して Microsoft 通話プランを使用している場合に必要な変更は、そのユーザーに TeamsUpgradePolicy で TeamsOnly モードを割り当てることのみです。  TeamsOnly モードを割り当てる前は、着信 PSTN 通話はユーザーの Skype for Business クライアントに配信されます。 TeamsOnly モードにアップグレードすると、着信 PSTN 通話はユーザーの Teams クライアントに配信されます。  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>オンプレミス音声を使用している Skype for Business Online からの場合

このシナリオでは、ユーザーは既に Skype for Business Online を使用していますが、PSTN 接続はオンプレミスで、ハイブリッド モードかクラウド コネクタ エディションの Skype for Business Server を使用しています。 PSTN 機能を使用してこれらのユーザーを TeamsOnly モードに移行することは、そのユーザーにダイレクト ルーティングを許可することを意味します。ダイレクト ルーティングでは、PSTN トランクは、オンプレミス セッション ボーダー コントローラー (SBC) を介して、クラウドのダイレクト ルーティング サービスに直接接続します。

基本的なステップを次に示します。  ステップ 1 から 4 は、提案されている順序で並んでいますが、任意の順序で実行できます。 重要なのは、これらすべてをステップ 5 の前に完了する必要があるということです。

1. テナント全体のポリシーを Skype for Business のモードの 1 つに設定する予定の場合は、前述のように既存のアイランド ユーザーにアイランド モードを明示的に割り当てることにより、それらのユーザーを必ず grandfather 化してください。

2. ダイレクト ルーティング用にテナントを構成します。 「[ダイレクト ルーティングのテナントごとの構成の概要](#summary-of-per-tenant-configuration-of-direct-routing)」を参照してください。

3. 必要に応じて、これらのユーザーに対してさまざまな Teams ポリシーを構成します (TeamsMessagingPolicy や TeamsMeetingPolicy など)。 この操作はいつでも行えますが、ユーザーをアップグレードした時にユーザーが確実に正しく構成されているようにするには、ユーザーを TeamsOnly モードにアップグレードする前にこれを行なっておくのが最善です。

4. 選択したユーザーに音声移行の準備をします。 
   - 必要に応じて、Teams ライセンスを割り当てます。  ユーザーが既に Skype for Business Online のオンプレミス音声を使用できているなら、そのユーザーは Microsoft 電話システムだけでなく、Skype for Business プラン 2 も所有しています。 両方のプラン (Skype for Business Online プラン 2 のライセンスを含む) を有効なままにしておきます。  
   - 目的の OnlineVoiceRoutingPolicy を割り当てます。 

5. これらのステップは相互に合うように調整する必要があります。 

   - Microsoft 365 または Office 365 では、ユーザーを TeamsOnly モード (Grant-CsTeamsUpgradePolicy) にアップグレードします。
   - SBC で、通話をオンプレミスの仲介サーバーではなくダイレクト ルーティングに送信することにより、音声ルーティングが着信通話を許可するように構成します。


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>エンタープライズ VoIP を使用している Skype for Business Server オンプレミスからダイレクト ルーティングに移行する場合

このシナリオでは、ユーザーは Skype for Business オンプレミスにまだ所属しており、PSTN 接続もオンプレミスです。 PSTN 機能を使用してこれらのユーザーを TeamsOnly モードに移行することは、そのユーザーにダイレクト ルーティングを許可して、クラウドに移行することを意味します。 
 
基本的なステップを次に示します。  ステップ 1 から 5 は、提案されている順序で並んでいますが、任意の順序で実行できます。 重要なのは、これらすべてをステップ 6 の前に完了する必要があるということです。

1. テナント全体のポリシーを Skype for Business のモードの 1 つに設定する予定の場合は、前述のように既存のアイランド ユーザーにアイランド モードを明示的に割り当てることにより、それらのユーザーを必ず grandfather 化してください。

2. まだ構成していない場合は、[Skype for Business Hybrid 用に組織を構成](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)します。

3. ダイレクト ルーティング用にテナントを構成します。 「[ダイレクト ルーティングのテナントごとの構成の概要](#summary-of-per-tenant-configuration-of-direct-routing)」を参照してください。

4. 必要に応じて、これらのユーザーに対してさまざまな Teams ポリシーを構成します (TeamsMessagingPolicy や TeamsMeetingPolicy など)。 この操作はいつでも行えますが、ユーザーをアップグレードした時にユーザーが確実に正しく構成されているようにするには、ユーザーを TeamsOnly アップグレードする前にこれを行なっておくのが最善です。

5. 必要に応じて、Microsoft 365 または Office 365 のライセンスを割り当てます。  ユーザーは、電話システムに加えて、Teams と Skype for Business Online プラン 2 の両方が必要です。 Skype for Business Online プラン 2 が無効になっている場合は、もう一度有効にします。  

6. これらのステップは相互に合うように調整する必要があります。 

   - オンプレミスの Skype for Business ツールを使用し、-MoveToTeams スイッチを指定して Move-CsUser を実行します。 -MoveToTeams スイッチをサポートしていないバージョンの Skype for Business Server を使用している場合は、まず Move-CsUser を実行してから、テナントのリモート PowerShell か Teams 管理コンソールで、TeamsOnly モードを割り当てます。

   - SBC で、通話をオンプレミスの仲介サーバーではなくダイレクト ルーティングに送信することにより、音声ルーティングが着信通話を許可するように構成します。 

   - Microsoft 365 または Office 365 の場合: 発信通話を有効にするために、関連する OnlineVoiceRoutingPolicy を割り当てます。 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>エンタープライズ VoIP を使用している Skype for Business Server オンプレミスから Microsoft 通話プランに移行する場合

このシナリオでは、ユーザーは Skype for Business オンプレミスにまだ所属しており、PSTN 接続もオンプレミスです。 PSTN 機能を使用してこれらのユーザーを TeamsOnly モードに移行することは、そのユーザーをクラウドに移行して、そのユーザーの番号を元の通信事業者から Microsoft 通話プランに移植するか、そのユーザーに新しい番号を割り当てるかを意味します。 

基本的なステップを次に示します。ステップ 1 から 5 は、提案されている順序で並んでいますが、任意の順序で実行できます。 重要なのは、これらすべてをステップ 6 の前に完了する必要があるということです。 

1. テナント全体のポリシーを Skype for Business のモードの 1 つに設定する予定の場合は、前述のように既存のアイランド ユーザーにアイランド モードを明示的に割り当てることにより、それらのユーザーを必ず grandfather 化してください。 

2. まだ構成していない場合は、[Skype for Business Hybrid 用に組織を構成](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)します。 

3. 必要に応じて、これらのユーザーに対してさまざまな Teams ポリシーを構成します (TeamsMessagingPolicy や TeamsMeetingPolicy など)。 この操作はいつでも行えますが、ユーザーをアップグレードした時にユーザーが確実に正しく構成されているようにするには、ユーザーを TeamsOnly アップグレードする前にこれを行なっておくのが最善です。 

4. 必要に応じて、Microsoft 365 または Office 365 のライセンスを割り当てます。ユーザーは、電話システムに加えて、Teams と Skype for Business Online プラン 2 の両方が必要です。 Skype for Business Online プラン 2 が無効になっている場合は、もう一度有効にします。  

5. ユーザーの電話番号を取得します。 (詳細については、「[組織の電話番号を管理する](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)」を参照してください)。

   - 番号を再利用する場合は、通信事業者に移植要求を提出します。  
   - または、直接 Microsoft から新しい番号を取得することもできます。 

6. ユーザーをアップグレードし、必要に応じて LineUri を割り当てます。 オンプレミスの Skype for Business ツールを使用し、-MoveToTeams スイッチを指定して Move-CsUser を実行します。  

    - 番号を Microsoft に移植する場合は、この操作のタイミングを調整して、ポートが発生するときに発生するようにする必要があります。 

    - Microsoft から新しい番号を取得して使用する場合は、そのユーザーの LineUri を変更することが必要になります。 この操作は、CsOnlineVoiceUser を使用してオンラインでユーザーを移動した後に行う必要があります。  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>ダイレクト ルーティングのテナントごとの構成の概要 

1. [このリスト](direct-routing-border-controllers.md)を確認して、ご利用のセッション ボーダー コントローラー (SBC) がダイレクト ルーティングでサポートされていることを確認します。 正しいバージョンのファームウェアを使用していることも確認する必要があります。  

2. オンプレミスの SBC と Teams のダイレクト ルーティング サービスをペアリングします。 詳細については、「[SBC を電話システムのダイレクト ルーティング サービスにペアリングする](direct-routing-configure.md)」を参照してください。 

3. この構成は、実質的にオンプレミス構成のミラーです。 オンライン構成は次の内容で構成されます。 
   - OnlineVoiceRoutingPolicy (Skype for Business Online のユーザーを移行する場合はオンプレミスの VoiceRoutingPolicy に基づき、エンタープライズ VoIP を使用してオンプレミスからユーザーを移行する場合は VoicePolicy に基づく)。
   - OnlinePSTNUsage オブジェクト (オンプレミスの PSTN 使用法に基づく)。 
   - OnlineVoiceRoute オブジェクト (オンプレミスの VoiceRoute に基づく)。 

詳細については、「[ダイレクト ルーティングを構成する](direct-routing-configure.md)」を参照してください。 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>移行時に EnterpriseVoiceEnabled プロパティを管理する 

ダイレクト ルーティングや Microsoft 通話プランを使用する場合、ユーザーは、PSTN 機能を利用できるようにするため、Azure AD で EnterpriseVoiceEnabled=true に指定する必要があります。  EnterpriseVoiceEnabled (EV-enabled) は、オンプレミスのディレクトリとクラウドの両方に存在するプロパティです (ポリシーではない)。 Teams で重要なのは、クラウドの値です。  EV-enabled がどのようにして true に設定されるかの正確なロジックは、次のシナリオによって決定されます。 

- ユーザーがオンプレミスの Skype for Business Server で EV-enabled になっており、Move-CsUser を使用してそのユーザーをクラウドに移行する前に電話システムのライセンスがそのユーザーに割り当てられている場合、そのオンライン ユーザーは EV-enabled=true でプロビジョニングされます。 

- 既存の TeamsOnly または Skype for Business Online ユーザーに電話システムのライセンスが割り当てられる場合は、EV-enabled は既定では true に設定されません。  オンプレミスのユーザーが、電話システムのライセンスを割り当てる前にクラウドに移行される場合も同様です。 どちらの場合も、管理者は次のコマンドレットを指定する必要があります。 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md) 

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[オンプレミスとクラウドの間でユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[会議移行サービス (MMS) を使用する](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

