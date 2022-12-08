---
title: Teams PowerShell モジュールでのアプリケーション ベースの認証
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Microsoft Teams の管理に使用される Teams PowerShell モジュールでのアプリケーション ベースの認証について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04cc2e3c069f30e44dd0c62a42be42fd1cce16b7
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307952"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Teams PowerShell モジュールでのアプリケーション ベースの認証

アプリケーション ベースの認証は、バージョン 4.7.1-preview 以降の Teams PowerShell モジュールでサポートされるようになりました。 現在、この認証モードは商用環境でのみサポートされています。


## <a name="cmdlets-supported"></a>サポートされているコマンドレット

以下に示すコマンドレットを除き、すべてのコマンドレットが現在サポートされています。 

  - New-Team
  - [Get|Set|新規|Sync]-CsOnlineApplicationInstance
  - \*-CsUserCallingSettings
  - \*-CsUserCallingDelegate
  - \*PolicyPackage\*
  - \*-CsTeamsShiftsConnection\*
  - \*-CsBatchTeamsDeployment\*


## <a name="examples"></a>例

次の例は、Azure AD アプリベースの認証で Teams PowerShell モジュールを使用する方法を示しています。 

- 証明書の拇印を使用して接続します。

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  CertificateThumbprint パラメーターを使用する場合は、コマンドを実行しているコンピューターに証明書をインストールする必要があります。 証明書は、ユーザー証明書ストアにインストールする必要があります。
  
- アクセス トークンを使用して接続する:
  
  アクセス トークンは、login.microsoftonline.com エンドポイントを介して取得できます。 "MS Graph" と "Skype と Teams テナント 管理 API" の 2 つのアクセス トークンが必要です。

  ```powershell
  $ClientSecret   = "…"
  $ApplicationID = "00000000-0000-0000-0000-000000000000"
  $TenantID = "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"

  $graphtokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "https://graph.microsoft.com/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret   
  }  

  $graphToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $graphtokenBody | Select-Object -ExpandProperty Access_Token 

  $teamstokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "48ac35b8-9aa8-4d74-927d-1f4a14a0b239/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret 
  } 

  $teamsToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $teamstokenBody | Select-Object -ExpandProperty Access_Token 

  Connect-MicrosoftTeams -AccessTokens @("$graphToken", "$teamsToken")
  ```
  
## <a name="how-does-it-work"></a>それはどのように動作しますか?

Teams PowerShell モジュールは、アプリケーション ID、テナント ID、証明書の拇印を使用してアプリ ベースのトークンをフェッチします。 Azure AD 内でプロビジョニングされたアプリケーション オブジェクトには、アクセス トークンで返されるディレクトリ ロールが割り当てられます。 セッションのロールベースのアクセス制御 (RBAC) は、トークンで使用できるディレクトリ ロール情報を使用して構成されます。


## <a name="setup-application-based-authentication"></a>アプリケーション ベースの認証を設定する

アプリケーション オブジェクトを使用した認証には、初期オンボードが必要です。 アプリケーションとサービス プリンシパルは同じ意味で使用されますが、アプリケーションはクラス オブジェクトに似ていますが、サービス プリンシパルはクラスのインスタンスのようなものです。 これらのオブジェクトの詳細については、 [Azure Active Directory のアプリケーション オブジェクトとサービス プリンシパル オブジェクトに](/azure/active-directory/develop/app-objects-and-service-principals)関するページを参照してください。

Azure Ad でアプリケーションを作成するためのサンプル手順を以下に示します。詳細な手順については、この [記事](/azure/active-directory/develop/howto-create-service-principal-portal)を参照してください。

1. Azure AD でアプリケーションを登録する
2. アプリケーションに API アクセス許可を割り当てる
   - -Cs コマンドレットの場合\*、 - 必要なMicrosoft Graph APIアクセス許可は です`Organization.Read.All`。
   - 非 \*Cs コマンドレットの場合- 必要なMicrosoft Graph APIアクセス許可は`Organization.Read.All`、、`User.Read.All`、`Group.ReadWrite.All`、`AppCatalog.ReadWrite.All`、`TeamSettings.ReadWrite.All``Channel.Delete.All`、、`ChannelSettings.ReadWrite.All`です`ChannelMember.ReadWrite.All`。  
3. 自己署名証明書を生成する
4. Azure AD アプリケーションに証明書をアタッチする
5. [Azure AD ロール](/microsoftteams/using-admin-roles#teams-roles-and-capabilities)をアプリケーションに割り当てる

アプリケーションには、適切な RBAC ロールが割り当てられている必要があります。 アプリは Azure AD でプロビジョニングされるため、サポートされている任意の組み込みロールを使用できます。
 
