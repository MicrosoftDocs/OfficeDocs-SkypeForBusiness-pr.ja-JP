---
title: オンプレミスとクラウドの間でユーザーの移動
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: '概要: Skype のハイブリッドが有効になっているビジネス サーバーの設置型展開、ユーザーを移動できます、オンプレミス環境とクラウド (マイクロソフトのチームにするかオンライン ビジネスの Skype) の間で.'
ms.openlocfilehash: 492a2a7d14af77bc0b90afe03f0d36de0f830129
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247692"
---
# <a name="move-users-between-on-premises-and-cloud"></a>オンプレミスとクラウドの間でユーザーの移動

Skype ハイブリッドが有効になっているビジネス サーバー用の設置型展開、オンプレミス環境とクラウド (マイクロソフトのチームにするかオンライン ビジネスの Skype) の間でユーザーを移動できます。 ユーザーが存在するかどうか設置型またはクラウドでのビジネス ホーム ページ用のユーザーの Skype と呼びます。

- 施設内に置かれているユーザーは、ビジネスのサーバーの設置型の Skype と対話します。
- オンラインが置かれているユーザーは、オンライン ビジネス サービスの Skype と対話可能性があります。

*チームのユーザーでは、Skype のビジネス ホームでは、本質的にあるか、ビジネスの Skype を使用するかどうか。* チーム (並べて表示) を使用しているビジネス ユーザー向けの設置型の Skype を使っている場合は、施設内でそれらのユーザーが配置されています。 設置型のビジネス用の Skype でのチームのユーザーには、チーム、クライアントからのビジネス ユーザー向けに、Skype と相互運用することはありませんも、それらと通信できるチームからフェデレーション組織のユーザーです。 このような機能をできるは、ユーザーを移動した後ビジネス用の Skype から社内設置型のオンラインにするだけです。 ユーザーをオンラインに移動すると、オンライン ビジネスなど、必要に応じて、チームの Skype を使用することを許可できますか、またはさせることができますチームのみです。 組織は既にチームを使用している場合は、チームのみのモードで、チームのクライアントですべての着信のチャットと通話のルーティングが及ぶことを維持するために移動することを強くお勧めします。 詳細については、[ビジネスの Skype でのチームの共存](/microsoftteams/coexistence-chat-calls-presence)と[移行しチームと、ビジネス用の Skype を使用する組織の相互運用性ガイド](/microsoftteams/migration-interop-guidance-for-teams-with-skype)を参照してください。

## <a name="prerequisites"></a>必要条件

(Skype ビジネスのみまたはチームのみのモードにするかどうか) をクラウドに移行するユーザーを移動するのには前提条件:

- 組織では、Azure AD 接続が正しく構成されている必要があり、[構成の Azure AD 接続](configure-azure-ad-connect.md)の説明に従って、ユーザーのすべての関連属性が同期します。
- [ビジネスのハイブリッド構成の Skype](configure-federation-with-skype-for-business-online.md)の説明に従って、Skype のビジネスのハイブリッドを構成しなければなりません。
- ユーザー割り当てる必要がありますライセンスの Skype ビジネス online (プラン 2) があり、チームを使用するには、必要がありますもチームのライセンスです。  さらに：
    - ダイヤルイン会議用の設置型、ユーザーには、オーディオ会議のライセンスを実行する前に、Office 365 に割り当てられている必要があります。 既定ではユーザーが有効な場合は、オンライン ユーザーを移動します。 クラウドへの移行、ユーザーがクラウドでの音声会議を準備します。 指定してこのチェックをオーバーライドするにはいくつかの理由でユーザーをクラウドに移動するが、音声会議機能を使用する場合は、`BypassAudioConferencingCheck`のパラメーター `Move-CsUser`。
    - 社内でのエンタープライズ VoIP のユーザーが有効な場合、既定でユーザー ライセンスが必要電話システム ユーザーをオンラインに移動する前に、Office 365 に割り当てられています。 1 回、クラウド内の電話システムのユーザーをクラウドに移行済みが準備されます。 指定してこのチェックをオーバーライドするにはいくつかの理由でユーザーをクラウドに移行するが、電話システムの機能を使用する場合は、`BypassEnterpriseVoiceCheck`のパラメーター `Move-CsUser`。


## <a name="moving-users"></a>ユーザーの移動

ユーザーを移動するとき、オンプレミスからクラウドに移行します。

- ユーザーは、クラウドでのビジネスのオンライン サービスのビジネス機能のため、Skype の Skype を使用してを起動します。
- ビジネス ユーザーは、Skype でチームのユーザーが相互運用性を有効になり、他の組織とも統合します。
- 設置型からの連絡先は、(ビジネス用の Skype)、またはチームのいずれかのクラウドに移動されます。
- 今後予定されている既存の会議主催者は、オンラインに移行されます。 会議の移行では、非同期的に発生し、ユーザーを移動した後、約 90 分間を開始します。  会議の移行のステータスを確認するのには、 [Get csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)を使用できます。 会議を行う前にアップロードされたすべてのコンテンツが移動されていないことに注意してください。

設置型とクラウド (チームにするかオンライン ビジネスの Skype) の間でユーザーを移動、ビジネス管理者のコントロール パネルの移動 CsUser コマンドレット、または、Skype のいずれかを使用して、どちらも設置型のツールです。 これらのツールは、次の 3 つの異なる移動パスをサポートします。

- [から Skype](move-users-from-on-premises-to-skype-for-business-online.md)します。
- [ビジネス上のサーバー (設置型) のチームだけに直接 Skype から](move-users-from-on-premises-to-teams.md)(なるもに移動 Skype のオンライン ビジネス)。  ビジネス サーバー 2019 の Skype と Skype ビジネス サーバー 2015 用の累積的な更新の 8 チームのみに設置型から直接移動するオプションがあります。 Business Server の以前のバージョンの Skype を使用する組織は、最初に移動して Skype のビジネス オンライン、およびそれらがオンラインになったらこれらのユーザーに TeamsOnly モードを適用して、チームだけにユーザーを移動できます。
- [オンラインから (かどうかのみかをチーム) に、社内設置型の](move-users-from-the-cloud-to-on-premises.md)です。

## <a name="required-administrative-credentials"></a>必要な管理者資格情報

設置型とクラウドの間でユーザーを移動するに Office 365 のテナントのようにも、ビジネスのサーバー環境の両方、Skype の設置に十分な特権を持つアカウントを使用する必要があります。 必要なすべての権限を持つ 1 つのアカウントを使用することができますか、または 2 つのアカウントを使用することができます、アクセスする場合に設置型のツールを使用して、オンプレミスの資格情報とし、これらのツールでを指定する追加の資格情報、Office 365 の管理者アカウントです。  

- オンプレミス環境で移動を実行するユーザーはビジネス サーバーの Skype の CSServerAdminstrator ロールが必要です。
- 、Office 365 でユーザーの移動を実行する必要がありますグローバル管理者であるか、または両方の Skype ビジネス管理者およびユーザー管理者の役割を持つ必要があります。  

    > [!Important]
    > - ビジネス管理者のコントロール パネルで、Skype を使用している場合は、上記に記載したように、適切なロールを持つ、Office 365 アカウントの資格情報を入力が求められます。 終了するアカウントを指定する必要があります。 onmicrosoft.com。 不可能な場合は、移動 CsUser コマンドレットを使用します。
    >- 終了するアカウントを使用する PowerShell の csuser からの移動を使用する場合か、ことができます onmicrosoft.com、またはアカウントを使用できます、設置、Azure の AD に同期されるコマンドレットの HostedMigrationOverrideUrl パラメーターを指定するも、。. ホスト移行の上書きの URL の値は、次の URL の新種です。https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>上記の URL で、XX を次のように、2 つまたは 3 つのいずれかの文字に置き換えます。
    >   - ビジネス オンラインの PowerShell セッションでの Skype では、次のコマンドレットを実行します。<br>`Get-CsTenant|ft identity`
    >    - 結果の値は、次の形式になります。<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - 2 桁または 3 桁のコードでは、セクションでは、DC に含まれている XX = lyncXX001。 2 文字コードの場合は、(0 a) などの数値の後に数字があります。 3 文字コードである場合 (jp1) などの数字の後に 2 つの文字があります。 すべての場合、001 XX コードの直後に表示されます。


## <a name="voice-configuration-requirements"></a>音声の構成要件

設置型で、エンタープライズ ボイスのユーザーを構成する場合、オンラインに移動するか、または、テレフォニー機能に移行した可能性があります、音声の構成の更新を調整する必要があります。 使用可能なオプションかどうか、ユーザーが使用するチームまたは Skype ビジネス クライアントにそれらがオンラインになったらによって異なります。

- [Microsoft の計画を呼び出す](/microsoftteams/calling-plans-for-office-365)を使用する、ユーザーのテレフォニー プロバイダーを更新できます。 これは、ユーザーを使用して、チームや Skype ビジネス クライアント用かどうかのオプションです。
- 設置 PSTN は、プロバイダーを使用する続行することができます。
  - チームを使用する音声ユーザーは、[直接ルーティング](/microsoftteams/direct-routing-plan)を構成しなければなりません。 直接ルーティングをできるは、ユーザーを移動した後から施設内にオンラインにするだけです。
  - ビジネス ハイブリッド音声機能は、Skype の音声を使用するユーザー、Skype クライアントのビジネスのオンライン移動後を構成しなければなりません。

サポート ・ マトリックスと同様に、ハイブリッド環境でのテレフォニー オプションの詳細については、 [PSTN への接続を持つハイブリッド環境でユーザー アカウント](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)を参照してください。

## <a name="other-considerations"></a>その他の考慮事項

ポリシー (メッセージング、会議、および呼び出しの動作を制御する場合など) に設置し、オンライン環境は、独立しました。 環境内のすべてのポリシーを構成して、ユーザーへの割り当て、オンプレミス、クラウドに移行するからそのユーザーを移動する前にオンラインへ移行するとすぐに、適切な構成があるように考慮することがあります。

## <a name="see-also"></a>関連項目

[ユーザーをオンプレミスから Skype for Business Online に移動する](move-users-from-on-premises-to-skype-for-business-online.md)

[移動ユーザーがチームを設置](move-users-from-on-premises-to-teams.md)

[Meeting Migration Service (MMS) のセットアップ](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[ダイレクト ルーティングを計画する](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)