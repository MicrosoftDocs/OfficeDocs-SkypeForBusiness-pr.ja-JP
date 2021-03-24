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
description: '概要: ハイブリッドに対して有効になっている Skype for Business Server のオンプレミス展開では、オンプレミス環境とクラウドの間でユーザーを移動できます (Microsoft Teams または Skype for Business Online に移動できます)。'
ms.openlocfilehash: b4b354a6a43ab58740a053f86d9b7da1faaeb0da
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110673"
---
# <a name="move-users-between-on-premises-and-cloud"></a>オンプレミスとクラウドの間でユーザーを移動する

ハイブリッドが有効化されている Skype for Business Server のオンプレミス展開では、オンプレミス環境とクラウド (Microsoft Teams または Skype for Business Online) との間でユーザーを移動できます。 ユーザーのいる場所、つまり、オンプレミスまたはクラウドは、そのユーザーの Skype for Business ホームとして認識されます。

- オンプレミスのユーザーは、オンプレミスの Skype for Business サーバーとやり取りします。
- ホームがオンラインのユーザーは、Skype for Business Online サービスとやり取りします。

*Teams ユーザーは、Skype for Business を使用するかどうかに関して、本質的に Skype for Business ホームを持っています。* Teams も使用しているオンプレミスの Skype for Business ユーザー (並べて) がある場合、それらのユーザーはオンプレミスに設定されます。 Skype for Business をオンプレミスに持つ Teams ユーザーは、Teams クライアントから Skype for Business ユーザーと相互運用する機能も、フェデレーション組織のユーザーと Teams から通信する機能もありません。 このような機能は、ユーザーがオンプレミスの Skype for Business からオンラインに移動された後にのみ使用できます。 ユーザーをオンラインに移動すると、そのユーザーに Skype for Business Online (および、必要に応じて Teams) を使用することを許可するか、ユーザーを TeamsOnly にするかのいずれかを行えます。 組織が既に Teams を使用している場合は、ユーザーを TeamsOnly モードに移動することを強くお勧めします。これにより、すべての受信チャットと通話が Teams クライアントに配信されるルーティングを確保できます。 詳細については、「Teams と Skype for Business の共存」および [「Teams と Skype for Business](/microsoftteams/coexistence-chat-calls-presence) を使用する組織の移行と相互運用性のガイダンス [」を参照してください](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。

## <a name="prerequisites"></a>前提条件

ユーザーをクラウドに移動するための前提条件 (Skype for Business Only または Teams Only モードの場合):

- 組織では、「Azure AD Connect の構成」の説明に従って、Azure AD AD Connect が正しく構成され、ユーザーに [関連するすべての属性を同期している必要があります](configure-azure-ad-connect.md)。
- 「Skype for Business ハイブリッドの構成」の説明に従って [、Skype for Business ハイブリッドを構成する必要があります](configure-federation-with-skype-for-business-online.md)。
- ユーザーに Skype for Business Online (プラン 2) のライセンスが割り当てられている必要があり、ユーザーが Teams を使用する場合は、ユーザーは Teams のライセンスも必要です。  さらに:
    - ユーザーがオンプレミスでダイヤルイン会議を有効にしている場合、既定では、ユーザーをオンラインに移動する前に、Microsoft 365 または Office 365 で割り当てられた電話会議ライセンスも割り当てられている必要があります。 クラウドへの移行後、ユーザーはクラウドの電話会議に対してプロビジョニングされます。 何らかの理由でユーザーをクラウドに移動するが、電話会議機能を使用しない場合は、パラメーターをで指定してこのチェックを `BypassAudioConferencingCheck` 上書きできます `Move-CsUser` 。
    - ユーザーがオンプレミスの エンタープライズ VoIP に対して有効になっている場合、ユーザーをオンラインに移動する前に、既定で Microsoft 365 または Office 365 で電話システム ライセンスが割り当てられている必要があります。 クラウドへの移行後、ユーザーはクラウドの電話システムに対してプロビジョニングされます。 何らかの理由でユーザーをクラウドに移動し、電話システム機能を使用しない場合は、パラメーターをで指定してこのチェックを `BypassEnterpriseVoiceCheck` 上書きできます `Move-CsUser` 。


## <a name="moving-users"></a>ユーザーの移動

ユーザーがオンプレミスからクラウドに移動された場合:

- ユーザーは、Skype for Business のすべての機能について、Skype for Business Online サービスの使用をクラウドで開始します。
- Teams ユーザーは、Skype for Business ユーザーとの相互運用に対して有効化され、他の組織とのフェデレーションも可能になります。
- オンプレミスからの連絡先は、クラウド (Skype for Business または Teams) に移動されます。
- 今後スケジュールされた既存の会議は、オンラインに移行されます。ユーザーが TeamsOnly に直接移動された場合 (以下を参照)、会議は Teams 会議に変換され、それ以外の場合は会議は Skype for Business のままですが、オンプレミスではなくオンラインでホストされるので移行されます。  会議の移行は非同期で行われ、ユーザーの移動から約 90 分後に開始されます。  会議の移行の状態を特定するには、[Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms) を使用します。 会議に先立ってアップロードされたコンテンツは移動されません。

オンプレミスとクラウドの間でユーザーを移動するには (Teams または Skype for Business Online に関係ありません)、Move-CsUser コマンドレットまたは Skype for Business Admin コントロール パネルのいずれかを使用します。どちらもオンプレミス ツールです。 これらのツールでは、3 種類の移動パスがサポートされています。

- [Skype for Business Server (オンプレミス) から Skype for Business Online まで](move-users-from-on-premises-to-skype-for-business-online.md)。
- [Skype for Business Server (オンプレミス)](move-users-from-on-premises-to-teams.md) から Teams Only (Skype for Business Online にも移動) に直接移動します。  オンプレミスから Teams に直接移動するオプションは、Skype for Business Server 2019 および Skype for Business Server 2015 の累積的な更新プログラム 8 で利用できます。 以前のバージョンの Skype for Business Server を使用している組織では、最初にユーザーを Skype for Business Online に移動し、次に、これらのユーザーがオンライン状態になったら TeamsOnly モードを適用することによりユーザーを TeamsOnly に移動できます。
- [オンライン (Teams のみかどうか)](move-users-from-the-cloud-to-on-premises.md)からオンプレミスまで。

## <a name="required-administrative-credentials"></a>必要な管理者の資格情報

オンプレミスとクラウドの間でユーザーを移動するには、オンプレミスの Skype for Business Server 環境と Microsoft 365 または Office 365 組織の両方で十分な特権を持つアカウントを使用する必要があります。 必要なすべての特権を持つ 1 つのアカウントを使用するか、2 つのアカウントを使用できます。その場合は、オンプレミスの資格情報を使用してオンプレミス ツールにアクセスし、それらのツールでは、Microsoft 365 または Office 365 管理アカウントに対して追加の資格情報を提供します。  

- オンプレミスの環境では、移動を実行するユーザーに Skype for Business Server の CSServerAdminstrator ロールが割り当てられている必要があります。
- Microsoft 365 および Office 365 では、移動を実行するユーザーはグローバル管理者か、Skype for Business Administrator とユーザー管理者の両方の役割を持っている必要があります。  

    > [!Important]
    > - Skype for Business Admin コントロール パネルを使用している場合は、上記で説明したように、適切な役割を持つ Microsoft 365 または Office 365 アカウントの資格情報を提供するように求めるメッセージが表示されます。 .onmicrosoft.com で終わるアカウントを指定する必要があります。 それができない場合は、次のコマンドレットをMove-CsUserします。
    >- PowerShell で Move-CsUser を使用している場合は、.onmicrosoft.com で終わるアカウントを使用するか、コマンドレットで HostedMigrationOverrideUrl パラメーターも指定する場合は、Azure AD に同期されている任意のオンプレミス アカウントを使用できます。 ホストされた移行オーバーライド URL の値は、次の URL のバリアント型です。 https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>上記の URL で、XX を次のように決定された 2 文字または 3 文字で置き換えます。
    >   - Skype for Business Online PowerShell セッションで、次のコマンドレットを実行します。<br>`Get-CsTenant|ft identity`
    >    - 結果の値は、次の形式になります。<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - 2 桁または 3 桁のコードは、セクション DC=lyncXX001 に含まれる XX です。 2 文字のコードの場合は、数字の後に数字 (0a など) が続きます。 3 文字のコードの場合は、2 文字の後に数字 (jp1 など) が続きます。 すべての場合、XX コードの直後に 001 が表示されます。


## <a name="voice-configuration-requirements"></a>音声構成の要件

ユーザーがオンプレミスのエンタープライズボイス用に構成されている場合は、オンラインに移動する際に音声構成の更新を調整するか、テレフォニー機能なしで移行する必要があります。 使用可能なオプションは、ユーザーがオンラインにした後に Teams クライアントまたは Skype for Business クライアントを使用するかどうかによって異なっています。

- ユーザーのテレフォニー プロバイダーを更新して、Microsoft 通話プラン [を使用できます](/microsoftteams/calling-plans-for-office-365)。 これは、ユーザーが Teams クライアントまたは Skype for Business クライアントを使用するかどうかのオプションです。
- 引き続きオンプレミス PSTN プロバイダーを使用できます。
  - Teams を使用する音声ユーザーは、直接ルーティング用に [構成する必要があります](/microsoftteams/direct-routing-plan)。 直接ルーティングは、ユーザーがオンプレミスからオンラインに移動された後にのみ使用できます。
  - オンラインに移動した後に Skype for Business クライアントを使用する音声ユーザーは、Skype for Business ハイブリッド音声機能用に構成する必要があります。

ハイブリッド環境でのテレフォニー オプションとサポートのマトリックスの詳細については、「PSTN 接続を備えるハイブリッド環境のユーザー アカウント」 [を参照してください](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)。

## <a name="other-considerations"></a>その他の考慮事項

オンプレミスとオンラインの環境のポリシー (メッセージング、会議、通話の動作を制御するためのポリシーなど) は相互に独立しています。 オンプレミスからクラウドにユーザーを移動する前に、環境内のポリシーを構成してユーザーに割り当て、オンラインに移行するとすぐに適切な構成を行う必要があります。

## <a name="see-also"></a>関連項目

[ユーザーをオンプレミスから Skype for Business Online に移動する](move-users-from-on-premises-to-skype-for-business-online.md)

[オンプレミスから Teams にユーザーを移動する](move-users-from-on-premises-to-teams.md)

[Meeting Migration Service (MMS) のセットアップ](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[ダイレクト ルーティングを計画する](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)