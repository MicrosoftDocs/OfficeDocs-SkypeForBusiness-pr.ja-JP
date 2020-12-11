---
title: ダイレクト ルーティング SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 構成、必要な主要な展開決定、音声ルーティングに関する考慮事項など、ダイレクト ルーティングの詳細について説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3204bc58b083f62feca3f878d2189558b69af6bd
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620732"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a>ダイレクト ルーティング用の分岐電気機器 (SBA) - パブリック プレビュー


> [!NOTE]
> これはパブリック プレビュー リリースです。

場合によっては、Microsoft Phone System に接続するためにダイレクト ルーティングを使用しているお客様のサイトで、インターネットが停止することがあります。

ブランチと呼ばれるお客様のサイトが、直接ルーティングを通じて Microsoft クラウドに一時的に接続できないことを想定します。 ただし、ブランチ内のイントラネットは引き続き完全に機能し、ユーザーは PSTN 接続を提供しているセッション ボーダー コントローラー (SBC) に接続できます。

この記事では、停止した場合に Microsoft Phone System が公衆交換電話網 (PSTN) 通話を発信および受信し続け、発信および受信を行う場合に、SBA (不可不可) の分岐電気機器 (SBA) を使用する方法について説明します。

## <a name="prerequisites"></a>前提条件

SBA は、Microsoft が SBC ベンダーに提供するコードを配布可能なコードで、その後、ファームウェアにコードを埋め込むか、別の VM またはハードウェアで SBA を実行するために個別に配布します。 

埋め込まれたEdvedable Branch Controller を使用して最新のセッション ボーダー コントローラーファームウェアを取得するには、SBC ベンダーにお問い合わせください。 さらに、次の情報が必要です。

- ブランチ サイトの Microsoft Teams クライアントが SBC で直接流れるメディアを使用するには、メディア バイパス用に SBC を構成する必要があります。 

- SBA VM OS で TLS1.2 を有効にする必要があります。

## <a name="supported-teams-clients"></a>サポートされている Teams クライアント

SBA 機能は、次の Microsoft Teams クライアントでサポートされています。 

- Microsoft Teams Windows デスクトップ 

- Microsoft Teams macOS デスクトップ 

## <a name="how-it-works"></a>メカニズム

インターネットの停止中、Teams クライアントは自動的に SBA に切り替える必要があります。継続的な通話は中断することなく継続する必要があります。 ユーザーからの操作は必要ありません。 Teams クライアントがインターネットが正常に動作し、すべての発信通話が完了すると、クライアントは通常の操作モードに戻り、他の Teams サービスに接続します。 SBA は収集された通話データ レコードをクラウドにアップロードし、この情報をテナント管理者が確認するために通話履歴が更新されます。 

Microsoft Teams クライアントがオフライン モードの場合、次の呼び出し関連機能を使用できます。 

- SBC を経由するメディアを使用して、ローカル SBA/SBC を介して PSTN 通話を行う。

- SBC を経由するメディアを使用して、ローカル SBA/SBC 経由で PSTN 通話を受信する。 

- PSTN 通話の保留と再開。

## <a name="configuration"></a>構成

SBA 機能を機能するには、Teams クライアントは、各ブランチ サイトで使用できる SBA と、そのサイト内のユーザーに割り当てられている SBA を知る必要があります。 構成手順は次のとおりです。

1. SA を作成します。
2. Teams ブランチのアクセス可能性ポリシーを作成します。
3. ユーザーにポリシーを割り当てる。
4. Azure Active Directory で SBA のアプリケーションを登録します。

すべての構成は、Skype for Business Online PowerShell コマンドレットを使用して行います。 (Teams 管理センターは、ダイレクト ルーティング SBA 機能をまだサポートしていません)。 

(SBC ベンダーのドキュメントへのリンクを含む SBC の構成については、この記事の最後にあるセッション ボーダー コントローラーの構成を参照してください)。

### <a name="create-the-sbas"></a>SA を作成する

SA を作成するには、次のコマンドレットNew-CsTeamsSurvivableBranchApplianceします。 このコマンドレットには、次のパラメーターがあります。

| パラメーター| 説明 |
| :------------|:-------|
| Identity  | SBA の ID  |
| Fqdn | SBA の FQDN |
| サイト | SBA が保存されている TenantNetworkSite |
| 説明 | 無料の書式テキスト |
|||

次に例を示します。

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Teams ブランチの分けやすさに関するポリシーを作成する 

ポリシーを作成するには、次のコマンドレットNew-CsTeamsSurvivableBranchAppliancePolicyします。 このコマンドレットには、次のパラメーターがあります。 ポリシーには、1 つ以上の SA を含めできます。

| パラメーター| 説明 |
| :------------|:-------|
| Identity | ポリシーの ID |
| BranchApplianceFqdns  | サイト内の SBA の FQDN |
||

次に例を示します。

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

このコマンドレットを使用して、ポリシーの SA を追加またはSet-CsTeamsSurvivableBranchAppliancePolicyできます。 次に例を示します。 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>ユーザーにポリシーを割り当てる

ポリシーを個々のユーザーに割り当てるには、次のコマンドレットGrant-CsTeamsSurvivableBranchAppliancePolicyします。 このコマンドレットには、次のパラメーターがあります。

| パラメーター| 説明 |
| :------------|:-------|
| Identity | ユーザーの ID |
| PolicyName | ポリシーの ID |
||

次に例を示します。

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

次の例に示すように、ポリシー$Nullユーザーからポリシーを削除できます。

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Azure Active Directory で SBA のアプリケーションを登録する

テナント内で使用される異なる SBA が Microsoft 365 から必要なデータを読み取り込むには、Azure Active Directory で SBA 用のアプリケーションを登録する必要があります。 

アプリケーションの登録の詳細については、次を参照してください。

- [Azure Active Directory 用の業務用アプリを開発する](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Microsoft ID プラットフォームでアプリケーションを登録します](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。  

テナント内のすべての SA で使用するために 1 つのアプリケーションのみを登録する必要があります。 

SBA 登録には、登録によって作成された次の値が必要です。 

- アプリケーション (クライアント) ID 
- クライアント シークレット 

SBA アプリケーションの場合は、次の注意が必要です。 

- 名前は、ユーザーが決めたものにできます。  
- サポートされているアカウントの種類 = この組織のディレクトリのアカウントのみ。 
- Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient .
- 暗黙的な付与トークン = Access トークンと ID トークン。 
- API のアクセス許可 = Skype と Teams テナント管理者アクセス -> アプリケーションのアクセス許可 -> application_access_custom_sba_appliance。
- クライアント シークレット: 任意の説明と有効期限を使用できます。 
- クライアント シークレットは、作成後すぐにコピーしてください。 
- アプリケーション (クライアント) ID が [概要] タブに表示されます。

次の手順に従います。

1. アプリケーションを登録します。
2. 暗黙的な付与トークンを設定します。
3. API のアクセス許可を設定します。
4. クライアント シークレットを作成します。


## <a name="session-border-controller-configuration"></a>セッション ボーダー コントローラーの構成 

埋め込まれたEdEdしおり分岐電気機器を使用してセッション ボーダー コントローラーを構成する方法の詳細なガイダンスについては、SBC ベンダーが提供するドキュメントを参照してください。 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [リボン](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>問題の報告

問題がある場合は、SBC ベンダーのサポート組織に報告してください。 問題を報告する場合は、変更可能なブランチ 電気機器が構成されていることを示します。

## <a name="known-issues"></a>既知の問題

- 新しい変更可能な分岐機器を追加する場合、そのブランチ の分岐の分岐の利用に関するポリシーでそれらを使用するには、時間がかかる場合があります。

- ユーザーに変更可能な分岐ポリシーを割り当てると、SBA が Get-CsOnlineUser の出力に表示されるまで時間がかかる場合があります。 

- Azure の連絡先に対する逆ADの参照は実行されません。 

- SBA では、通話の転送設定はサポートされていません。 

- 動的緊急通話 (E911) 用に構成された緊急電話番号への緊急通話の発信はサポートされていません。

- この値の出力Get-CsOnlineUser TeamsBranchSurvivabilityPolicy が表示されます。
