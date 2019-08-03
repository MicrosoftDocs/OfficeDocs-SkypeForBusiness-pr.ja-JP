---
title: オンプレミスとクラウドの間でユーザーを移動する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
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
ms.openlocfilehash: b7e3ecc46af5a3043848d9291394c0bff7835883
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160636"
---
# <a name="move-users-between-on-premises-and-cloud"></a>オンプレミスとクラウドの間でユーザーを移動する

ハイブリッドに対応した Skype for Business Server のオンプレミス展開では、オンプレミス環境とクラウド (Microsoft Teams または Skype for Business Online のいずれか) 間でユーザーを移動することができます。 ユーザーが社内に設置されているか、クラウド内にあるかは、ユーザーの Skype for Business ホームと呼ばれます。

- オンプレミスに所属するユーザーは、オンプレミスの Skype for Business サーバーと対話します。
- オンラインに所属するユーザーは、Skype for Business Online サービスと対話することができます。

*Teams ユーザーには、Skype for business を使用しているかどうかにかかわらず、Skype for Business ホームがもともと用意されています。* Teams を使用しているオンプレミスの Skype for Business ユーザーがいる場合 (side-by-side) は、これらのユーザーはオンプレミスに所属しています。 オンプレミスの Skype for business を使用している teams には、Teams クライアントから Skype for business ユーザーとの相互運用を行うことはできません。また、チームからフェデレーション組織のユーザーとの通信を行うこともできません。 このような機能は、ユーザーがオンプレミスの Skype for Business からオンラインに移行した後にのみ使用できます。 ユーザーをオンラインに移行する場合は、Skype for Business Online (およびオプションで Teams) を使用できるようにするか、チームのみを作成することができます。 組織が既に Teams を使用している場合は、teams のみのモードに移行することを強くお勧めします。これにより、すべての受信チャットと通話のルーティングが Teams クライアントに記録されるようになります。 詳細については、「teams と skype for business の[共存](/microsoftteams/coexistence-chat-calls-presence)」および「skype for Business と[teams を使用する組織向けの相互運用性のガイダンス](/microsoftteams/migration-interop-guidance-for-teams-with-skype)」を参照してください。

## <a name="prerequisites"></a>前提条件

ユーザーをクラウドに移動するための前提条件 (Skype for Business のみか Teams のみ):

- 「 [AZURE Ad connect を構成](configure-azure-ad-connect.md)する」の説明に従って、組織には、Azure ad connect が適切に構成されており、ユーザーの関連するすべての属性を同期している必要があります。
- 「 [Configure skype For business hybrid](configure-federation-with-skype-for-business-online.md)」で説明されているように、Skype for business ハイブリッドを構成する必要があります。
- ユーザーには、Skype for Business Online (プラン 2) のライセンスが割り当てられている必要があり、Teams を使用する場合は Teams ライセンスも必要です。  さらに、次の機能も使用できます。
    - オンプレミスでユーザーのダイヤルイン会議が有効になっている場合、既定では、ユーザーが Office 365 で割り当てられた電話会議ライセンスを所有している必要があります。これを実行する前に、ユーザーをオンラインに移動します。 クラウドに移行されると、ユーザーはクラウドで電話会議用にプロビジョニングされます。 何らかの理由でユーザーをクラウドに移動するが、電話会議機能を使用しない場合は、 `BypassAudioConferencingCheck`パラメーターを指定してこのチェックを`Move-CsUser`無効にすることができます。
    - オンプレミスのエンタープライズ Voip がユーザーに対して有効になっている場合、ユーザーは既定で、ユーザーをオンラインに移行する前に、Office 365 で割り当てられた電話システムライセンスが必要です。 クラウドに移行すると、ユーザーはクラウドの電話システム用にプロビジョニングされます。 何らかの理由でユーザーをクラウドに移動し、電話システム機能を使用しない場合は、 `BypassEnterpriseVoiceCheck`パラメーターを指定してこのチェックを`Move-CsUser`無効にすることができます。


## <a name="moving-users"></a>ユーザーの移動

ユーザーがオンプレミスからクラウドに移動された場合:

- ユーザーは、すべての Skype for business 機能について、クラウドで Skype for Business Online サービスの使用を開始します。
- Teams ユーザーは、Skype for Business ユーザーとの相互運用性を有効にし、他の組織とのフェデレーションも可能になります。
- オンプレミスの連絡先は、クラウド (Skype for Business または Teams) に移動されます。
- 今後予定されている既存の会議はオンラインに移行されます。ユーザーが直接 Teams に移行される場合 (以下を参照)、会議は Teams 会議に変換されますが、それ以外の場合、会議は Skype for Business に移行されます。オンプレミスではなく、オンラインでホストされます。  会議の移行は非同期的に行われ、ユーザーの移動後約90分で開始されます。  会議の移行の状態を確認するには、 [csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)を使用できます。 会議の前にアップロードされたコンテンツは移動されないことに注意してください。

オンプレミスとクラウド (Teams または Skype for Business Online のいずれか) 間でユーザーを移動するには、2つのユーザーコマンドレットを使用するか、または Skype for Business 管理者コントロールパネルを使用します。どちらもオンプレミスツールです。 これらのツールは、3つの異なる移動パスをサポートしています。

- [Skype for Business Server (オンプレミス) から skype For Business Online に](move-users-from-on-premises-to-skype-for-business-online.md)接続します。
- [Skype For Business Server (オンプレミス) から Teams のみに直接](move-users-from-on-premises-to-teams.md)(これも、Skype for Business Online に移動されます)。  オンプレミスから Teams に直接移動するオプションは、skype for business Server 2019 と、Skype for Business Server 2015 の累積更新プログラム8でのみ利用できます。 以前のバージョンの Skype for business Server を使用している組織では、最初に Skype for business Online に移行することにより、ユーザーを Teams に移行することができます。
- [オンプレミス (Teams のみかどうかにかかわらず) のオンラインから](move-users-from-the-cloud-to-on-premises.md)。

## <a name="required-administrative-credentials"></a>必要な管理者資格情報

オンプレミスとクラウドの間でユーザーを移動するには、オンプレミスの Skype for Business Server 環境および Office 365 テナントの両方で十分な特権を持つアカウントを使用する必要があります。 必要なすべての権限を持つ1つのアカウントを使用するか、または2つのアカウントを使用することができます。この場合、オンプレミスの資格情報を使用してオンプレミスのツールにアクセスした後、それらのツールで Office 365 の追加の資格情報を提供することができます。管理アカウント。  

- オンプレミス環境では、移動を実行するユーザーは、Skype for Business Server で CSServerAdminstrator 者の役割を持っている必要があります。
- Office 365 では、移動を実行するユーザーはグローバル管理者であるか、または Skype for Business 管理者とユーザー管理者の両方の役割を持っている必要があります。  

    > [!Important]
    > - [Skype for Business 管理ツール] コントロールパネルを使用している場合は、前述のように、Office 365 アカウントの資格情報を適切な役割で提供するように求められます。 Onmicrosoft.com で終わるアカウントを指定する必要があります。 これができない場合は、ユーザーコマンドレットを使用します。
    >- PowerShell で CsUser を使用している場合は、onmicrosoft.com で終了するアカウントを使用するか、または、コマンドレットで HostedMigrationOverrideUrl パラメーターも指定している場合は、Azure AD に同期されたオンプレミスのアカウントを使用することができます。. ホストされた移行の上書き URL の値は、次の URL のバリアント型 (variant) です。https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>上記の URL では、次のようにして、XX を2文字または3文字に置き換えます。
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

オンプレミスの環境とオンライン環境でのポリシー (メッセージング、会議、通話の動作の制御など) は、独立しています。 環境内でポリシーを構成して、そのユーザーをオンプレミスからクラウドに移行する前にユーザーに割り当てることができます。これにより、それらのポリシーをオンラインに移行した直後に、適切な構成を行うことができます。

## <a name="see-also"></a>関連項目

[オンプレミスから Skype for Business Online へのユーザーの移動](move-users-from-on-premises-to-skype-for-business-online.md)

[オンプレミスから Teams へのユーザーの移動](move-users-from-on-premises-to-teams.md)

[会議移行サービス (MMS) のセットアップ](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[直接ルーティングを計画する](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
