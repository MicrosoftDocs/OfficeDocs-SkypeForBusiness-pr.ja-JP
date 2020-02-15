---
title: クライアントバージョン構成設定の既存のコレクションを削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00b594254b4ecac166be8e639dd8e7d437fcdffc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="5921a-102">Lync Server 2013 でクライアントバージョン構成設定の既存のコレクションを削除する</span><span class="sxs-lookup"><span data-stu-id="5921a-102">Delete an existing collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5921a-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5921a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5921a-104">以前にサイト用に構成されたクライアント構成設定を削除する場合は、Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルから設定を削除できます。</span><span class="sxs-lookup"><span data-stu-id="5921a-104">If you want to remove the client configuration settings that have been previously configured for a site, you can remove the settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="5921a-105">Lync Server コントロールパネルを使用してクライアント構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="5921a-105">To remove client configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5921a-106">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5921a-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5921a-107">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5921a-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5921a-108">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5921a-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5921a-109">左側のナビゲーションバーで [**クライアント**] をクリックし、[**クライアントバージョンの構成**] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5921a-109">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="5921a-110">サイトを選択し、[**編集**]、[**削除**]、[ **OK**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5921a-110">Select the site, click **Edit**, click **Delete**, and then click **OK**.</span></span>

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5921a-111">Windows PowerShell コマンドレットを使用してクライアントバージョン構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="5921a-111">Removing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5921a-112">クライアントバージョン構成**設定は、コマンドレット**を使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="5921a-112">You can delete client version configuration settings by using the **Remove-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="5921a-113">このコマンドレットは、Lync Server 2013 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="5921a-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5921a-114">リモート Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Microsoft Lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)を使用したリモート PowerShell の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5921a-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a><span data-ttu-id="5921a-115">指定したクライアントバージョン構成設定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="5921a-115">To remove a specified collection of client version configuration settings</span></span>

  - <span data-ttu-id="5921a-116">次のコマンドは、Redmond サイトに適用されているクライアントバージョンの構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="5921a-116">The following command removes the client version configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="5921a-117">サイトスコープに適用されているすべてのクライアントバージョン構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="5921a-117">To remove all the client version configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="5921a-118">このコマンドは、サイトスコープで構成されているすべてのクライアントバージョン構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="5921a-118">This command removes all the client version configuration settings configured at the site scope:</span></span>
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a><span data-ttu-id="5921a-119">DefaultAction プロパティの値に基づいて、すべてのクライアントバージョン構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="5921a-119">To remove all the client version configuration settings based on the value of the DefaultAction property</span></span>

  - <span data-ttu-id="5921a-120">次のコマンドを実行すると、既定のアクションが "ブロック" に設定されているすべてのクライアントバージョンの構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="5921a-120">And this command removes all the client version configuration settings where the default action has been set to "Block":</span></span>
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

<span data-ttu-id="5921a-121">詳細については、「 [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5921a-121">For details, see the Help topic for the [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

