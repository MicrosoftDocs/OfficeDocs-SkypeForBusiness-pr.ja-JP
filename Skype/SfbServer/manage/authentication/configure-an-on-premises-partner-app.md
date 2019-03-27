---
title: Skype のビジネス サーバーの設置パートナー アプリケーションを構成します。
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: '概要: は、Skype のビジネス サーバーの設置パートナー アプリケーションを構成します。'
ms.openlocfilehash: fe80ae08a730ad4765c366a77fd0c44daaa18899
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878481"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a><span data-ttu-id="73acb-103">Skype のビジネス サーバーの設置パートナー アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="73acb-103">Configure an on-premises partner application for Skype for Business Server</span></span>
 
<span data-ttu-id="73acb-104">**の概要:** Skype のビジネス サーバーの設置パートナー アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="73acb-104">**Summary:** Configure an on-premises partner application for Skype for Business Server.</span></span>
  
<span data-ttu-id="73acb-105">サーバーのビジネス パートナーのアプリケーションを Skype を構成する必要がありますし、OAuthTokenIssuer の証明書を割り当てるとします。</span><span class="sxs-lookup"><span data-stu-id="73acb-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Skype for Business Server partner applications.</span></span> <span data-ttu-id="73acb-106">(説明する手順構成 Microsoft Exchange Server 2013 と SharePoint、パートナーのアプリケーションとして動作するように省略可能である。)設置パートナー アプリケーションを構成するのには、次の Windows PowerShell スクリプトをコピーして、メモ帳 (または他の任意のテキスト エディター) にコードを貼り付けて起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73acb-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and SharePoint to act as partner applications, which is optional.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>
  
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

<span data-ttu-id="73acb-107">コードをコピーした後、スクリプトを .PS1 ファイル拡張子を使用して保存します (例: C:\Scripts\ServerToServerAuth.ps1)。</span><span class="sxs-lookup"><span data-stu-id="73acb-107">After copying the code, save the script using a .PS1 file extension (for example, C:\Scripts\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="73acb-108">このスクリプトを実行する前に、メタデータの Url を置換する必要があります注https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1とhttp://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1それぞれの Exchange 2013 と SharePoint のサーバーによって使用されるメタデータの Url を持つ。</span><span class="sxs-lookup"><span data-stu-id="73acb-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="73acb-109">それぞれの製品のメタデータの URL を特定する方法については、Exchange 2013 と SharePoint の製品マニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73acb-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>
  
<span data-ttu-id="73acb-110">このスクリプトの最後の行で、Set-CsOAuthConfiguration コマンドレットが次の構文で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="73acb-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="73acb-p103">Set-CsOAuthConfiguration を呼び出すときに Realm パラメーターが使用されなかったため、領域には組織の完全修飾ドメイン名 (FQDN) が自動的に設定されます (例: litwareinc.com)。領域名が組織名と異なる場合は、次のように領域名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73acb-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

<span data-ttu-id="73acb-113">変更後のスクリプトを実行し、パートナーのアプリケーションとビジネス サーバー管理シェルには、Skype 内からスクリプト ファイルを実行して、Exchange 2013 および SharePoint の両方を構成します。</span><span class="sxs-lookup"><span data-stu-id="73acb-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="73acb-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="73acb-114">For example:</span></span>
  
```
C:\Scripts\ServerToServerAuth.ps1
```

<span data-ttu-id="73acb-115">両方の Exchange 2013 をする必要はありませんし、SharePoint Server がインストールされている場合でも、このスクリプトを実行することができることに注意してください: 問題は発生しませんがあるない場合でも、パートナーのアプリケーションと SharePoint サーバーを構成すると答えると場合は、SharePoint のサーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="73acb-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>
  
<span data-ttu-id="73acb-116">このスクリプトを実行したときに、次のようなエラー メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="73acb-116">When you run this script you might receive an error message similar to the following:</span></span>
  
```
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

<span data-ttu-id="73acb-p105">このエラー メッセージは、通常は次の 2 つのどちらかを意味します。1) スクリプトに指定されたいずれかの URL が無効である (いずれかのメタデータ URL が実際のメタデータ URL ではない)。または、2) いずれかのメタデータ URL に接続できない。これが発生した場合は、URL が正しいこと、およびアクセス可能であることを確認し、スクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="73acb-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>
  
<span data-ttu-id="73acb-119">ビジネス サーバーの Skype のパートナーのアプリケーションを作成した後、Skype のビジネスのサーバーを Exchange 2013 のパートナーのアプリケーションを構成してください。</span><span class="sxs-lookup"><span data-stu-id="73acb-119">After creating the partner application for Skype for Business Server you must then configure Skype for Business Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="73acb-120">構成の EnterprisePartnerApplication.ps1 はスクリプトを実行して Exchange 2013 のパートナーのアプリケーションを構成することができます。実行する必要があるものは、Skype のビジネス サーバーのメタデータの URL を指定して、Skype のビジネス サーバーが新しいパートナー アプリケーションであることを示すだけです。</span><span class="sxs-lookup"><span data-stu-id="73acb-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Skype for Business Server and indicate that Skype for Business Server is the new partner application.</span></span> 
  
<span data-ttu-id="73acb-121">Skype ビジネス サーバー アプリケーションとして構成する、パートナーの交換、Exchange 管理シェルを開き次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="73acb-121">To configure Skype for Business Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>
  
```
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


