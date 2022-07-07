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
ms.openlocfilehash: 93aea5e294bbaf8d6988e5bfdeaafb1340345bdf
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682656"
---
# <a name="move-users-between-on-premises-and-cloud"></a>オンプレミスとクラウドの間でユーザーを移動する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Serverのオンプレミス展開では、Skype for Businessのユーザーが Teams を使用することもできますが、オンプレミスのSkype for Business Server展開を使用するように構成されている限り、そのようなユーザーはすべての Teams 機能を使用できるわけではありません。 これらのユーザーはオンプレミスで "ホーム" と言われ、特定の Teams 機能は使用できませんが、これらのユーザーはオンプレミスに所属しています。たとえば、次のようになります。
- 他の組織のユーザーとユーザーの Teams クライアントを介したフェデレーション通話とチャットは利用できません
- ユーザーの Teams クライアントを介して、Skype for Business クライアントを使用する組織内の他のユーザーとの相互運用。
- PSTN 通話機能 (ユーザーに電話システム ライセンスが割り当てられている場合)。

Teams の完全な機能を得るには、これらのユーザーをオンプレミスからクラウドSkype for Business移動する必要があります。その時点でユーザーは TeamsOnly になります。 ユーザーをオンプレミスからクラウドに移動する操作は、ユーザーの共存モードを TeamsOnly に設定します。 ユーザーがクラウドと TeamsOnly に移動されると、すべての着信チャットと通話が Teams クライアントに送信されます。 詳細については、「[Teams と Skype for Businessと移行の共存](/microsoftteams/coexistence-chat-calls-presence)と、Skype for Businessと[共に Teams を使用する組織の相互運用性に関するガイダンス](/microsoftteams/migration-interop-guidance-for-teams-with-skype)」を参照してください。

ユーザーをオンプレミスのSkype for Business Serverデプロイからクラウドに移行するには、[ハイブリッドSkype for Business構成する](/skypeforbusiness/hybrid/plan-hybrid-connectivity)必要があります。  ハイブリッドに対してデプロイが有効になったら、ユーザーをオンプレミス環境からクラウドに移動して、以下で説明するように TeamsOnly にすることができます。 必要に応じて、TeamsOnly ユーザーをオンプレミスの Skype for Bsuiness 展開に戻すこともできます。 



## <a name="prerequisites"></a>前提条件

TeamsOnly モードにユーザーを移動するための前提条件:

- 組織では、Azure AD Connect が適切に構成されており、 [Azure AD Connect の構成](configure-azure-ad-connect.md)に関する説明に従って、ユーザーに関連するすべての属性を同期している必要があります。
- Skype for Business ハイブリッドの構成に関するページで説明されているように、[ハイブリッドを構成Skype for Business](configure-federation-with-skype-for-business-online.md)必要があります。
- ユーザーには Teams と Skype for Business Online のライセンスが割り当てられている必要があります (プラン 2)。 Skype for Business オンライン の廃止後も、Skype for Business オンライン ライセンスは引き続き必要です。  さらに、
    - ユーザーがオンプレミスでダイヤルイン会議を有効にしている場合は、ユーザーをオンラインに移行する前に、Teams で電話会議ライセンスも割り当てられている必要があります。 クラウドへの移行後、ユーザーはクラウドの電話会議に対してプロビジョニングされます。 
    - ユーザーがオンプレミスのエンタープライズ VoIPに対して有効になっている場合は、ユーザーをオンラインに移行する前に、Teams で電話システム ライセンスが割り当てられている必要があります。 クラウドに移行すると、ユーザーはクラウド内の Phone System にプロビジョニングされます。 
  
2022 年 7 月 31 日の時点で、オンプレミスの展開とクラウドの間でユーザーを移動するには、次の最小バージョンの Skype for Business Server または Lync Server を使用している必要があります。

</br>
</br>

|オンプレミス製品|必要な最小バージョン|必要な最小ビルド|
|---|---|---|
|Skype for Business Server 2019| CU6 |7.0.2046.385|
|Skype for Business Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| 修正プログラム 7 を使用した CU10|5.0.8308.1182|
||||

</br>
</br>

## <a name="moving-users"></a>ユーザーの移動

ユーザーがオンプレミスからクラウドに移動された場合:

- Teams ユーザーはSkype for Businessユーザーとの相互運用性を有効にし、TeamsOnly の場合は他の組織とフェデレーションすることもできます。
- オンプレミスの連絡先は Teams に移動されます。
- 今後スケジュールされた既存の会議は、Teams 会議に変換されます。 会議の移行は非同期で行われ、ユーザーの移動から約 90 分後に開始されます。  会議の移行の状態を特定するには、[Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms) を使用します。 会議の前にアップロードされたコンテンツは移動されません。
- 電話システムが割り当てられているユーザーは、適切に構成されると PSTN 機能にアクセスできます。
 
ユーザーを Teams に移動するには、Move-CsUser コマンドレットまたはSkype for Business 管理 コントロール パネルを使用します。どちらもオンプレミス ツールです。 これらのツールでは、次の移動パスがサポートされています。

- [Skype for Business Server (オンプレミス) から Teams のみ。](move-users-from-on-premises-to-teams.md)
- [オンライン (Teams のみかどうか) からオンプレミスへ](move-users-from-the-cloud-to-on-premises.md)。


> [!NOTE] 
>  どのバージョンのSkype for Business Serverまたは Lync Server が使用されているかに関係なく、オンプレミスから Teams のみに直接移動する動作が自動的に行われるようになりました。 ユーザーをオンプレミスから TeamsOnly に直接移動するために、Move-CsUserで -MoveToTeams 切り替えを指定する必要はなくなりました。 以前は、このスイッチが指定されていない場合、ユーザーはオンプレミスSkype for Business Serverホームから Skype for Business Online に移行し、モードは変更されませんでした。 Move-CsUser を使用してユーザーをオンプレミスからクラウドに移動すると、ユーザーには TeamsOnly モードが自動的に割り当てられ、スイッチが実際に指定されたかどうかに関係なく、スイッチが指定されたかのように `-MoveToTeams` 、オンプレミスからの会議が自動的に Teams 会議に変換されます。 


## <a name="required-administrative-credentials"></a>必要な管理者の資格情報

オンプレミスとクラウドの間でユーザーを移動するには、オンプレミスのSkype for Business Server環境と Teams 組織の両方で十分な特権を持つアカウントを使用する必要があります。 必要なすべての特権を持つ 1 つのアカウントを使用することも、2 つのアカウントを使用することもできます。 2 つのアカウントを使用する場合は、オンプレミスの資格情報を使用してオンプレミス のツールにアクセスし、それらのツールで Teams 管理アカウントの追加の資格情報を指定します。  

- オンプレミス環境では、移動を実行するユーザーには、Skype for Business Serverに CSServerAdministrator、CsUserAdministrator、RTCUniversalUserAdmins ロールが必要です。
- Teams では、移動を実行するユーザーは、次のロールの少なくとも 1 つのメンバーである必要があります。
  - グローバル管理者ロール
  - Teams 管理者ロール
  - Skype for Business管理者ロール。  

    > [!Important]
    > - Skype for Business 管理 コントロール パネルを使用している場合は、前述のように、適切なロールを持つ Microsoft 365 アカウントの資格情報を指定するように求められます。 .onmicrosoft.com で終わるアカウントを指定する必要があります。 それが不可能な場合は、Move-CsUser コマンドレットを使用します。
    >- PowerShell でMove-CsUserを使用している場合は、.onmicrosoft.com で終わるアカウントを使用するか、コマンドレットで HostedMigrationOverrideUrl パラメーターも指定すれば、Azure AD に同期されるオンプレミス アカウントを使用できます。 ホストされた移行オーバーライド URL の値は、次の URL のバリアントです。 https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>上記の URL で、XX を次のように決定された 2 文字または 3 文字に置き換えます。
    >   - Teams PowerShell セッションで、次のコマンドレットを実行します。<br>`Get-CsTenant | ft ServiceInstance`
    >   - 結果の値は次の形式になります。<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - 2 文字または 3 文字のコードは、セクション YYYY-XX-ZZ に含まれる XX です。 2 文字のコードの場合は、数字の後に数字 (4A など) が続きます。 3 文字のコードの場合は、2 文字の後に数字 (JP1 など) が続きます。 たとえば、NOAM-4A-S7 です。


## <a name="voice-configuration-requirements"></a>音声構成の要件

ユーザーがオンプレミスでエンタープライズ音声用に構成されている場合は、オンラインに移行するときに音声構成の更新を調整する必要があります。 または、テレフォニー機能を使用せずに移行することもできます。 
- [Microsoft 通話プラン](/microsoftteams/calling-plans-for-office-365)を使用するように、ユーザーのテレフォニー プロバイダーを更新できます。 これは、ユーザーが Teams またはSkype for Business クライアントを使用するかどうかのオプションです。
- オンプレミスの PSTN プロバイダーを引き続き使用できます。
  - Teams を使用する音声ユーザーは、 [ダイレクト ルーティング](/microsoftteams/direct-routing-plan)用に構成する必要があります。 直接ルーティングは、ユーザーがオンプレミスからオンラインに移動した後にのみ使用できます。

サポートアビリティ マトリックスを含むハイブリッド環境のテレフォニー オプションの詳細については、「 [PSTN 接続を使用するハイブリッド環境のユーザー アカウント](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)」を参照してください。

## <a name="other-considerations"></a>その他の考慮事項

オンプレミスとオンラインの環境のポリシー (メッセージング、会議、通話の動作を制御するためのポリシーなど) は相互に独立しています。 環境内のポリシーを構成し、そのユーザーをオンプレミスからクラウドに移動する前にユーザーに割り当てることを検討すると、オンラインに移行するとすぐに適切な構成が可能になります。

## <a name="see-also"></a>関連項目

[オンプレミスから Teams にユーザーを移動する](move-users-from-on-premises-to-teams.md)

[Meeting Migration Service (MMS) のセットアップ](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[ダイレクト ルーティングを計画する](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
