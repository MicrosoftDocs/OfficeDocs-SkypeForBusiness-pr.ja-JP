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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '概要: ハイブリッドが有効になっているSkype for Business Serverのオンプレミスデプロイでは、オンプレミス環境とクラウドの間でユーザーを移動できます。'
ms.openlocfilehash: 15e237fdf54854a86216bc3890ae26209449c146
ms.sourcegitcommit: d847256fca80e4e8954f767863c880dc8472ca04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2022
ms.locfileid: "65304009"
---
# <a name="move-users-between-on-premises-and-cloud"></a>オンプレミスとクラウドの間でユーザーを移動する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

ハイブリッドが有効になっているSkype for Business Serverのオンプレミス展開では、オンプレミス環境とTeamsの間でユーザーを移動できます。 ユーザーのいる場所、つまり、オンプレミスまたはクラウドは、そのユーザーの Skype for Business ホームとして認識されます。

- オンプレミスに所属するユーザーは、オンプレミスのSkype for Business サーバーと対話します。
- オンラインに所属しているユーザーは、Teams サービスとやり取りできます。

*Teamsユーザーは、Skype for Businessを使用するかどうかに関係なく、本質的にSkype for Businessホームを持っています。* Teamsも使用しているオンプレミス Skype for Business ユーザーがいる場合 (並べて)、それらのユーザーはオンプレミスに所属します。 オンプレミスにSkype for Businessを持つTeamsユーザーは、Teams クライアントのSkype for Business ユーザーと相互運用できず、フェデレーション組織内のユーザーとTeamsから通信することもできません。 このような機能は、ユーザーがオンプレミスからオンラインにSkype for Businessし、TeamsOnly を作成した後にのみ完全に利用できます。 ユーザーを TeamsOnly モードに移行することをお勧めします。これにより、すべての受信チャットと通話のルーティングがTeams クライアントに確実に移行されます。 詳細については、[TeamsとSkype for Businessを](/microsoftteams/coexistence-chat-calls-presence)[組み合わせて使用する組織のTeams Skype for Businessと移行および相互運用性に関するガイダンスとの共存に関するガイダンス](/microsoftteams/migration-interop-guidance-for-teams-with-skype)を参照してください。

## <a name="prerequisites"></a>前提条件

TeamsOnly モードにユーザーを移動するための前提条件:

- 組織は、Azure AD Connect適切に構成され、[Azure AD Connectの構成](configure-azure-ad-connect.md)に関する説明に従って、ユーザーに関連するすべての属性を同期している必要があります。
- Skype for Business ハイブリッドの構成に関するページで説明されているように、[ハイブリッドを構成Skype for Business](configure-federation-with-skype-for-business-online.md)必要があります。
- ユーザーには、Teams および Skype for Business Online のライセンスが割り当てられている必要があります (プラン 2)。 Skype for Business Online の廃止後も、Skype for Business Online ライセンスは引き続き必要です。  さらに、
    - ユーザーがオンプレミスでダイヤルイン会議を有効にしている場合は、ユーザーをオンラインに移行する前に、Teamsで電話会議 ライセンスも割り当てられている必要があります。 クラウドへの移行後、ユーザーはクラウドの電話会議に対してプロビジョニングされます。 
    - ユーザーがオンプレミスでエンタープライズ VoIPを有効にしている場合は、ユーザーをオンラインに移行する前に、Teamsで電話システム ライセンスが割り当てられている必要があります。 クラウドに移行すると、ユーザーはクラウド内の電話システムにプロビジョニングされます。 


## <a name="moving-users"></a>ユーザーの移動

ユーザーがオンプレミスからクラウドに移動された場合:

- TeamsユーザーはSkype for Businessユーザーとの相互運用性を有効にし、TeamsOnly の場合は他の組織とフェデレーションすることもできます。

- オンプレミスの連絡先は、Teamsに移動されます。

- 今後スケジュールされた既存の会議は、Teams会議に変換されます。 会議の移行は非同期で行われ、ユーザーの移動から約 90 分後に開始されます。  会議の移行の状態を特定するには、[Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms) を使用します。 会議の前にアップロードされたコンテンツは移動されません。

ユーザーをTeamsに移動するには、Move-CsUser コマンドレットまたはSkype for Business管理者コントロール パネルのいずれかを使用します。どちらもオンプレミス ツールです。 これらのツールでは、次の移動パスがサポートされています。

- [Skype for Business Server (オンプレミス) から直接Teamsのみ](move-users-from-on-premises-to-teams.md)。  オンプレミスから Teams のみに直接移動する動作は、使用されているSkype for Business Serverまたは Lync Server のバージョンに関係なく、自動的に行われます。 この動作を取得するためにスイッチを `-MoveToTeams` 指定する必要はなくなりました。  
- [オンライン (Teamsのみかどうか) からオンプレミスに。](move-users-from-the-cloud-to-on-premises.md)

> [!NOTE] 
> ユーザーをオンプレミスから TeamsOnly に直接移動するために、Move-CsUserで -MoveToTeams スイッチを指定する必要はなくなりました。 以前は、このスイッチが指定されていない場合、ユーザーはオンプレミスSkype for Business Serverホームから Skype for Business Online に移行し、モードは変更されませんでした。 Move-CsUser を使用してユーザーをオンプレミスからクラウドに移動すると、ユーザーには TeamsOnly モードが自動的に割り当てられ、スイッチが実際に指定されたかどうかに関係なく、スイッチが指定された場合`-MoveToTeams`と同様に、オンプレミスからの会議が自動的にTeams会議に変換されます。 
> 

## <a name="required-administrative-credentials"></a>必要な管理者の資格情報

オンプレミスとクラウドの間でユーザーを移動するには、オンプレミスのSkype for Business Server環境とTeams組織の両方で十分な特権を持つアカウントを使用する必要があります。 必要なすべての特権を持つ 1 つのアカウントを使用することも、2 つのアカウントを使用することもできます。 2 つのアカウントを使用する場合は、オンプレミスの資格情報を使用してオンプレミス ツールにアクセスし、それらのツールでTeams管理アカウントの追加の資格情報を指定します。  

- オンプレミス環境では、移動を実行するユーザーには、Skype for Business Serverに CSServerAdministrator、CsUserAdministrator、RTCUniversalUserAdmins ロールが必要です。
- Teamsでは、移動を実行するユーザーは、次のロールの少なくとも 1 つのメンバーである必要があります。
  - グローバル管理者ロール
  - Teams管理者ロール
  - Skype for Business管理者ロール。  

    > [!Important]
    > - Skype for Business管理者コントロール パネルを使用している場合は、前述のように、適切なロールを持つMicrosoft 365 アカウントの資格情報を入力するように求められます。 .onmicrosoft.com で終わるアカウントを指定する必要があります。 それが不可能な場合は、Move-CsUser コマンドレットを使用します。
    >- PowerShell でMove-CsUserを使用している場合は、.onmicrosoft.com で終わるアカウントを使用するか、コマンドレットで HostedMigrationOverrideUrl パラメーターも指定すれば、Azure AD に同期されるオンプレミス アカウントを使用できます。 ホストされた移行オーバーライド URL の値は、次の URL のバリアントです。 https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>上記の URL で、XX を次のように決定された 2 文字または 3 文字に置き換えます。
    >   - Teams PowerShell セッションで、次のコマンドレットを実行します。<br>`Get-CsTenant | ft ServiceInstance`
    >   - 結果の値は次の形式になります。<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - 2 文字または 3 文字のコードは、セクション YYYY-XX-ZZ に含まれる XX です。 2 文字のコードの場合は、数字の後に数字 (4A など) が続きます。 3 文字のコードの場合は、2 文字の後に数字 (JP1 など) が続きます。 たとえば、NOAM-4A-S7 です。


## <a name="voice-configuration-requirements"></a>音声構成の要件

ユーザーがオンプレミスでエンタープライズ音声用に構成されている場合は、オンラインに移行するときに音声構成の更新を調整する必要があります。 または、テレフォニー機能を使用せずに移行することもできます。 使用可能なオプションは、ユーザーがオンラインになったら、ユーザーがTeamsまたはSkype for Businessクライアントを使用するかどうかによって異なります。

- [Microsoft 通話プラン](/microsoftteams/calling-plans-for-office-365)を使用するように、ユーザーのテレフォニー プロバイダーを更新できます。 これは、ユーザーがTeamsまたはSkype for Businessクライアントを使用するかどうかのオプションです。
- オンプレミスの PSTN プロバイダーを引き続き使用できます。
  - Teamsを使用する音声ユーザーは[、ダイレクト ルーティング](/microsoftteams/direct-routing-plan)用に構成する必要があります。 直接ルーティングは、ユーザーがオンプレミスからオンラインに移動した後にのみ使用できます。
  - オンラインに移行した後にSkype for Business クライアントを使用する音声ユーザーは、音声機能Skype for Business Hybrid構成する必要があります。

サポートアビリティ マトリックスを含むハイブリッド環境のテレフォニー オプションの詳細については、「 [PSTN 接続を使用するハイブリッド環境のユーザー アカウント](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)」を参照してください。

## <a name="other-considerations"></a>その他の考慮事項

オンプレミスとオンラインの環境のポリシー (メッセージング、会議、通話の動作を制御するためのポリシーなど) は相互に独立しています。 環境内のポリシーを構成し、そのユーザーをオンプレミスからクラウドに移動する前にユーザーに割り当てることを検討すると、オンラインに移行するとすぐに適切な構成が可能になります。

## <a name="see-also"></a>関連項目

[オンプレミスから Teams にユーザーを移動する](move-users-from-on-premises-to-teams.md)

[Meeting Migration Service (MMS) のセットアップ](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[ダイレクト ルーティングを計画する](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
