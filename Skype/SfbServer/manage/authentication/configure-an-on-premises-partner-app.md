---
title: Skype for Business Server 用のオンプレミスパートナーアプリケーションを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: '概要: Skype for Business Server 用のオンプレミスパートナーアプリケーションを構成します。'
ms.openlocfilehash: 3f8aa3bfc7407ccf6409d00c540cfeab724913ab
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818829"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a><span data-ttu-id="0162f-103">Skype for Business Server 用のオンプレミスパートナーアプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="0162f-103">Configure an on-premises partner application for Skype for Business Server</span></span>
 
<span data-ttu-id="0162f-104">**概要:** Skype for Business Server 用のオンプレミスパートナーアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="0162f-104">**Summary:** Configure an on-premises partner application for Skype for Business Server.</span></span>
  
<span data-ttu-id="0162f-105">OAuthTokenIssuer 証明書を割り当てたら、Skype for Business Server パートナーアプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0162f-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Skype for Business Server partner applications.</span></span> <span data-ttu-id="0162f-106">(説明する必要がある手順では、Microsoft Exchange Server 2013 と SharePoint の両方を、パートナーアプリケーションとして機能するように構成します。これはオプションです)。オンプレミスパートナーアプリケーションを構成するには、まず、次の Windows PowerShell スクリプトをコピーし、メモ帳 (またはその他のテキストエディター) にコードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0162f-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and SharePoint to act as partner applications, which is optional.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>
  
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

<span data-ttu-id="0162f-107">コードをコピーした後、スクリプトを .PS1 ファイル拡張子を使用して保存します (例: C:\Scripts\ServerToServerAuth.ps1)。</span><span class="sxs-lookup"><span data-stu-id="0162f-107">After copying the code, save the script using a .PS1 file extension (for example, C:\Scripts\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="0162f-108">このスクリプトを実行する前に、メタデータの Url https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1とhttp://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 、Exchange 2013 および SharePoint サーバーで使用されるメタデータ url をそれぞれ置換する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0162f-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="0162f-109">各製品のメタデータ URL を特定する方法については、Exchange 2013 と SharePoint の製品に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0162f-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>
  
<span data-ttu-id="0162f-110">このスクリプトの最後の行で、Set-CsOAuthConfiguration コマンドレットが次の構文で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0162f-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="0162f-p103">Set-CsOAuthConfiguration を呼び出すときに Realm パラメーターが使用されなかったため、領域には組織の完全修飾ドメイン名 (FQDN) が自動的に設定されます (例: litwareinc.com)。領域名が組織名と異なる場合は、次のように領域名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0162f-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

<span data-ttu-id="0162f-113">これらの変更を加えた後は、Skype for Business Server 管理シェルからスクリプトファイルを実行して、スクリプトを実行し、Exchange 2013 と SharePoint の両方をパートナーアプリケーションとして構成できます。</span><span class="sxs-lookup"><span data-stu-id="0162f-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="0162f-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0162f-114">For example:</span></span>
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

<span data-ttu-id="0162f-115">このスクリプトは、Exchange 2013 と SharePoint Server の両方がインストールされていない場合でも実行できます。 sharepoint Server がインストールされていない場合でも、パートナーアプリケーションとして SharePoint Server を構成すると、問題は発生しません。</span><span class="sxs-lookup"><span data-stu-id="0162f-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>
  
<span data-ttu-id="0162f-116">このスクリプトを実行したときに、次のようなエラー メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="0162f-116">When you run this script you might receive an error message similar to the following:</span></span>
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

<span data-ttu-id="0162f-p105">このエラー メッセージは、通常は次の 2 つのどちらかを意味します。1) スクリプトに指定されたいずれかの URL が無効である (いずれかのメタデータ URL が実際のメタデータ URL ではない)。または、2) いずれかのメタデータ URL に接続できない。これが発生した場合は、URL が正しいこと、およびアクセス可能であることを確認し、スクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="0162f-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>
  
<span data-ttu-id="0162f-119">Skype for Business Server 用パートナーアプリケーションを作成した後、Skype for Business Server を Exchange 2013 のパートナーアプリケーションとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0162f-119">After creating the partner application for Skype for Business Server you must then configure Skype for Business Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="0162f-120">Configure-EnterprisePartnerApplication を実行して、Exchange 2013 のパートナーアプリケーションを構成することができます。Skype for Business Server のメタデータ URL を指定するだけで、Skype for Business Server が新しいパートナーアプリケーションであることを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="0162f-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Skype for Business Server and indicate that Skype for Business Server is the new partner application.</span></span> 
  
<span data-ttu-id="0162f-121">Skype for Business Server を Exchange のパートナーアプリケーションとして構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0162f-121">To configure Skype for Business Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


