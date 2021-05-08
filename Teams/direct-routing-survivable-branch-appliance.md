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
description: 構成、必要なコア デプロイの決定、音声ルーティングに関する考慮事項など、ダイレクト ルーティングの詳細について説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: edf2c2a97bec2b167f1218d983d3c9f7fa4bd667
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096427"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>ダイレクト ルーティングのための存続可能ブランチ アプライアンス (SBA)


場合によっては、ダイレクト ルーティングを使用してシステムに接続する顧客サイトMicrosoft 電話インターネットが停止することがあります。

ブランチと呼ばれるお客様のサイトが、直接ルーティングを介して一時的に Microsoft クラウドに接続できないとします。 ただし、ブランチ内のイントラネットは引き続き完全に機能し、ユーザーは PSTN 接続を提供するセッション ボーダー コントローラー (SBC) に接続できます。

この記事では、存続可能ブランチ アプライアンス (SBA) を使用して、障害が発生した場合に Microsoft 電話 System が引き続き公衆交換電話網 (PSTN) 通話を発信および受信できる方法について説明します。

## <a name="prerequisites"></a>前提条件

SBA は、Microsoft が SBC ベンダーに提供する再配布可能なコードです。その後、コードをファームウェアに埋め込むか、別の VM またはハードウェアで SBA を実行するために個別に配布します。 

組み込みの存続可能ブランチ アプライアンスを使用して最新のセッション ボーダー コントローラー ファームウェアを取得するには、SBC ベンダーにお問い合わせください。 さらに、次の情報が必要です。

- ブランチ サイト内の Microsoft Teams クライアントが SBC と直接流れるメディアを確保するには、メディア バイパス用に SBC を構成する必要があります。 

- SBA VM OS で TLS1.2 を有効にする必要があります。

## <a name="supported-teams-clients"></a>サポートされているTeams クライアント

SBA 機能は、次のクライアントでMicrosoft Teamsされます。 

- Microsoft Teams Windows デスクトップ 

- Microsoft Teams macOS デスクトップ 

## <a name="how-it-works"></a>メカニズム

インターネットの停止中、クライアントTeams自動的に SBA に切り替える必要があります。また、継続的な呼び出しは中断することなく続行する必要があります。 ユーザーからのアクションは必要ありません。 Teams クライアントがインターネットが稼働し、すべての発信呼び出しが完了するとすぐに、クライアントは通常の操作モードに戻り、他の Teams サービスに接続します。 SBA は収集された通話データ レコードをクラウドにアップロードし、通話履歴が更新され、テナント管理者がこの情報を確認できます。 

クライアントがMicrosoft Teamsモードの場合、次の呼び出し関連機能を使用できます。 

- ローカル SBA/SBC 経由で PSTN 通話を行い、SBC を通過するメディアを使用します。

- SBC を通過するメディアを使用してローカル SBA/SBC 経由で PSTN 通話を受信する。 

- PSTN 通話の保留と再開。

## <a name="configuration"></a>構成

SBA 機能を機能するには、Teams クライアントは、各ブランチ サイトで使用できる SBA と、そのサイト内のユーザーに割り当てられている SBA を知っている必要があります。 構成手順は次のとおりです。

1. SBA を作成します。
2. ブランチの存続Teamsポリシーを作成します。
3. ポリシーをユーザーに割り当てる。
4. SBA のアプリケーションをアプリケーションに登録Azure Active Directory。

すべての構成は、オンライン PowerShell コマンドレットSkype for Business使用して行われます。 (Teams センターでは、直接ルーティング SBA 機能はまだサポートされていません)。 

(SBC ベンダーのドキュメントへのリンクを含む SBC の構成については、この記事の最後にある「セッション ボーダー コントローラーの構成」を参照してください)。

### <a name="create-the-sbas"></a>SBA を作成する

SA を作成するには、次のコマンドレットNew-CsTeamsSurvivableBranchApplianceします。 このコマンドレットには、次のパラメーターがあります。

| パラメーター| 説明 |
| :------------|:-------|
| Identity  | SBA の ID  |
| Fqdn | SBA の FQDN |
| サイト | SBA がある TenantNetworkSite |
| 説明 | 自由形式のテキスト |
|||

次に例を示します。

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>ブランチの存続Teamsポリシーを作成する 

ポリシーを作成するには、次のコマンドレットNew-CsTeamsSurvivableBranchAppliancePolicyします。 このコマンドレットには、次のパラメーターがあります。 ポリシーには、1 つ以上の SBA を含め得る点に注意してください。

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

次のコマンドレットを使用して、ポリシーの SBA を追加Set-CsTeamsSurvivableBranchAppliancePolicyできます。 次に例を示します。 

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

ユーザーからポリシーを削除するには、次の例に$Nullポリシーを付与します。

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>SBA のアプリケーションをアプリケーションに登録Azure Active Directory

テナント内で使用される異なる SBA が Microsoft 365 から必要なデータを読み取るのを許可するには、SBA のアプリケーションを Azure Active Directory に登録する必要があります。 

アプリケーションの登録の詳細については、次を参照してください。

- [新しいビジネス アプリを開発Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [アプリケーションを Microsoft ID プラットフォーム に登録します](/azure/active-directory/develop/quickstart-register-app)。  

登録する必要があるアプリケーションは、テナント内のすべての SBA で使用するために 1 つのみです。 

SBA 登録には、登録によって作成された次の値が必要です。 

- アプリケーション (クライアント) ID 
- クライアント シークレット 

SBA アプリケーションの場合は、次の注意が必要です。 

- 名前は、ユーザーが決定した名前にできます。  
- サポートされているアカウントの種類 = この組織のディレクトリ内のアカウントのみ。 
- Web リダイレクト URI = https://login.microsoftonline.com/common/oauth2/nativeclient 。
- 暗黙的な付与トークン = アクセス トークンと ID トークン。 
- API のアクセス許可 = SkypeテナントTeamsアクセス -> アプリケーションのアクセス許可 -> application_access_custom_sba_appliance。
- クライアント シークレット: 任意の説明と有効期限を使用できます。 
- クライアント シークレットは、作成後すぐにコピーしてください。 
- アプリケーション (クライアント) ID が [概要] タブに表示されます。

その後、次の手順に従います。

1. アプリケーションを登録します。
2. 暗黙的な付与トークンを設定します。
3. API のアクセス許可を設定します。
4. クライアント シークレットを作成します。


## <a name="session-border-controller-configuration"></a>セッション ボーダー コントローラーの構成 

組み込みの Survivable Branch Appliance を使用してセッション ボーダー コントローラーを構成する方法の詳細なガイダンスについては、SBC ベンダーが提供するドキュメントを参照してください。 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [リボン](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>問題の報告

SBC ベンダーのサポート組織に問題を報告します。 問題を報告する場合は、存続可能ブランチ アプライアンスが構成されていることを示します。

## <a name="known-issues"></a>既知の問題

- 新しい存続可能ブランチ アプライアンスを追加する場合は、存続可能ブランチ アプライアンス ポリシーで使用できるまで時間がかかる場合があります。

- ユーザーに存続可能ブランチ アプライアンス ポリシーを割り当てると、Get-CsOnlineUser の出力に SBA が表示されるまで時間がかかる場合があります。 

- Azure ADに対する逆引き番号参照は実行されません。 

- SBA では、通話の転送設定はサポートされていません。 

- 動的緊急通話 (E911) 用に構成された緊急電話番号への緊急通話はサポートされていません。

- このコマンドの出力Get-CsOnlineUser TeamsBranchSurvivabilityPolicy が表示されます。