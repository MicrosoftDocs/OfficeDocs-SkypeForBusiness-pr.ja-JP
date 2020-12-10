---
title: ダイレクトルーティング SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
description: 詳細については、「構成」、「基本的な展開の決定事項」、「ボイスルーティングの考慮事項」などのダイレクトルーティングについて説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b30f8a435f256edc816ebeea075425fddeaf8bb
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611791"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a>Survivable Branch Appliance (SBA) – Direct Routing-パブリックプレビュー


> [!NOTE]
> これはパブリックプレビューのリリースです。

場合によっては、ダイレクトルーティングを使用して Microsoft 電話システムに接続すると、インターネットが停止することがあります。

顧客サイト------------------------------------------ ただし、ブランチ内のイントラネットは完全に機能しているため、ユーザーは PSTN 接続を提供するセッションボーダーコントローラー (SBC) に接続できます。

この記事では、Survivable Branch Appliance (SBA) を使用して、停止時に Microsoft 電話システムが PSTN (公衆交換電話網) 通話の発信と受信を継続できるようにする方法について説明します。

## <a name="prerequisites"></a>前提条件

SBA は、Microsoft が、そのコードを SBCs のファームウェアに埋め込むために Microsoft が提供する配布可能なコードです。 

埋め込まれた Survivable Branch アプライアンスを使って、最新のセッションボーダーコントローラーのファームウェアを取得するには、SBC ベンダーにお問い合わせください。 さらに、次のものが必要です。

- この SBC は、メディアをバイパスするように構成する必要があります。これにより、ブランチサイトの Microsoft Teams クライアントは、SBC でメディアに直接流れることができます。 

- SBA VM OS で TLS 1.2 を有効にする必要があります。

## <a name="supported-teams-clients"></a>サポートされているチームクライアント

SBA 機能は、次の Microsoft Teams クライアントでサポートされています。 

- Microsoft Teams Windows デスクトップ 

- Microsoft Teams macOS デスクトップ 

## <a name="how-it-works"></a>メカニズム

インターネットの停止中は、チームクライアントが SBA に自動的に切り替える必要があります。進行中の通話は、引き続き中断されます。 ユーザーからの操作は必要ありません。 チームクライアントがインターネットが稼働していることを検出し、発信通話が完了したら、クライアントは通常の操作モードに戻り、他の Teams サービスに接続します。 SBA によって、収集された通話データレコードがクラウドにアップロードされ、通話履歴が更新され、テナント管理者がこの情報を確認できるようになります。 

Microsoft Teams クライアントがオフラインモードの場合は、次のような呼び出しに関連する機能を利用できます。 

- ローカルの SBA/SBC 経由で、メディアを SBC を介して流れる PSTN 通話。

- ローカルの SBA/SBC での PSTN 通話の受信。 SBC を介してメディアが流れます。 

- PSTN 通話を保留および再開します。

## <a name="configuration"></a>構成

SBA 機能が機能するためには、チームクライアントは、どの SBAs が各ブランチサイトで利用可能で、どの SBAs がそのサイトのユーザーに割り当てられているかを知る必要があります。 構成の手順は次のとおりです。

1. SBAs を作成します。
2. Teams ブランチ survivability ポリシーを作成します。
3. ユーザーにポリシーを割り当てます。
4. Azure Active Directory を使用して SBA にアプリケーションを登録します。

すべての構成は、Skype for Business Online PowerShell コマンドレットを使用して行われます。 (Teams 管理センターでは、ダイレクトルーティング SBA 機能はまだサポートされていません)。 

(SBC の設定方法については、「SBC ベンダーのドキュメントへのリンク」を参照してください)。この記事の最後にある「セッション境界コントローラーの構成」をご覧ください。)

### <a name="create-the-sbas"></a>SBAs を作成する

SBAs を作成するには、New-CsTeamsSurvivableBranchAppliance コマンドレットを使用します。 このコマンドレットには、次のパラメーターがあります。

| パラメーター| 説明 |
| :------------|:-------|
| Identity  | SBA の id  |
| Fqdn | SBA の FQDN |
| サイト | SBA が配置されている TenantNetworkSite |
| 説明 | テキストを無料で表示 |
|||

次に例を示します。

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Teams ブランチ Survivability ポリシーを作成する 

ポリシーを作成するには、New-CsTeamsSurvivableBranchAppliancePolicy コマンドレットを使用します。 このコマンドレットには、次のパラメーターがあります。 ポリシーには1つ以上の SBAs を含めることができることに注意してください。

| パラメーター| 説明 |
| :------------|:-------|
| Identity | ポリシーの id |
| BranchApplianceFqdns  | サイト内の SBA の FQDN。 |
||

次に例を示します。

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

Set-CsTeamsSurvivableBranchAppliancePolicy コマンドレットを使用して、ポリシーから SBAs を追加または削除することができます。 次に例を示します。 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>ユーザーにポリシーを割り当てる

個々のユーザーにポリシーを割り当てるには、Grant-CsTeamsSurvivableBranchAppliancePolicy コマンドレットを使用します。 このコマンドレットには、次のパラメーターがあります。

| パラメーター| 説明 |
| :------------|:-------|
| Identity | ユーザーの id |
| PolicyName | ポリシーの id |
||

次に例を示します。

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

次の例に示すように、$Null ポリシーを付与することで、ユーザーからポリシーを削除することができます。

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Azure Active Directory を使用して SBA にアプリケーションを登録する

テナント内で別の SBAs を使用して、Microsoft 365 から必要なデータを読み取ることができるようにするには、SBA 用のアプリケーションを Azure Active Directory と共に登録する必要があります。 

アプリケーションの登録の詳細については、以下を参照してください。

- [Azure Active Directory 用の基幹業務アプリの開発](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Microsoft identity platform にアプリケーションを登録](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)します。  

テナント内のすべての SBAs で使用する1つのアプリケーションのみ登録する必要があります。 

SBA の登録では、登録によって作成される次の値を指定する必要があります。 

- アプリケーション (クライアント) ID 
- クライアントシークレット 

SBA アプリケーションの場合は、次の点にご注意ください。 

- 名前は任意の名前にすることができます。  
- サポートされているアカウントの種類 = この組織ディレクトリのアカウントのみ。 
- Web リダイレクト Uri = https://login.microsoftonline.com/common/oauth2/nativeclient 。
- 暗黙的な許可トークン = アクセストークンと ID トークン。 
- API 権限 = Skype および Teams のテナント管理者アクセス-> アプリケーションのアクセス許可 > application_access_custom_sba_appliance。
- クライアントシークレット: 任意の説明と有効期限を使用できます。 
- クライアントシークレットは、作成した後すぐにコピーしてください。 
- アプリケーション (クライアント) ID は [概要] タブに表示されます。

次に、次の手順を実行します。

1. アプリケーションを登録します。
2. 暗黙的な grant トークンを設定します。
3. API のアクセス許可を設定します。
4. クライアントシークレットを作成します。


## <a name="session-border-controller-configuration"></a>セッション境界コントローラー構成 

埋め込まれた Survivable Branch Appliance を使ってセッション境界コントローラーを構成する方法については、「SBC ベンダーから提供されるドキュメント」を参照してください。 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [リボン](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE (システム)](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>問題の報告

問題が SBC ベンダーのサポート組織に報告されます。 問題を報告するときに、Survivable Branch アプライアンスが構成されていることを示します。

## <a name="known-issues"></a>既知の問題

- 新しい Survivable Branch アプライアンスを追加した場合、Survivable Branch Appliance のポリシーで使用できるようになるまでに少し時間がかかる場合があります。

- Survivable Branch Appliance のポリシーをユーザーに割り当てる場合は、SBA が Get Csonline ユーザーの出力に表示されるまでに少し時間がかかることがあります。 

- Azure AD の連絡先に対して数値のルックアップを逆に実行することはできません。 

- SBA は、着信の転送設定をサポートしていません。 

- 動的な緊急通報 (E911) 用に設定された緊急電話番号への緊急通話の発信はサポートされていません。

- Get-CsOnlineUser の出力に TeamsBranchSurvivabilityPolicy が表示されます。
