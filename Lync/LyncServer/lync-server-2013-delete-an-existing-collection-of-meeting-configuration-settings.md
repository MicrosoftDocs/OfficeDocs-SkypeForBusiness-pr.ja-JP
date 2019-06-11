---
title: 会議の構成設定の既存のコレクションを削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d564cf8fbcfb8c66df5e84841aae456913f1dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="bbefc-102">Lync Server 2013 で既存の会議構成設定のコレクションを削除する</span><span class="sxs-lookup"><span data-stu-id="bbefc-102">Delete an existing collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbefc-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bbefc-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bbefc-104">サイトまたはユーザーの構成を削除できます。</span><span class="sxs-lookup"><span data-stu-id="bbefc-104">You can delete a site or user configuration.</span></span> <span data-ttu-id="bbefc-105">グローバル構成を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="bbefc-105">The global configuration cannot be removed.</span></span> <span data-ttu-id="bbefc-106">グローバル構成を削除すると、グローバル構成は自動的に既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="bbefc-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a><span data-ttu-id="bbefc-107">サイトまたはユーザーの会議の設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="bbefc-107">To delete a site or user meeting configuration</span></span>

1.  <span data-ttu-id="bbefc-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bbefc-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bbefc-109">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bbefc-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bbefc-110">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bbefc-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bbefc-111">左側のナビゲーションバーで、[**会議**] をクリックし、[**会議の設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbefc-111">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="bbefc-112">会議構成の一覧で、削除するサイトまたはプールの構成をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbefc-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bbefc-113">Windows PowerShell コマンドレットを使用して会議の構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="bbefc-113">Removing Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bbefc-114">会議の設定を削除するには、Windows PowerShell を使用するか、または、Csmeeting 構成コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bbefc-114">Meeting settings can be deleted by using Windows PowerShell and the Remove-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="bbefc-115">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="bbefc-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bbefc-116">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbefc-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a><span data-ttu-id="bbefc-117">会議の構成設定の指定したコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="bbefc-117">To remove a specified collection of meeting configuration settings</span></span>

  - <span data-ttu-id="bbefc-118">このコマンドを実行すると、Redmond サイトに適用された会議の構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="bbefc-118">This command removes the meeting configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="bbefc-119">サイトの範囲に適用されているすべての会議の設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="bbefc-119">To remove all the meeting configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="bbefc-120">このコマンドを実行すると、サイトのスコープに適用されているすべての会議の構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="bbefc-120">This command removes all the meeting configuration settings applied to the site scope:</span></span>
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a><span data-ttu-id="bbefc-121">既定で匿名ユーザーを許可する会議の構成設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="bbefc-121">To remove all the meeting configuration settings that admit anonymous users by default</span></span>

  - <span data-ttu-id="bbefc-122">また、匿名ユーザーが既定で許可される設定をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="bbefc-122">And this one removes all the settings that allow anonymous users to be admitted by default:</span></span>
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

<span data-ttu-id="bbefc-123">詳細については、「 [Cs会議構成の削除](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15))」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbefc-123">For more information, see the help topic for the [Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

