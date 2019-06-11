---
title: 'Lync Server 2013: ダイヤルイン会議のアクセス番号を削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2559b8a3e053c02a6a67ccc17ab5a1f25b46a05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="77411-102">Lync Server 2013 でダイヤルイン会議アクセス番号を削除する</span><span class="sxs-lookup"><span data-stu-id="77411-102">Delete a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77411-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="77411-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="77411-104">ダイヤルイン会議アクセス番号を削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="77411-104">Follow these steps to delete a dial-in conferencing access number.</span></span>

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="77411-105">ダイヤルイン会議のアクセス番号を削除するには</span><span class="sxs-lookup"><span data-stu-id="77411-105">To delete a dial-in conferencing access number</span></span>

1.  <span data-ttu-id="77411-106">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="77411-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="77411-107">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="77411-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="77411-108">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="77411-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="77411-109">左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="77411-109">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="77411-110">[ダイヤルイン アクセス番号] ページの一覧で、削除するダイヤルイン番号をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="77411-110">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="77411-111">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="77411-111">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="77411-112">Windows PowerShell コマンドレットを使用したダイヤルイン会議アクセス番号の削除</span><span class="sxs-lookup"><span data-stu-id="77411-112">Removing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="77411-113">Windows PowerShell と**CsDialInConferencingAccessNumber**コマンドレットを使用して、ダイヤルイン会議アクセス番号を削除できます。</span><span class="sxs-lookup"><span data-stu-id="77411-113">Dial-in conferencing access numbers can be deleted by using Windows PowerShell and the **Remove-CsDialInConferencingAccessNumber** cmdlet.</span></span> <span data-ttu-id="77411-114">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="77411-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="77411-115">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77411-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a><span data-ttu-id="77411-116">特定のダイヤルイン会議アクセス番号を削除するには</span><span class="sxs-lookup"><span data-stu-id="77411-116">To remove a specific dial-in conferencing access number</span></span>

  - <span data-ttu-id="77411-117">このコマンドは、Id sip:RedmondDialInAccess@litwareinc.com のダイヤルイン会議アクセス番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="77411-117">This command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a><span data-ttu-id="77411-118">特定の地域に割り当てられているダイヤルイン会議アクセス番号をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="77411-118">To remove all the dial-in conferencing access numbers assigned to a specific region</span></span>

  - <span data-ttu-id="77411-119">このコマンドは、北西地域に関連付けられているダイヤルイン会議アクセス番号をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="77411-119">This command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a><span data-ttu-id="77411-120">プライマリ言語に基づいてダイヤルイン会議アクセス番号を削除するには</span><span class="sxs-lookup"><span data-stu-id="77411-120">To remove dial-in conferencing access numbers based on primary language</span></span>

  - <span data-ttu-id="77411-121">このコマンドは、イタリア語が主要言語である、ダイヤルイン会議のすべてのアクセス番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="77411-121">This command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

<span data-ttu-id="77411-122">詳細については、 [CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77411-122">For more information, see the help topic for the [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

