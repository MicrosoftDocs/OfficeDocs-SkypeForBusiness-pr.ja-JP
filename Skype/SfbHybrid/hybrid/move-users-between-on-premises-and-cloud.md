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
description: '概要: ハイブリッドに対応した Skype for Business Server のオンプレミス展開では、オンプレミス環境とクラウド (Microsoft Teams または Skype for Business Online) の間でユーザーを移動することができます。'
ms.openlocfilehash: aea3bed7db6c7821d957aa0e6d56cbafd548edb7
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780086"
---
# <a name="move-users-between-on-premises-and-cloud"></a>オンプレミスとクラウドの間でユーザーを移動する

ハイブリッドが有効化されている Skype for Business Server のオンプレミス展開では、オンプレミス環境とクラウド (Microsoft Teams または Skype for Business Online) との間でユーザーを移動できます。 ユーザーのいる場所、つまり、オンプレミスまたはクラウドは、そのユーザーの Skype for Business ホームとして認識されます。

- オンプレミスに所属するユーザーは、オンプレミスの Skype for Business サーバーと対話します。
- ホームがオンラインのユーザーは、Skype for Business Online サービスとやり取りします。

*Teams ユーザーには、Skype for business を使用しているかどうかにかかわらず、Skype for Business ホームがもともと用意されています。* Teams を使用しているオンプレミスの Skype for Business ユーザーがいる場合 (side-by-side) は、これらのユーザーはオンプレミスに所属しています。 オンプレミスの Skype for business を使用している teams には、Teams クライアントから Skype for business ユーザーとの相互運用を行うことはできません。また、チームからフェデレーション組織のユーザーとの通信を行うこともできません。 このような機能は、ユーザーがオンプレミスの Skype for Business からオンラインに移行した後にのみ使用できます。 ユーザーをオンラインに移動すると、そのユーザーに Skype for Business Online (および、必要に応じて Teams) を使用することを許可するか、ユーザーを TeamsOnly にするかのいずれかを行えます。 組織が既に Teams を使用している場合は、ユーザーを TeamsOnly モードに移動することを強くお勧めします。これにより、すべての受信チャットと通話が Teams クライアントに配信されるルーティングを確保できます。 詳細については、「teams と skype for business の[共存](/microsoftteams/coexistence-chat-calls-presence)」および「skype for Business と[teams を使用する組織向けの相互運用性のガイダンス](/microsoftteams/migration-interop-guidance-for-teams-with-skype)」を参照してください。

## <a name="prerequisites"></a>前提条件

ユーザーをクラウドに移動するための前提条件 (Skype for Business のみか Teams のみ):

- 「 [AZURE Ad connect を構成](configure-azure-ad-connect.md)する」の説明に従って、組織には、Azure ad connect が適切に構成されており、ユーザーの関連するすべての属性を同期している必要があります。
- 「 [Configure skype For business hybrid](configure-federation-with-skype-for-business-online.md)」で説明されているように、Skype for business ハイブリッドを構成する必要があります。
- ユーザーに Skype for Business Online (プラン 2) のライセンスが割り当てられている必要があり、ユーザーが Teams を使用する場合は、ユーザーは Teams のライセンスも必要です。  さらに:
    - オンプレミスでユーザーのダイヤルイン会議が有効になっている場合、既定では、ユーザーが Office 365 で割り当てられた電話会議ライセンスを所有している必要があります。これを実行する前に、ユーザーをオンラインに移動します。 クラウドへの移行後、ユーザーはクラウドの電話会議に対してプロビジョニングされます。 何らかの理由でユーザーをクラウドに移動するが、電話会議機能を使用しない場合は、 `BypassAudioConferencingCheck`パラメーターを指定してこのチェックを`Move-CsUser`無効にすることができます。
    - オンプレミスのエンタープライズ Voip がユーザーに対して有効になっている場合、ユーザーは既定で、ユーザーをオンラインに移行する前に、Office 365 で割り当てられた電話システムライセンスが必要です。 クラウドへの移行後、ユーザーはクラウドの電話システムに対してプロビジョニングされます。 何らかの理由でユーザーをクラウドに移動し、電話システム機能を使用しない場合は、 `BypassEnterpriseVoiceCheck`パラメーターを指定してこのチェックを`Move-CsUser`無効にすることができます。


## <a name="moving-users"></a>ユーザーの移動

ユーザーがオンプレミスからクラウドに移動された場合:

- ユーザーは、Skype for Business のすべての機能について、Skype for Business Online サービスの使用をクラウドで開始します。
- Teams ユーザーは、Skype for Business ユーザーとの相互運用に対して有効化され、他の組織とのフェデレーションも可能になります。
- オンプレミスの連絡先は、クラウド (Skype for Business または Teams) に移動されます。
- 今後予定されている既存の会議はオンラインに移行されます。ユーザーが直接 Teams に移動した場合 (以下を参照)、会議は Teams 会議に変換されますが、会議はオンプレミスではなくオンラインでホストされるように移行されます。  会議の移行は非同期で行われ、ユーザーの移動から約 90 分後に開始されます。  会議の移行の状態を特定するには、[Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms) を使用します。 会議に先立ってアップロードされたコンテンツは移動されません。

オンプレミスとクラウド (Teams または Skype for Business Online のいずれか) 間でユーザーを移動するには、2つのユーザーコマンドレットを使用するか、または Skype for Business 管理者コントロールパネルを使用します。どちらもオンプレミスツールです。 これらのツールでは、3 種類の移動パスがサポートされています。

- [Skype for Business Server (オンプレミス) から skype For Business Online に](move-users-from-on-premises-to-skype-for-business-online.md)接続します。
- [Skype For Business Server (オンプレミス) から Teams に直接](move-users-from-on-premises-to-teams.md)(または、Skype For business Online にも移動) します。  オンプレミスから Teams に直接移動するオプションは、skype for business Server 2019 と、Skype for Business Server 2015 の累積更新プログラム8でのみ利用できます。 以前のバージョンの Skype for Business Server を使用している組織では、最初にユーザーを Skype for Business Online に移動し、次に、これらのユーザーがオンライン状態になったら TeamsOnly モードを適用することによりユーザーを TeamsOnly に移動できます。
- [オンプレミス (Teams のみかどうかにかかわらず) のオンラインから](move-users-from-the-cloud-to-on-premises.md)。

## <a name="required-administrative-credentials"></a>必要な管理者の資格情報

オンプレミスとクラウドの間でユーザーを移動するには、オンプレミスの Skype for Business Server 環境および Office 365 組織の両方で十分な特権を持つアカウントを使用する必要があります。 必要な権限がすべて含まれている 1 つのアカウントを使用することも、2 つのアカウントを使用することもできます。後者の場合、オンプレミスの資格情報を使用してオンプレミスのツールにアクセスし、これらのツールで Office 365 管理者アカウントの追加の資格情報を提供します。  

- オンプレミスの環境では、移動を実行するユーザーに Skype for Business Server の CSServerAdminstrator ロールが割り当てられている必要があります。
- Office 365 では、移動を実行するユーザーは、グローバル管理者であるか、Skype for Business 管理者ロールとユーザー管理者ロールの両方が割り当てられているかのいずれかである必要があります。  

    > [!Important]
    > - [Skype for Business 管理ツール] コントロールパネルを使用している場合は、前述のように、Office 365 アカウントの資格情報を適切な役割で提供するように求められます。 Onmicrosoft.com で終わるアカウントを指定する必要があります。 これができない場合は、ユーザーコマンドレットを使用します。
    >- PowerShell で CsUser を使用している場合は、onmicrosoft.com で終了するアカウントを使用するか、または、コマンドレットで HostedMigrationOverrideUrl パラメーターも指定している場合は、Azure AD に同期されたオンプレミスのアカウントを使用することができます。 ホストされた移行の上書き URL の値は、次の URL のバリアント型 (variant) です。https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>上記の URL では、次のようにして、XX を2文字または3文字に置き換えます。
    >   - Skype for Business Online の PowerShell セッションで、次のコマンドレットを実行します。<br>`Get-CsTenant|ft identity`
    >    - 結果の値は次の形式になります。<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - 2桁または3桁のコードは、セクション DC = lyncXX001 に含まれる XX です。 2文字のコードの場合、数字の後に数字 (0a など) が続きます。 3文字のコードでは、2文字の後に数字 (jp1 など) が続きます。 すべての場合において、XX コードの直後に001が表示されます。


## <a name="voice-configuration-requirements"></a>音声構成の要件

オンプレミスでエンタープライズ voip を使用するようにユーザーが構成されている場合は、オンラインに移行するときに音声構成の更新を調整するか、またはテレフォニー機能を使用せずに移行することができます。 利用可能なオプションは、ユーザーがオンラインになったときに Teams または Skype for Business クライアントを使用するかどうかによって異なります。

- [Microsoft 通話プラン](/microsoftteams/calling-plans-for-office-365)を使用するようにユーザーのテレフォニープロバイダーを更新することができます。 これは、ユーザーが Teams または Skype for Business クライアントを使用するかどうかを指定するオプションです。
- オンプレミスの PSTN プロバイダーを引き続き使用することができます。
  - Teams を使用する音声ユーザーは、[直接ルーティング](/microsoftteams/direct-routing-plan)用に構成されている必要があります。 直接ルーティングは、ユーザーがオンプレミスからオンラインに移行した後にのみ使用できます。
  - Skype for business クライアントをオンラインで移動した後で使用する音声ユーザーは、Skype for business ハイブリッド音声機能を使用するように構成する必要があります。

ハイブリッド環境でのテレフォニーオプションおよびサポートのマトリックスの詳細については、「 [PSTN 接続を使用したハイブリッド環境でのユーザーアカウント](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)」を参照してください。

## <a name="other-considerations"></a>その他の考慮事項

オンプレミスとオンラインの環境のポリシー (メッセージング、会議、通話の動作を制御するためのポリシーなど) は相互に独立しています。 環境内でポリシーを構成して、そのユーザーをオンプレミスからクラウドに移行する前にユーザーに割り当てることができます。これにより、それらのポリシーをオンラインに移行した直後に、適切な構成を行うことができます。

## <a name="see-also"></a>関連項目

[ユーザーをオンプレミスから Skype for Business Online に移動する](move-users-from-on-premises-to-skype-for-business-online.md)

[オンプレミスから Teams にユーザーを移動する](move-users-from-on-premises-to-teams.md)

[Meeting Migration Service (MMS) のセットアップ](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[ダイレクト ルーティングを計画する](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
