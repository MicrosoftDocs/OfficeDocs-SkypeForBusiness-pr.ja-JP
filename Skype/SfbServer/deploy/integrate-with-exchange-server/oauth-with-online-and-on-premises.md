---
title: Skype ビジネス オンラインと Exchange サーバーの間の統合
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: OAuth を構成するオンライン ビジネスの社内の Exchange と Skype との間の認証は、ビジネスおよび Exchange の統合機能の機能のサポート」に記載の Skype を使用できます。
ms.openlocfilehash: c6a3819c9ec6ae0c207307a23f67bf04e4f07ac0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894240"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a>オンライン ビジネス用の Skype またはマイクロソフトのチームと Exchange Server との統合を構成します。 

ビジネス オンラインの Exchange サーバーと Skype との間の統合を構成すると、Skype の[機能のサポート](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)」で説明されているビジネスと Exchange の統合の機能が有効にします。

2019 を介して Exchange Server 2013 との統合をこのトピックに適用されます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>事前に必要な知識

- このタスクを完了するまでの予想所要時間: 15 分

-  この手順を実行するには、アクセス許可が割り当てられている必要があります。 必要なアクセス許可を表示するには、 [Exchange およびシェル インフラストラクチャのアクセス許可](https://go.microsoft.com/fwlink/p/?LinkId=746511)を参照してください。

- このトピックの手順に適用されるキーボード ショートカットの詳細については、 [Exchange 管理センターでのキーボード ショートカット]( https://go.microsoft.com/fwlink/p/?LinkId=746512)を参照してください。

## <a name="configure-integration-between-exchange-server-and-o365"></a>Exchange Server および O365 間の統合を構成します。

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>手順 1: Exchange Server および O365 間 OAuth 認証を構成します。

次の資料の手順に従います。

[Exchange および Exchange Online 組織間の OAuth 認証を構成します。](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a>手順 2: Skype のオンライン ビジネスやチームのパートナー アプリケーションの新しいメール ユーザー アカウントを作成します。

この手順は、Exchange サーバー上で行われます。 これによって、メール ユーザーを作成し、適切な管理役割の権限を割り当てます。 このアカウントは、次の手順で使用します。

Exchange 組織用の検証済みのドメインを指定します。 このドメインは、オンプレミスの Exchange アカウントを使用するプライマリ SMTP ドメインとして使用する同じドメインにする必要があります。 このドメインと呼ばれる\<、検証済みのドメイン\>、次の手順にします。 また、 \<DomainControllerFQDN\>ドメイン コント ローラーの FQDN である必要があります。

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

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a>手順 3: を作成し、ビジネスをオンラインまたはチームの Skype のパートナーのアプリケーションを有効にします。

新しいパートナー アプリケーションを作成し、先に作成したアカウントを使用します。 設置型で、Exchange の PowerShell Exchange 組織で次のコマンドを実行します。

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a>成否を確認する

正常に作業している機能のいくつかを確認し、構成が正しいことを確認します。 

1. Outlook の予定表委任 2016 の Exchange Server とメールボックスの 2019 2 チームのユーザーを指定の動作を確認します。

2. モバイル クライアントの会話の履歴は、Outlook の会話履歴フォルダーに表示されていることを確認します。

代わりに、トラフィックを見てください。 OAuth のハンド シェークのトラフィックが非常に特徴的な (そして基本認証と同様に表示されない)、特に領域、どこを開始するために次のような発行元のトラフィックを参照してください: @ 00000004-0000-0ff1-ce00-000000000000 (こともありますが、前@ 記号)、渡されるトークンです。 ユーザー名またはパスワード、OAuth のポイントは表示されません。 ですが、'Office' の発行元が表示されます – ここでは「4」業務と、サブスクリプション レルムの Skype。

場合は必ず正常に OAuth を使用している、確認しておきます内容を予測して、どのようなトラフィックのようになります知っています。 [予想される結果を次のとおりです](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)が、ここでは、ごく標準的な[Microsoft アプリケーションで、OAuth トラフィックの例](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)(読み取り、更新トークンを使用しないが非常に役立ちます)、あり、Fiddler の拡張機能に、OAuth JWT (JSON を表示できるようになります。Web トークン)。

[を設定するには 1 つの例](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)を次のとおりですが、このプロセスに着手するときに任意のネットワーク トレース ツールを使用することができます。

## <a name="related-topics"></a>関連トピック

[Exchange および Exchange Online 組織間の OAuth 認証を構成します。](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
