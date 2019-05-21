---
title: Skype for Business Online と Exchange server の統合
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: オンプレミスの Exchange と Skype for Business Online の間で OAuth 認証を構成すると、機能のサポートで説明されている Skype for Business と Exchange の統合機能が有効になります。
ms.openlocfilehash: be1fd4ae0c1a1046a8da1d9a30550ac238a4034a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278127"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a>Skype for Business Online または Microsoft Teams と Exchange Server との統合を構成する 

Exchange server と Skype for Business Online との統合を構成すると、[機能のサポート](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)で説明されている Skype for Business と Exchange の統合機能が有効になります。

このトピックは、Exchange Server 2013 から2019への統合に適用されます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>事前に必要な知識

- このタスクを完了するまでの予想所要時間: 15 分

-  この手順を実行するには、アクセス許可が割り当てられている必要があります。 必要なアクセス許可を確認するには、「 [Exchange とシェルインフラストラクチャのアクセス許可](https://go.microsoft.com/fwlink/p/?LinkId=746511)」を参照してください。

- このトピックの手順に適用される可能性があるショートカットキーの詳細については、「 [Exchange 管理センターのキーボードショートカット]( https://go.microsoft.com/fwlink/p/?LinkId=746512)」を参照してください。

## <a name="configure-integration-between-exchange-server-and-o365"></a>Exchange Server と O365 の統合を構成する

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>手順 1: Exchange Server と O365 の間の OAuth 認証を構成する

次の記事の手順を実行します。

[Exchange と Exchange Online の組織間の OAuth 認証を構成する](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a>手順 2: Skype for Business Online または Teams パートナーアプリケーションの新しいメールユーザーアカウントを作成する

この手順は Exchange server で行います。 これによって、メール ユーザーを作成し、適切な管理役割の権限を割り当てます。 このアカウントは、次の手順で使用します。

Exchange 組織の確認済みドメインを指定します。 このドメインは、オンプレミスの Exchange アカウントで使用されるプライマリ SMTP ドメインと同じドメインである必要があります。 このドメインは、次\<の手順で\> 、確認済みドメインとして参照されます。 また、ドメイン\<コントローラーの fqdn\>として domainコントローラ fqdn を指定する必要があります。

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

このコマンドによって、アドレス一覧で新しいメール ユーザーが非表示になります。

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

次の 2 つのコマンドでは、この新しいアカウントに UserApplication および ArchiveApplication の管理役割を割り当てます。

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a>手順 3: Skype for Business Online または Teams のパートナーアプリケーションを作成して有効にする

新しいパートナー アプリケーションを作成し、先に作成したアカウントを使用します。 オンプレミスの Exchange 組織の Exchange PowerShell で次のコマンドを実行します。

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a>成否を確認する

機能の一部が正常に動作していることを確認して、構成が正しいことを確認します。 

1. Outlook の予定表の委任の確認 Exchange Server 2016 または2019メールボックスを使用している2つの Teams ユーザーの間で動作します。

2. [モバイルクライアントの会話履歴を確認する] が Outlook の [会話履歴] フォルダーに表示されます。

または、トラフィックを確認します。 OAuth ハンドシェイクのトラフィックは、実際には非常に優れています (基本的な認証とは言えません)。特に、領域については、次のような発行者のトラフィックを表示することになります (例: 00000004-0000-0ff1-ce00-000000000000 @@ sign)。これは、渡されるトークンの中にあります。 OAuth のポイントであるユーザー名またはパスワードは表示されません。 ただし、"Office" の発行者が表示されます。この例では、「4」が Skype for Business であり、サブスクリプションの領域です。

OAuth を正常に使用していることを確認したい場合は、想定される内容と、トラフィックの外観を把握してください。 ここ[](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)では、 [Microsoft アプリケーションでの oauth トラフィックの](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)標準的な例を示します (この例では、更新トークンを使用していませんが、Fiddler の拡張機能を使って oauth JWT (JSON) を表示することができます)。Web Token)。

次に[1 つを設定する例](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)を示しますが、この処理を実行する任意のネットワークトレースツールを使用できます。

## <a name="related-topics"></a>関連トピック

[Exchange と Exchange Online の組織間の OAuth 認証を構成する](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
