---
title: オンプレミスとクラウドの間でユーザーを移動する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '概要: ハイブリッドに対して有効になっている Skype for Business Server のオンプレミス展開では、ユーザーをオンプレミス環境とクラウドの間で移動できます (Microsoft Teams または Skype for Business Online に移行した後)。'
ms.openlocfilehash: 998adf068dbfd360cb5a3e279320d1fee96f761f
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855946"
---
# <a name="move-users-between-on-premises-and-cloud"></a>オンプレミスとクラウドの間でユーザーを移動する

ハイブリッドに対して有効になっている Skype for Business Server のオンプレミス展開では、ユーザーをオンプレミス環境とクラウドの間で移動できます (Microsoft Teams または Skype for Business Online の場合は、その使用を中止する前に行います。 ユーザーのいる場所、つまり、オンプレミスまたはクラウドは、そのユーザーの Skype for Business ホームとして認識されます。

- オンプレミスのユーザーは、オンプレミスのサーバーとSkype for Businessします。
- ホームがオンラインのユーザーは、Skype for Business Online サービスとやり取りします。

*Teams のユーザーは、Skype for Business を使用しているかどうかに関わらず、Skype for Business ホームを最初から持っています。* オンプレミスのユーザーがSkype for Business (並べて) Teamsしている場合、それらのユーザーはオンプレミスに設定されます。 Teams Skype for Business を使用しているユーザーは、Teams クライアントから Skype for Business ユーザーと相互運用したり、フェデレーション組織のユーザーと Teams から通信したりする機能もありません。 このような機能は、ユーザーがオンプレミスからオンラインに移動Skype for Business TeamsOnly にした後にのみ完全に利用できます。 ユーザーをオンラインに移動すると、そのユーザーに Skype for Business Online (および、必要に応じて Teams) を使用することを許可するか、ユーザーを TeamsOnly にするかのいずれかを行えます。 ユーザーを Teams のみモードに移動し、すべての着信チャットと通話のルーティングが Teams クライアントに確実に送信されるのを強く推奨します。 詳細については、「Teamsと[](/microsoftteams/coexistence-chat-calls-presence)Teamsを使用する組織Skype for Business移行と相互運用性のガイダンス」を参照Teams[をSkype for Business。](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="prerequisites"></a>前提条件

ユーザーをクラウドに移動するための前提条件 (TeamsモードかオンラインSkype for Business前に行う必要があります。

- 組織では、「Configure Azure AD Connect」の説明に従って、Azure リソースを適切に構成し、ユーザーに関連するすべての属性を同期している[必要AD Connect。](configure-azure-ad-connect.md)
- Skype for Businessハイブリッドの構成」の説明に従って、ハイブリッド[Skype for Businessする必要があります](configure-federation-with-skype-for-business-online.md)。
- ユーザーには、オンライン (プラン 2) TeamsおよびSkype for Businessライセンスが割り当てられている必要があります。 オンラインの使用をSkype for Business後も、Skype for Businessオンライン ライセンスが必要です。  さらに、
    - ユーザーがオンプレミスでダイヤルイン会議を有効にしている場合は、ユーザーをオンラインに移動する前に、既定で Teams で電話会議ライセンスも割り当てられている必要があります。 クラウドへの移行後、ユーザーはクラウドの電話会議に対してプロビジョニングされます。 何らかの理由でユーザーをクラウドに移動するが、電話会議機能を使用しない場合は、パラメーターをで指定してこのチェックを `BypassAudioConferencingCheck` 上書きできます `Move-CsUser` 。
    - ユーザーがオンプレミスの エンタープライズ VoIPに対して有効になっている場合、ユーザーをオンラインに移動する前に、既定で 電話システム ライセンスが Teams に割り当てられている必要があります。 クラウドへの移行後、ユーザーはクラウドの電話システムに対してプロビジョニングされます。 何らかの理由でユーザーをクラウドに移動するが、電話システム 機能を使用しない場合は、 でパラメーターを指定してこのチェックを `BypassEnterpriseVoiceCheck` オーバーライドできます `Move-CsUser` 。


## <a name="moving-users"></a>ユーザーの移動

ユーザーがオンプレミスからクラウドに移動された場合:

- Teamsユーザーは、Skype for Businessユーザーとの相互運用性を有効にし、TeamsOnly の場合は他の組織とフェデレーションも行います。
- ユーザーは、Skype for Business のすべての機能について、Skype for Business Online サービスの使用をクラウドで開始します。
- オンプレミスからの連絡先はクラウドに移動されます (オンラインまたはオンラインTeamsまたはSkype for Businessされます。
- 今後スケジュールされた既存の会議は、オンラインに移行されます。ユーザーが TeamsOnly に直接移動された場合 (以下を参照)、会議は Teams 会議に変換され、それ以外の場合は会議は Skype for Business のままですが、オンプレミスではなくオンラインでホストされます。  会議の移行は非同期で行われ、ユーザーの移動から約 90 分後に開始されます。  会議の移行の状態を特定するには、[Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms) を使用します。 会議に先立ってアップロードされたコンテンツは移動されません。

オンプレミスとクラウドの間でユーザーを移動するには (Teams または Skype for Business Online に関係ありません)、Move-CsUser コマンドレットまたは Skype for Business 管理コントロール パネルのいずれかを使用します。どちらもオンプレミス ツールです。 これらのツールでは、3 種類の移動パスがサポートされています。

- [(Skype for Business Server) から直接](move-users-from-on-premises-to-teams.md)(オンプレミス) から [Teamsのみ] に移動します (また、Skype for Business Online に移動します)。  オンプレミスからオンプレミスに直接移動するTeamsのみ、使用するサーバーまたは Lync Server のバージョンに関係なく、Skype for Business Serverが自動的に実行されます。 この動作を取得するためにスイッチを指定 `-MoveToTeams` する必要がなくなりました。  
- [(オンプレミスSkype for Business Server) から [オンライン] Skype for Businessします](move-users-from-on-premises-to-skype-for-business-online.md)。 TeamsOnly にならずにユーザーを Skype for Business Online に移動する必要があるお客様は、まず TeamsOnly モードでユーザーをクラウドに移動し、次にユーザーモードを TeamsOnly 以外のユーザーモードに更新して、どちらかまたは Teams 管理センターを使用してこれを実現できます。 `Grant-CsTeamsUpgradePolicy` このオプションは、オンラインが廃止されたSkype for Business使用できなくなりました。
- [オンラインから (Teamsかどうかに関Teams)、オンプレミスに展開します](move-users-from-the-cloud-to-on-premises.md)。

> [!NOTE] 
> オンプレミスから TeamsOnly にユーザーを直接移動するために、Move-CsUser -MoveToTeams スイッチを指定する必要がなくなりました。 以前は、このスイッチが指定されていない場合、ユーザーは Skype for Business Server オンプレミスのホームから Skype for Business Online に移行し、モードは変更されません。 Move-CsUser を使用してユーザーをオンプレミスからクラウドに移動すると、ユーザーは自動的に TeamsOnly モードに割り当て、スイッチが実際に指定されたかどうかに関係なく、スイッチが指定された場合と同様に、オンプレミスからの会議が自動的に Teams 会議に変換されます。 `-MoveToTeams` 
> 

## <a name="required-administrative-credentials"></a>必要な管理者の資格情報

オンプレミスとクラウドの間でユーザーを移動するには、オンプレミスの Skype for Business Server 環境と Teams 組織の両方で十分な権限を持つアカウントを使用する必要があります。 必要なすべての特権を持つ 1 つのアカウントを使用するか、2 つのアカウントを使用できます。その場合は、オンプレミスの資格情報を使用してオンプレミス のツールにアクセスし、それらのツールで Teams 管理アカウントに追加の資格情報を提供します。  

- オンプレミス環境では、移動を実行するユーザーには、CSServerAdministrator の役割が必要Skype for Business Server。
- このTeams、移動を実行するユーザーは、次のいずれかの条件を満たしている必要があります。
  - ユーザーは、グローバル管理者ロールのメンバーです。
  - ユーザーは、管理者ロールとユーザー管理者ロールTeamsメンバーです。
  - ユーザーは、管理者ロールとユーザー管理者ロールSkype for Businessメンバーです。  

    > [!Important]
    > - Skype for Business 管理コントロール パネルを使用している場合は、上記のように、適切な役割を持つ Microsoft 365 アカウントの資格情報を提供するように求めるメッセージが表示されます。 .onmicrosoft.com で終わるアカウントを指定する必要があります。 それができない場合は、次のコマンドレットをMove-CsUserします。
    >- PowerShell で Move-CsUser を使用している場合は、.onmicrosoft.com で終わるアカウントを使用するか、コマンドレットで HostedMigrationOverrideUrl パラメーターも指定する場合は、Azure AD に同期されている任意のオンプレミス アカウントを使用できます。 ホストされた移行オーバーライド URL の値は、次の URL のバリアント型です。 https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>上記の URL で、XX を次のように決定された 2 文字または 3 文字で置き換えます。
    >   - PowerShell セッションTeams、次のコマンドレットを実行します。<br>`Get-CsTenant|ft identity`
    >   - 結果の値は、次の形式になります。<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >   - 2 桁または 3 桁のコードは、セクション DC=lyncXX001 に含まれる XX です。 2 文字のコードの場合は、数字の後に数字 (0a など) が続きます。 3 文字のコードの場合は、2 文字の後に数字 (jp1 など) が続きます。 すべての場合、XX コードの直後に 001 が表示されます。


## <a name="voice-configuration-requirements"></a>音声構成の要件

ユーザーがオンプレミスのエンタープライズボイス用に構成されている場合は、オンラインに移動する際に音声構成の更新を調整するか、テレフォニー機能なしで移行する必要があります。 使用可能なオプションは、ユーザーがオンラインにした後で、TeamsクライアントSkype for Business使用するかによって異なっています。

- ユーザーのテレフォニー プロバイダーを更新して、Microsoft 通話プラン [を使用できます](/microsoftteams/calling-plans-for-office-365)。 これは、ユーザーがクライアントを使用するか、クライアントTeams Skype for Businessです。
- 引き続きオンプレミス PSTN プロバイダーを使用できます。
  - 直接ルーティングを使用する音声Teamsを構成する[必要があります](/microsoftteams/direct-routing-plan)。 直接ルーティングは、ユーザーがオンプレミスからオンラインに移動された後にのみ使用できます。
  - オンラインに移動した後、Skype for Businessクライアントを使用する音声ユーザーは、音声機能用Skype for Business Hybridする必要があります。

ハイブリッド環境でのテレフォニー オプションとサポートのマトリックスの詳細については、「PSTN 接続を備えるハイブリッド環境のユーザー アカウント」 [を参照してください](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)。

## <a name="other-considerations"></a>その他の考慮事項

オンプレミスとオンラインの環境のポリシー (メッセージング、会議、通話の動作を制御するためのポリシーなど) は相互に独立しています。 オンプレミスからクラウドにユーザーを移動する前に、環境内のポリシーを構成してユーザーに割り当て、オンラインに移行するとすぐに適切な構成を行う必要があります。

## <a name="see-also"></a>関連項目

[オンプレミスから Teams にユーザーを移動する](move-users-from-on-premises-to-teams.md)

[ユーザーをオンプレミスから Skype for Business Online に移動する](move-users-from-on-premises-to-skype-for-business-online.md)

[Meeting Migration Service (MMS) のセットアップ](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[ダイレクト ルーティングを計画する](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
