---
title: 'Lync Server 2013: hot desking を有効または無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c56d7ae13be9afa3af7e4732242a86f4be4c458
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a><span data-ttu-id="96c61-102">Lync Server 2013 でホット desking を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="96c61-102">Enable or disable hot desking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96c61-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="96c61-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="96c61-104">一般的な市外電話は、*ホット卓上電話*として設定できます。</span><span class="sxs-lookup"><span data-stu-id="96c61-104">You can set up common area phones as *hot-desk phones*.</span></span> <span data-ttu-id="96c61-105">ホットデスク電話では、ユーザーは自分のユーザーアカウントにログオンして、ログオンした後、Lync Server の機能と自分のユーザープロファイル設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="96c61-105">With hot-desk phones, users can log on to their own user account, and, after they are logged on, use Lync Server features and their own user profile settings.</span></span> <span data-ttu-id="96c61-106">ホット desking は、クライアントポリシーを使用して管理されます。ホット desking を有効または無効にするには、一般的なエリアの電話で使用されるクライアントポリシーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c61-106">Hot desking is managed by using client policies: to enable or disable hot desking, you need to modify the client policies that are used by your common area phones.</span></span> <span data-ttu-id="96c61-107">共通のエリア電話に割り当てられている会議ポリシーを確認する方法の詳細については、「 [Lync Server 2013 で一般的な市外局番の情報を表示](lync-server-2013-view-common-area-phone-information.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c61-107">For details about how to determine the conferencing policies that have been assigned to your common area phones, see [View common area phone information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span></span>

<span data-ttu-id="96c61-108">電話のホット desキングを有効または無効にするには、**新しい-CSClientPolicy**コマンドレットの Enablehot desキングパラメーターを使用します。または、次のように**設定**します。</span><span class="sxs-lookup"><span data-stu-id="96c61-108">You use the EnableHotdesking parameter of the **New-CSClientPolicy** cmdlet or the **Set-CSClientPolicy** cmdlet to enable or disable hot desking on a phone, as follows.</span></span> <span data-ttu-id="96c61-109">これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行します。</span><span class="sxs-lookup"><span data-stu-id="96c61-109">Run these cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="96c61-110">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c61-110">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="enabling-hot-desking"></a><span data-ttu-id="96c61-111">ホット desking の有効化</span><span class="sxs-lookup"><span data-stu-id="96c61-111">Enabling hot desking</span></span>

  - <span data-ttu-id="96c61-112">共通の市外局番に対してホット desking を有効にするには、その電話 (または電話の集合) に割り当てられているクライアントポリシーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c61-112">To enable hot desking for a common area phone, you must modify the client policy that has been assigned to that phone (or collection of phones).</span></span>
    
    <span data-ttu-id="96c61-113">変更する必要があるポリシーを特定した後、次の手順では、 **Set-CsClientPolicy**コマンドレットを使用して、Enableホット desキングパラメーターを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="96c61-113">After you have identified the policy that needs to be modified, the next step is to use the **Set-CsClientPolicy** cmdlet to set the EnableHotdesking parameter to True.</span></span> <span data-ttu-id="96c61-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="96c61-114">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - <span data-ttu-id="96c61-115">または、**新しい-CsClientPolicy**コマンドレットを使用して、ホット desking を有効にする新しいクライアントポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="96c61-115">Alternatively, you can use the **New-CsClientPolicy** cmdlet to create a new client policy that enables hot desking.</span></span> <span data-ttu-id="96c61-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="96c61-116">For example:</span></span>
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="96c61-117">このポリシーを作成したら、適切な共通エリアの電話に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c61-117">After this policy has been created, you must assign it to the appropriate common area phones.</span></span> <span data-ttu-id="96c61-118">詳細については、「 <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Lync Server 2013 で共通の市外局番にポリシーを割り当てる</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c61-118">For details, see <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Assign policies in Lync Server 2013 to a common area phone</A>.</span></span>



</div>

<div>

## <a name="disabling-hot-desking"></a><span data-ttu-id="96c61-119">ホット desking の無効化</span><span class="sxs-lookup"><span data-stu-id="96c61-119">Disabling hot desking</span></span>

  - <span data-ttu-id="96c61-120">一般的な市外電話のホット desking を無効にするには、 **Set-CsClientPolicy**コマンドレットの Enablehot desking パラメーターを既定値の False にリセットします。</span><span class="sxs-lookup"><span data-stu-id="96c61-120">To disable hot desking for a common area phone, reset the EnableHotdesking parameter of the **Set-CsClientPolicy** cmdlet to the default value of False.</span></span> <span data-ttu-id="96c61-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="96c61-121">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

<span data-ttu-id="96c61-122">詳細については、「[新しい-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)コマンドレット」および「 [csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c61-122">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

