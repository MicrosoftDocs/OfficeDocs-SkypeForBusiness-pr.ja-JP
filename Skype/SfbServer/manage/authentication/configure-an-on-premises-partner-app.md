---
title: Skype のビジネス サーバーの設置パートナー アプリケーションを構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: '概要: は、Skype のビジネス サーバーの設置パートナー アプリケーションを構成します。'
ms.openlocfilehash: a13157d590d6cdd067ed2a0a717fd744adb9de4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913378"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>Skype のビジネス サーバーの設置パートナー アプリケーションを構成します。
 
**の概要:** Skype のビジネス サーバーの設置パートナー アプリケーションを構成します。
  
サーバーのビジネス パートナーのアプリケーションを Skype を構成する必要がありますし、OAuthTokenIssuer の証明書を割り当てるとします。 (説明する手順構成 Microsoft Exchange Server 2013 と SharePoint、パートナーのアプリケーションとして動作するように省略可能である。)設置パートナー アプリケーションを構成するのには、次の Windows PowerShell スクリプトをコピーして、メモ帳 (または他の任意のテキスト エディター) にコードを貼り付けて起動する必要があります。
  
```
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

コードをコピーした後、スクリプトを .PS1 ファイル拡張子を使用して保存します (例: C:\Scripts\ServerToServerAuth.ps1)。 このスクリプトを実行する前に、メタデータの Url を置換する必要があります注https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1とhttp://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1それぞれの Exchange 2013 と SharePoint のサーバーによって使用されるメタデータの Url を持つ。 それぞれの製品のメタデータの URL を特定する方法については、Exchange 2013 と SharePoint の製品マニュアルを参照してください。
  
このスクリプトの最後の行で、Set-CsOAuthConfiguration コマンドレットが次の構文で呼び出されます。
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Set-CsOAuthConfiguration を呼び出すときに Realm パラメーターが使用されなかったため、領域には組織の完全修飾ドメイン名 (FQDN) が自動的に設定されます (例: litwareinc.com)。領域名が組織名と異なる場合は、次のように領域名を指定する必要があります。
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

変更後のスクリプトを実行し、パートナーのアプリケーションとビジネス サーバー管理シェルには、Skype 内からスクリプト ファイルを実行して、Exchange 2013 および SharePoint の両方を構成します。 次に例を示します。
  
```
C:\Scripts\ServerToServerAuth.ps1
```

両方の Exchange 2013 をする必要はありませんし、SharePoint Server がインストールされている場合でも、このスクリプトを実行することができることに注意してください: 問題は発生しませんがあるない場合でも、パートナーのアプリケーションと SharePoint サーバーを構成すると答えると場合は、SharePoint のサーバーをインストールします。
  
このスクリプトを実行したときに、次のようなエラー メッセージが表示されることがあります。
  
```
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

このエラー メッセージは、通常は次の 2 つのどちらかを意味します。1) スクリプトに指定されたいずれかの URL が無効である (いずれかのメタデータ URL が実際のメタデータ URL ではない)。または、2) いずれかのメタデータ URL に接続できない。これが発生した場合は、URL が正しいこと、およびアクセス可能であることを確認し、スクリプトを再実行します。
  
ビジネス サーバーの Skype のパートナーのアプリケーションを作成した後、Skype のビジネスのサーバーを Exchange 2013 のパートナーのアプリケーションを構成してください。 構成の EnterprisePartnerApplication.ps1 はスクリプトを実行して Exchange 2013 のパートナーのアプリケーションを構成することができます。実行する必要があるものは、Skype のビジネス サーバーのメタデータの URL を指定して、Skype のビジネス サーバーが新しいパートナー アプリケーションであることを示すだけです。 
  
Skype ビジネス サーバー アプリケーションとして構成する、パートナーの交換、Exchange 管理シェルを開き次のようなコマンドを実行します。
  
```
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


