---
title: Skype for Business Server のオンプレミス パートナー アプリケーションを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: '概要: Skype for Business Server のオンプレミス パートナー アプリケーションを構成します。'
ms.openlocfilehash: 82db666dbbd94fdae8a99bca13954d33d6d5805f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828437"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>Skype for Business Server のオンプレミス パートナー アプリケーションを構成する
 
**概要:** Skype for Business Server のオンプレミス パートナー アプリケーションを構成します。
  
OAuthTokenIssuer 証明書を割り当てた後、Skype for Business Server パートナー アプリケーションを構成する必要があります。 (説明する手順では、Microsoft Exchange Server 2013 と SharePoint の両方がパートナー アプリケーションとして機能し、オプションです。オンプレミスのパートナー アプリケーションを構成するには、まず次の Windows PowerShell スクリプトをコピーし、コードをメモ帳 (または他のテキスト エディター) に貼り付けます。
  
```PowerShell
if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
   {
       Remove-CsPartnerApplication app
   }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
        
if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
           }
     }

$shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
        
if ($shp -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
    }
else
    {
       if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.sharepoint
  
             New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl https://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
            }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

コードをコピーした後、スクリプトを .PS1 ファイル拡張子を使用して保存します (例: C:\Scripts\ServerToServerAuth.ps1)。 このスクリプトを実行する前に、メタデータ URL と https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 、Exchange 2013 サーバーと SharePoint サーバーで使用されるメタデータ URL をそれぞれ置き換える必要があります。 それぞれの製品のメタデータ URL を識別する方法については、Exchange 2013 および SharePoint の製品ドキュメントを参照してください。
  
このスクリプトの最後の行で、Set-CsOAuthConfiguration コマンドレットが次の構文で呼び出されます。
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Set-CsOAuthConfiguration を呼び出すときに Realm パラメーターが使用されなかったため、領域には組織の完全修飾ドメイン名 (FQDN) が自動的に設定されます (例: litwareinc.com)。領域名が組織名と異なる場合は、次のように領域名を指定する必要があります。
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

これらの変更を行った後、Skype for Business Server 管理シェル内からスクリプト ファイルを実行して、スクリプトを実行し、Exchange 2013 と SharePoint の両方をパートナー アプリケーションとして構成できます。 例:
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

このスクリプトは、Exchange 2013 と SharePoint Server の両方がインストールされていない場合でも実行できます。SharePoint Server がインストールされていない場合でも、SharePoint Server をパートナー アプリケーションとして構成しても問題は発生しません。
  
このスクリプトを実行したときに、次のようなエラー メッセージが表示されることがあります。
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

このエラー メッセージは、通常は次の 2 つのどちらかを意味します。1) スクリプトに指定されたいずれかの URL が無効である (いずれかのメタデータ URL が実際のメタデータ URL ではない)。または、2) いずれかのメタデータ URL に接続できない。これが発生した場合は、URL が正しいこと、およびアクセス可能であることを確認し、スクリプトを再実行します。
  
Skype for Business Server のパートナー アプリケーションを作成した後、Skype for Business Server を Exchange 2013 のパートナー アプリケーションとして構成する必要があります。 Exchange 2013 のパートナー アプリケーションを構成するには、次のスクリプトを実行Configure-EnterprisePartnerApplication.ps1。行う必要があるのは、Skype for Business Server のメタデータ URL を指定し、Skype for Business Server が新しいパートナー アプリケーションかどうかを示す方法です。 
  
Skype for Business Server を Exchange のパートナー アプリケーションとして構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します。
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


