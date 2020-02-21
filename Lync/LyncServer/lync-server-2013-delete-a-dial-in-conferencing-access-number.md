---
title: 'Lync Server 2013: ダイヤルイン会議アクセス番号の削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef5d0e51486ed6dca7c9ac17a991b0154c2f1135
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="939c8-102">Lync Server 2013 でダイヤルイン会議アクセス番号を削除する</span><span class="sxs-lookup"><span data-stu-id="939c8-102">Delete a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="939c8-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="939c8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="939c8-104">ダイヤルイン会議アクセス番号を削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="939c8-104">Follow these steps to delete a dial-in conferencing access number.</span></span>

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="939c8-105">ダイヤルイン会議アクセス番号を削除するには</span><span class="sxs-lookup"><span data-stu-id="939c8-105">To delete a dial-in conferencing access number</span></span>

1.  <span data-ttu-id="939c8-106">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="939c8-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="939c8-107">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="939c8-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="939c8-108">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939c8-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="939c8-109">左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939c8-109">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="939c8-110">[ダイヤルイン アクセス番号] ページの一覧で、削除するダイヤルイン番号をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939c8-110">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="939c8-111">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939c8-111">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="939c8-112">Windows PowerShell コマンドレットを使用してダイヤルイン会議アクセス番号を削除する</span><span class="sxs-lookup"><span data-stu-id="939c8-112">Removing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="939c8-113">ダイヤルイン会議アクセス番号は、Windows PowerShell と**get-csdialinconferencingaccessnumber**コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="939c8-113">Dial-in conferencing access numbers can be deleted by using Windows PowerShell and the **Remove-CsDialInConferencingAccessNumber** cmdlet.</span></span> <span data-ttu-id="939c8-114">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="939c8-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="939c8-115">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="939c8-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a><span data-ttu-id="939c8-116">特定のダイヤルイン会議アクセス番号を削除するには</span><span class="sxs-lookup"><span data-stu-id="939c8-116">To remove a specific dial-in conferencing access number</span></span>

  - <span data-ttu-id="939c8-117">次のコマンドは、ID が sip:RedmondDialInAccess@litwareinc.com であるダイヤルイン会議アクセス番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="939c8-117">This command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a><span data-ttu-id="939c8-118">特定の地域に割り当てられているすべてのダイヤルイン会議アクセス番号を削除するには</span><span class="sxs-lookup"><span data-stu-id="939c8-118">To remove all the dial-in conferencing access numbers assigned to a specific region</span></span>

  - <span data-ttu-id="939c8-119">次のコマンドは、Northwest 地域に関連するすべてのダイヤルイン会議アクセス番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="939c8-119">This command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a><span data-ttu-id="939c8-120">プライマリ言語に基づいてダイヤルイン会議アクセス番号を削除するには</span><span class="sxs-lookup"><span data-stu-id="939c8-120">To remove dial-in conferencing access numbers based on primary language</span></span>

  - <span data-ttu-id="939c8-121">このコマンドは、イタリアが第1言語であるすべてのダイヤルイン会議アクセス番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="939c8-121">This command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

<span data-ttu-id="939c8-122">詳細については、 [get-csdialinconferencingaccessnumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="939c8-122">For more information, see the help topic for the [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

