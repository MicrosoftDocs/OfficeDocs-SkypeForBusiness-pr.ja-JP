---
title: 'Lync Server 2013: 既存の Web サービス構成設定を削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faecc3675e4ed22e6bab3a85825ae65c50a8511f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="9531c-102">Lync Server 2013 で既存の Web サービスの構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="9531c-102">Delete existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9531c-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9531c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9531c-104">Web サービス構成設定を削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9531c-104">Follow these steps to delete web service configuration settings.</span></span>

<div>

## <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="9531c-105">Web サービス構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="9531c-105">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="9531c-106">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9531c-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="9531c-107">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9531c-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9531c-108">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9531c-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9531c-109">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**Web サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9531c-109">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="9531c-110">[**Web サービス**] ページの検索フィールドに、削除するポリシーの名前の全体または一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="9531c-110">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="9531c-111">ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9531c-111">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="9531c-112">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9531c-112">Click **OK**.</span></span>

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9531c-113">Windows PowerShell コマンドレットを使用して Web サービスの構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="9531c-113">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9531c-114">Web サービス構成設定は、Windows PowerShell と**CsWebServiceConfiguration**コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="9531c-114">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="9531c-115">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="9531c-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9531c-116">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9531c-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="9531c-117">Web サービス構成設定の特定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="9531c-117">To delete a specific collection of web service configuration settings</span></span>

  - <span data-ttu-id="9531c-118">次のコマンドを実行すると、レドモンド サイトに適用されている Web サービス セキュリティ設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="9531c-118">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="9531c-119">サイト スコープに適用されているすべての Web サービス構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="9531c-119">To delete all of the web service configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="9531c-120">次のコマンドを実行すると、サービス スコープに適用されているすべての Web サービス セキュリティ設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="9531c-120">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="9531c-121">証明書認証を許可しているすべての Web サービス構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="9531c-121">To delete all of the web service configuration settings that allow certificate authentication</span></span>

  - <span data-ttu-id="9531c-122">次のコマンドを実行すると、証明書認証の使用を許可しているすべての Web サービス セキュリティ設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="9531c-122">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

<span data-ttu-id="9531c-123">詳細については、「 [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9531c-123">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9531c-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="9531c-124">See Also</span></span>


[<span data-ttu-id="9531c-125">Lync Server 2013 コントロールパネルで認証を構成する</span><span class="sxs-lookup"><span data-stu-id="9531c-125">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

