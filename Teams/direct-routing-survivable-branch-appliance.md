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
description: 構成、必要なコアデプロイの決定、音声ルーティングに関する考慮事項など、ダイレクト ルーティングの詳細について説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b378ee327f2ba284a348ff7458c617fed71541c6
ms.sourcegitcommit: 12044ab8b2e79a7b23bf9a0918ae070925d21f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2021
ms.locfileid: "61401891"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>ダイレクト ルーティング用の存続可能ブランチ アプライアンス (SBA)


場合によっては、ダイレクト ルーティングを使用して Microsoft 電話 システムに接続する顧客サイトでインターネットが停止することがあります。

お客様のサイト (ブランチと呼ばれる) が、直接ルーティングを介して Microsoft クラウドに一時的に接続できないとします。 ただし、ブランチ内のイントラネットはまだ完全に機能しており、ユーザーは PSTN 接続を提供しているセッション ボーダー コントローラー (SBC) に接続できます。

この記事では、存続可能ブランチ アプライアンス (SBA) を使用して、Microsoft 電話 システムが停止した場合に公衆交換電話網 (PSTN) の呼び出しを引き続き発信および受信できるようにする方法について説明します。

## <a name="prerequisites"></a>前提条件

SBA は、Microsoft から SBC ベンダーに提供される配布可能なコードであり、そのコードをファームウェアに埋め込むか、SBA を個別の VM またはハードウェアで実行するように個別に配布します。 

組み込みの存続可能ブランチ アプライアンスを使用して最新のセッション ボーダー コントローラー ファームウェアを取得するには、SBC ベンダーにお問い合わせください。 さらに、次のものが必要です。

- SBC を Media Bypass 用に構成して、ブランチ サイト内のMicrosoft Teams クライアントが SBC で直接メディアを流れるようにする必要があります。 

- SBA VM OS で TLS1.2 を有効にする必要があります。
- ポート 3443、4444、および 8443 は、Microsoft SBA Server によってTeams クライアントと通信するために使用され、ファイアウォールで許可される必要があります。 
- ポート 5061 (または SBC で構成されたもの) は、Microsoft SBA Server が SBC と通信するために使用し、ファイアウォールで許可する必要があります。 
- UDP ポート 123 は、Microsoft SBA Server が NTP サーバーと通信するために使用するため、ファイアウォールで許可する必要があります。
- ポート 443 は、Microsoft SBA Server によってMicrosoft 365と通信するために使用され、ファイアウォールで許可する必要があります。
- パブリック クラウドの Azure IP 範囲とサービス タグは、次のガイドラインに従って定義する必要があります。 https://www.microsoft.com/download/details.aspx?id=56519

## <a name="supported-teams-clients"></a>サポートされているTeams クライアント

SBA 機能は、次のMicrosoft Teams クライアントでサポートされています。 

- デスクトップMicrosoft Teams Windows 

- macOS デスクトップをMicrosoft Teamsする
- モバイル向けのTeams 
- Teams Phone

## <a name="how-it-works"></a>メカニズム

インターネットの停止中、Teams クライアントは自動的に SBA に切り替える必要があり、継続的な呼び出しは中断なしで続行する必要があります。 ユーザーからの操作は必要ありません。 Teams クライアントがインターネットが起動し、発信呼び出しが完了したことを検出するとすぐに、クライアントは通常の操作モードに戻り、他のTeams サービスに接続します。 SBA は収集された通話データ レコードをクラウドにアップロードし、この情報がテナント管理者が確認できるように通話履歴が更新されます。 

Microsoft Teams クライアントがオフライン モードの場合、次の呼び出しに関連する機能を使用できます。 

- ローカル SBA/SBC 経由で PSTN 通話を行い、SBC を通過するメディアを使用します。

- ローカル SBA/SBC 経由で PSTN 通話を受信し、メディアが SBC を流れる。 

- PSTN 通話の保留と再開。

## <a name="configuration"></a>構成

SBA 機能を機能させるには、Teams クライアントは、各ブランチ サイトで使用可能な SBA と、そのサイト内のユーザーに割り当てられている SBA を把握する必要があります。 構成手順は次のとおりです。

1. SBA を作成します。
2. Teams ブランチの存続可能性ポリシーを作成します。
3. ポリシーをユーザーに割り当てます。
4. SBA のアプリケーションをAzure Active Directoryに登録します。

すべての構成は、Skype for Business Online PowerShell コマンドレットを使用して行われます。 (Teams管理センターでは、ダイレクト ルーティング SBA 機能はまだサポートされていません)。 

(SBC ベンダーのドキュメントへのリンクを含む SBC の構成については、この記事の最後にあるセッション ボーダー コントローラーの構成を参照してください)。

### <a name="create-the-sbas"></a>SBA を作成する

SBA を作成するには、New-CsTeamsSurvivableBranchAppliance コマンドレットを使用します。 このコマンドレットには、次のパラメーターがあります。

| パラメーター| 説明 |
| :------------|:-------|
| Identity  | SBA の ID  |
| Fqdn | SBA の FQDN |
| サイト | SBA が配置されている TenantNetworkSite |
| 説明 | 自由書式のテキスト |
|||

次に例を示します。

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Teams ブランチの存続可能性ポリシーを作成する 

ポリシーを作成するには、New-CsTeamsSurvivableBranchAppliancePolicy コマンドレットを使用します。 このコマンドレットには、次のパラメーターがあります。 ポリシーには 1 つ以上の SBA を含めることができます。

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

Set-CsTeamsSurvivableBranchAppliancePolicy コマンドレットを使用して、ポリシーに対して SBA を追加または削除できます。 次に例を示します。 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>ユーザーにポリシーを割り当てる

個々のユーザーにポリシーを割り当てるには、Grant-CsTeamsSurvivableBranchAppliancePolicy コマンドレットを使用します。 このコマンドレットには、次のパラメーターがあります。

| パラメーター| 説明 |
| :------------|:-------|
| Identity | ユーザーの ID |
| PolicyName | ポリシーの ID |
||

次に例を示します。

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

次の例に示すように、$Null ポリシーを付与することで、ユーザーからポリシーを削除できます。

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>SBA のアプリケーションをAzure Active Directoryに登録する

テナント内で使用されているさまざまな SBA がMicrosoft 365から必要なデータを読み取ることができるようにするには、SBA のアプリケーションをAzure Active Directoryに登録する必要があります。 

アプリケーションの登録の詳細については、次を参照してください。

- [Azure Active Directory向けの基幹業務アプリを開発する](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [アプリケーションをMicrosoft ID プラットフォームに登録します](/azure/active-directory/develop/quickstart-register-app)。  

テナント内のすべての SBA で使用するアプリケーションを 1 つだけ登録する必要があります。 

SBA 登録では、登録によって作成された次の値が必要です。 

- アプリケーション (クライアント) ID 
- クライアント シークレット 

SBA アプリケーションの場合は、次の点に注意してください。 

- 名前は、任意の名前にすることができます。  
- サポートされているアカウントの種類 = この組織のディレクトリ内のアカウントのみ。 
- Web リダイレクト Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.
- 暗黙的な付与トークン = アクセス トークンと ID トークン。 
- API のアクセス許可 = Skypeとテナント管理者アクセスのTeams -> アプリケーションのアクセス許可 -> application_access_custom_sba_appliance。
- クライアント シークレット: 任意の説明と有効期限を使用できます。 
- クライアント シークレットを作成した直後に必ずコピーしてください。 
- [概要] タブにアプリケーション (クライアント) ID が表示されます。

次に、次の手順に従います。

1. アプリケーションを登録します。
2. 暗黙的な付与トークンを設定します。
3. API アクセス許可を設定します。
4. クライアント シークレットを作成します。


## <a name="session-border-controller-configuration"></a>セッション ボーダー コントローラーの構成 

組み込みの存続可能ブランチ アプライアンスを使用してセッション ボーダー コントローラーを構成する方法の詳細なガイダンスについては、SBC ベンダーが提供するドキュメントを参照してください。 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [リボン](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>レポートの問題

SBC ベンダーのサポート組織に問題を報告します。 問題を報告するときは、存続可能ブランチ アプライアンスが構成されていることを示します。

## <a name="known-issues"></a>既知の問題

- 新しい存続可能ブランチ アプライアンスを追加すると、存続可能ブランチ アプライアンス ポリシーで使用できるようになるまでに時間がかかる場合があります。

- 存続可能ブランチ アプライアンス ポリシーをユーザーに割り当てると、Get-CsOnlineUser の出力に SBA が表示されるまでに時間がかかる場合があります。 

- Azure AD連絡先に対する逆引き番号参照は実行されません。 

- SBA では、通話転送設定はサポートされていません。 

- 動的緊急通報 (E911) 用に構成された緊急電話番号への緊急通報はサポートされていません。
