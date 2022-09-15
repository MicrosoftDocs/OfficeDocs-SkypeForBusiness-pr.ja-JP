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
description: Microsoft Teams の管理に使用される Teams PowerShell モジュールのアプリケーション ベースの認証について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea836225658292c312490704305261210ba0991c
ms.sourcegitcommit: 44d9f15f7f7c00b3651a11ff1e8b37dda1716a52
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2022
ms.locfileid: "67732784"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Teams PowerShell モジュールでのアプリケーション ベースの認証

アプリケーション ベースの認証は、Teams PowerShell モジュールでサポートされるようになりました。バージョン 4.7.1 以降のプレビューでは、一連のコマンドレットが制限されています。 現在、この認証モードは商用環境でのみサポートされています。 これは、Skype for Business Online の地域的にホストされた会議で以前に有効にされた顧客に対してはサポートされていません。


## <a name="cmdlets-supported"></a>サポートされているコマンドレット

\*すべての非 Cs コマンドレット (Get-Team など)、Get-CsTenant、Get-CsOnlineUser & Get-CsOnlineVoiceUserは既にサポートされています。 その他のコマンドレットは段階的にロールアウトされます。 


## <a name="examples"></a>例

次の例は、Azure AD アプリ ベースの認証で Teams PowerShell モジュールを使用する方法を示しています。 

- 証明書の拇印を使用して接続します。

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  CertificateThumbprint パラメーターを使用する場合は、コマンドを実行しているコンピューターに証明書をインストールする必要があります。 証明書は、ユーザー証明書ストアにインストールする必要があります。
  
- アクセス トークンを使用して接続する:
  
  アクセス トークンは、login.microsoftonline.com エンドポイントを使用して取得できます。 これには、"MS Graph" リソースと "Skype および Teams テナント 管理 API" リソースという 2 つのアクセス トークンが必要です。

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
  
## <a name="how-does-it-work"></a>どのように動作しますか?

Teams PowerShell モジュールは、アプリケーション ID、テナント ID、証明書拇印を使用してアプリ ベースのトークンをフェッチします。 Azure AD 内でプロビジョニングされたアプリケーション オブジェクトには、ディレクトリ ロールが割り当てられ、アクセス トークンで返されます。 セッションのロールベースのアクセス制御 (RBAC) は、トークンで使用できるディレクトリ ロール情報を使用して構成されます。


## <a name="setup-application-based-authentication"></a>アプリケーション ベースの認証をセットアップする

アプリケーション オブジェクトを使用した認証には、初期オンボードが必要です。 アプリケーションとサービス プリンシパルは同じ意味で使用されますが、アプリケーションはクラス オブジェクトに似ていますが、サービス プリンシパルはクラスのインスタンスのようなものです。 これらのオブジェクトの詳細については、 [Azure Active Directory のアプリケーション オブジェクトとサービス プリンシパル オブジェクトを](/azure/active-directory/develop/app-objects-and-service-principals)参照してください。

Azure Ad でアプリケーションを作成するための高度な手順については、以下で説明します。詳細な手順については、この [記事](/azure/active-directory/develop/howto-create-service-principal-portal)を参照してください。
  1. Azure AD にアプリケーションを登録する
  2. 自己署名証明書を生成する
  3. 証明書を Azure AD アプリケーションにアタッチする
  4. アプリケーションに Azure AD ロールを割り当てる

アプリケーションには、適切な RBAC ロールが割り当てられている必要があります。 アプリは Azure AD でプロビジョニングされているため、サポートされている組み込みロールのいずれかを使用できます。
 
