---
title: PSTN にアップグレードする際の考慮事項 TeamsからSkype for Business
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 音声から音声へのアップグレードに関するSkype for Businessに関するTeams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c19c1860c3a351cd7ed6a6240e20dc253f204ab1
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2022
ms.locfileid: "62180890"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>オンプレミスからオンプレミスへのアップグレードTeams PSTN Skype for Business関する考慮事項

この記事では、PSTN (公衆交換電話網) にアップグレードする際の考慮事項について説明Teams。

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

次の記事では、アップグレードの重要な概念と共存動作について説明します。

- [Teams と Skype for Business の共存](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存モード - リファレンス](migration-interop-guidance-for-teams-with-skype.md)
- [Teams のクライアント エクスペリエンスおよび共存モードへの準拠](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - アカウント電話システムのTeamsは、ユーザーのアカウントに [Teams のみ] モードのアップグレード ポリシーが割り当Teams場合にのみサポートされます。  
 > - アプリケーション電話システムをSkype for Businessは、ユーザーのアカウントに SfB モードで Teams アップグレード ポリシーが割り当てられている場合にのみサポートされます。 
 > - 電話システムアカウントに Islands モードのアップグレード ポリシーが割り当てられている場合Teamsはサポートされません。
 > - Skype for Business からのすべての呼び出しの転送、チーム通話グループ、および委任設定は移行されません。また、Teams 用に再作成する必要があります。
 > - クラウド音声機能のMicrosoft Teams概要と、組織に最適な Microsoft 音声ソリューションの決定に役立つ情報については、「音声ソリューションを計画する」をTeams[してください](cloud-voice-landing-page.md)。


## <a name="pstn-calling-scenarios"></a>PSTN 通話シナリオ

TeamsOnly モードに移行する場合、次の 4 つの呼び出しシナリオが考えられます。

- [Microsoft 通話プランを使用している Skype for Business Online のユーザー](#from-skype-for-business-online-with-microsoft-calling-plans)。 アップグレードすると、このユーザーは Microsoft 通話プランを引き続き使用します。

- [Skype for Business Online のユーザー](#from-skype-for-business-online-with-on-premises-voice) 。オンプレミスまたは Cloud Connector Edition Skype for Business音声機能を使用します。 TeamsOnly ユーザーが PSTN 機能を持つには、ユーザーの直接ルーティングへの移行に合Teamsアップグレードを調整する必要があります。

- [オンプレミスで Skype for Business](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)を使用するエンタープライズ VoIP、オンラインに移行し、オンプレミスの PSTN 接続を維持します。  このユーザーを Teams に移行するには、ユーザーのオンプレミス Skype for Business アカウントをクラウドに移動し、ユーザーの直接ルーティングへの移行に合った調整を行う必要があります。 

- [エンタープライズ VoIP を使用している Skype for Business オンプレミスのユーザー](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)のうち、オンラインに移行して、Microsoft 通話プランを使用するユーザー。  このユーザーを Teamsするには、ユーザーのオンプレミス アカウントをクラウドSkype for Businessする必要があります。 移行を A) そのユーザーの電話番号のポートを Microsoft 通話プランまたは B) に調整して、利用可能なリージョンから新しいサブスクライバー番号を割り当てる必要があります。

この記事では、概要のみを説明します。 詳細については、「[電話システムのダイレクト ルーティング](direct-routing-landing-page.md)」および「[通話プラン](calling-plan-landing-page.md)」を参照してください。 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Microsoft 通話プランを使用している Skype for Business Online からの場合 

このシナリオは、音声を含む最も簡単なアップグレード シナリオです。 

1. ユーザーに Teams ライセンスが割り当てられていることを確認します。 既定では、ライセンスまたはライセンスを割りMicrosoft 365割りOffice 365、Teams有効になります。 以前にライセンスを無効にしたTeams、何もする必要はありません。

2.  ユーザーが既に電話番号を指定して Microsoft 通話プランを使用している場合に必要な変更は、そのユーザーに TeamsUpgradePolicy で TeamsOnly モードを割り当てることのみです。 TeamsOnly モードを割り当てる前に、着信 PSTN 通話はユーザーのクライアントSkype for Businessされます。 TeamsOnly モードにアップグレードすると、着信 PSTN 通話はユーザーの Teams クライアントに配信されます。  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>オンプレミス音声を使用している Skype for Business Online からの場合

このシナリオでは、ユーザーは既にオンライン Skype for Businessしています。 ユーザーの PSTN 接続はオンプレミスで、ハイブリッド モードまたは Cloud Connector Edition Skype for Business Serverを使用します。 PSTN 機能を使用してこれらのユーザーを TeamsOnly モードに移行するには、ユーザーに直接ルーティングを有効にする必要があります。 直接ルーティングでは、PSTN トランクはオンプレミスのセッション ボーダー コントローラー (SBC) を介して直接ルーティング サービスに接続します。

基本的なステップを次に示します。  ステップ 1 から 4 は、提案されている順序で並んでいますが、任意の順序で実行できます。 これらの手順は、手順 5 の前に完了する必要があります。

1. テナント全体のポリシーを Skype for Business モードの 1 つに設定する場合は、前に説明したように、既存の Islands ユーザーを明示的に割り当て、そのユーザーを引き継がしてください。

2. ダイレクト ルーティング用にテナントを構成します。 「[ダイレクト ルーティングのテナントごとの構成の概要](#summary-of-per-tenant-configuration-of-direct-routing)」を参照してください。

3. 必要に応じて、これらのTeamsポリシー (TeamsMessagingPolicy、TeamsMeetingPolicy など) を構成します。 いつでも poicies を構成できます。 ただし、アップグレード時にユーザーが正しい構成を持つ必要がある場合は、ユーザーを TeamsOnly モードにアップグレードする前に、これらのポリシーを構成します。

4. 選択したユーザーに音声移行の準備をします。 
   - 必要に応じて、Teams ライセンスを割り当てます。  ユーザーが Skype for Business Online オンプレミス音声で既に機能している場合、ユーザーは既にプラン 2 と Skype for Business システムMicrosoft 電話しています。 両方のプラン (Skype for Business Online プラン 2 のライセンスを含む) を有効なままにしておきます。  
   - 目的の OnlineVoiceRoutingPolicy を割り当てます。 

5. これらのステップは相互に合うように調整する必要があります。 

   - このMicrosoft 365またはOffice 365、ユーザーを TeamsOnly モード (Grant-CsTeamsUpgradePolicy) にアップグレードします。
   - SBC で、通話をオンプレミスの仲介サーバーではなくダイレクト ルーティングに送信することにより、音声ルーティングが着信通話を許可するように構成します。


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>エンタープライズ VoIP を使用している Skype for Business Server オンプレミスからダイレクト ルーティングに移行する場合

このシナリオでは、ユーザーは引き続きオンプレミスSkype for Businessホームです。 ユーザーの PSTN 接続もオンプレミスです。 PSTN 機能を使用してこのユーザーを TeamsOnly モードに移行するには、ユーザーに直接ルーティングを有効にしてから、ユーザーをクラウドに移動する必要があります。 
 
基本的なステップを次に示します。 ステップ 1 から 5 は、提案されている順序で並んでいますが、任意の順序で実行できます。 手順 6 の前に、手順 1 ~ 5 を完了する必要があります。

1. テナント全体のポリシーを Skype for Business のモードの 1 つに設定する予定の場合は、前述のように既存のアイランド ユーザーにアイランド モードを明示的に割り当てることにより、それらのユーザーを必ず grandfather 化してください。

2. まだ構成していない場合は、[Skype for Business Hybrid 用に組織を構成](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)します。

3. ダイレクト ルーティング用にテナントを構成します。 「[ダイレクト ルーティングのテナントごとの構成の概要](#summary-of-per-tenant-configuration-of-direct-routing)」を参照してください。

4. 必要に応じて、これらのTeamsポリシー (TeamsMessagingPolicy、TeamsMeetingPolicy など) を構成します。 ポリシーは、いつでも構成できます。 ただし、アップグレード時にユーザーが正しい構成を持つ必要がある場合は、ユーザーを TeamsOnly にアップグレードする前に、これらのポリシーを構成します。

5. 必要に応じてMicrosoft 365割りOffice 365割り当てるか、ライセンスを割り当てる必要があります。  ユーザーは、オンライン プラン 2 Teamsと Skype for Businessの両方を持っている必要電話システム。 Skype for Business Online プラン 2 が無効になっている場合は、もう一度有効にします。  

6. これらのステップは相互に合うように調整する必要があります。 

   - オンプレミスの Skype for Business ツールを使用し、-MoveToTeams スイッチを指定して Move-CsUser を実行します。 -MoveToTeams スイッチをサポートしていないバージョンの Skype for Business Server を使用している場合は、まず Move-CsUser を実行してから、テナントリモート PowerShell または Teams 管理コンソールで TeamsOnly モードを割り当てる必要があります。

   - SBC で、通話をオンプレミスの仲介サーバーではなくダイレクト ルーティングに送信することにより、音声ルーティングが着信通話を許可するように構成します。 

   - [Microsoft 365 または Office 365: 関連する OnlineVoiceRoutingPolicy を割り当て、発信呼び出しを有効にする。 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>エンタープライズ VoIP を使用している Skype for Business Server オンプレミスから Microsoft 通話プランに移行する場合

このシナリオでは、ユーザーは引き続きオンプレミスSkype for Businessホームです。 ユーザーの PSTN 接続もオンプレミスです。 PSTN 機能を使用してこのユーザーを TeamsOnly モードに移行するには、ユーザーをクラウドに移動し、その番号を古い通信事業者から Microsoft 通話プランに移行するか、新しい番号をユーザーに割り当てる必要があります。 

基本的なステップを次に示します。ステップ 1 から 5 は、提案されている順序で並んでいますが、任意の順序で実行できます。 手順 6 の前に、手順 1 ~ 5 を完了する必要があります。 

1. テナント全体のポリシーを Skype for Business のモードの 1 つに設定する予定の場合は、前述のように既存のアイランド ユーザーにアイランド モードを明示的に割り当てることにより、それらのユーザーを必ず grandfather 化してください。 

2. まだ構成していない場合は、[Skype for Business Hybrid 用に組織を構成](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)します。 

3. 必要に応じて、これらのTeamsポリシー (TeamsMessagingPolicy、TeamsMeetingPolicy など) を構成します。 ポリシーは、いつでも構成できます。 ただし、アップグレード時にユーザーが正しい構成を持つ必要がある場合は、ユーザーを TeamsOnly にアップグレードする前に、これらのポリシーを構成します。 

4. 必要に応じてMicrosoft 365割りOffice 365割り当てるか、ライセンスを割り当てる必要があります。ユーザーは、オンライン プラン 2 Teamsと Skype for Businessの両方を持っている必要電話システム。 Skype for Business Online プラン 2 が無効になっている場合は、もう一度有効にします。  

5. ユーザーの電話番号を取得します。 (詳細については、「[組織の電話番号を管理する](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください)。

   - 番号を再利用する場合は、運送業者に移植要求を送信します。  
   - または、直接 Microsoft から新しい番号を取得することもできます。 

6. ユーザーをアップグレードし、必要に応じて LineUri を割り当てる。 オンプレミスの Skype for Business ツールを使用し、-MoveToTeams スイッチを指定して Move-CsUser を実行します。  

    - 番号を Microsoft に移植する場合は、この操作のタイミングを調整して、ポートが発生するときに発生するようにする必要があります。 

    - Microsoft の新しい番号を使用している場合は、Set-CsPhoneNumberAssignment を使用してユーザーをオンラインに移動した後、ユーザーの LineUri を変更する必要があります。  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>ダイレクト ルーティングのテナントごとの構成の概要 

1. [このリスト](direct-routing-border-controllers.md)を確認して、ご利用のセッション ボーダー コントローラー (SBC) がダイレクト ルーティングでサポートされていることを確認します。 また、ファームウェアの正しいバージョンを使用していることを確認します。  

2. オンプレミスの SBC と Teams のダイレクト ルーティング サービスをペアリングします。 詳細については、「[SBC を電話システムのダイレクト ルーティング サービスにペアリングする](direct-routing-configure.md)」を参照してください。 

3. この構成は、実質的にオンプレミス構成のミラーです。 オンライン構成は次の内容で構成されます。 
   - OnlineVoiceRoutingPolicy (Skype for Business Online のユーザーを移行する場合はオンプレミスの VoiceRoutingPolicy に基づき、エンタープライズ VoIP を使用してオンプレミスからユーザーを移行する場合は VoicePolicy に基づく)。
   - OnlinePSTNUsage オブジェクト (オンプレミスの PSTN 使用法に基づく)。 
   - OnlineVoiceRoute オブジェクト (オンプレミスの VoiceRoute に基づく)。 

詳細については、「[ダイレクト ルーティングを構成する](direct-routing-configure.md)」を参照してください。 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>移行時に EnterpriseVoiceEnabled プロパティを管理する 

ダイレクト ルーティングや Microsoft 通話プランを使用する場合、ユーザーは、PSTN 機能を利用できるようにするため、Azure AD で EnterpriseVoiceEnabled=true に指定する必要があります。  EnterpriseVoiceEnabled (EV-enabled) は、オンプレミスのディレクトリとクラウドの両方に存在するプロパティです (ポリシーではない)。 Teams で重要なのは、クラウドの値です。  EV-enabled がどのようにして true に設定されるかの正確なロジックは、次のシナリオによって決定されます。 

- ユーザーがオンプレミスの Skype for Business Server で EV-enabled になっており、Move-CsUser を使用してそのユーザーをクラウドに移行する前に電話システムのライセンスがそのユーザーに割り当てられている場合、そのオンライン ユーザーは EV-enabled=true でプロビジョニングされます。 

- 既存の TeamsOnly または Skype for Business Online ユーザーに電話システムのライセンスが割り当てられる場合は、EV-enabled は既定では true に設定されません。 オンプレミスのユーザーが、電話システムのライセンスを割り当てる前にクラウドに移行される場合も同様です。 どちらの場合も、管理者は次のコマンドレットを指定する必要があります。 

  ```PowerShell
  Set-CsPhoneNumberAssignment -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>関連リンク

[音声ソリューションTeams計画する](cloud-voice-landing-page.md)

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md) 

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[オンプレミスとクラウドの間でユーザーを移動する](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[会議移行サービス (MMS) を使用する](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
