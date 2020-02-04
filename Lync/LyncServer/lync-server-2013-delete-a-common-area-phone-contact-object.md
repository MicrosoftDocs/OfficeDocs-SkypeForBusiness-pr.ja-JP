---
title: 'Lync Server 2013: 一般的なエリア電話の連絡先オブジェクトを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a3088150c882a5ebca99318f7c85ddbddddc333
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="dc05d-102">Lync Server 2013 で一般的なエリア電話の連絡先オブジェクトを削除する</span><span class="sxs-lookup"><span data-stu-id="dc05d-102">Delete a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc05d-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="dc05d-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="dc05d-104">一般的な市外局番に関連付けられた連絡先オブジェクトを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="dc05d-104">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="dc05d-105">たとえば、従業員 lounge から電話を削除した場合、その電話に連絡先オブジェクトを関連付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dc05d-105">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="dc05d-106">**CsCommonAreaPhone**コマンドレットを使用すると、一般的な市外局番のアカウントを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="dc05d-106">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="dc05d-107">このコマンドレットを実行すると、 **CsCommonAreaPhone**によって返される一般的なエリアの携帯電話の一覧から電話が削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc05d-107">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="dc05d-108">さらに、その電話に関連付けられている連絡先オブジェクトが Active Directory ドメインサービスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc05d-108">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="dc05d-109">共通の市外局番を1つ、または、表示名や国番号、市外局番などの共通の市外局番を持つ携帯電話のいずれかを削除するには、 **CsCommonAreaPhone**を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc05d-109">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="dc05d-110">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="dc05d-110">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dc05d-111">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc05d-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="dc05d-112">指定した共通の市外局番を削除する</span><span class="sxs-lookup"><span data-stu-id="dc05d-112">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="dc05d-113">次のコマンドは、SIP アドレス sip:mainlobby@litwareinc.com を持つ一般的なエリアの電話を削除します。</span><span class="sxs-lookup"><span data-stu-id="dc05d-113">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="dc05d-114">表示名に基づいて一般的なエリア電話を削除する</span><span class="sxs-lookup"><span data-stu-id="dc05d-114">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="dc05d-115">このコマンドは、表示名に "建物 14" という文字列値が含まれているすべての共通領域の電話を削除します。</span><span class="sxs-lookup"><span data-stu-id="dc05d-115">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="dc05d-116">国と市外局番に基づいて一般的なエリア電話を削除する</span><span class="sxs-lookup"><span data-stu-id="dc05d-116">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="dc05d-117">このコマンドを実行すると、米国 (国コード 1) と市外局番425の一般的な市外局番がすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc05d-117">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="dc05d-118">詳細については、 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc05d-118">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dc05d-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc05d-119">See Also</span></span>


[<span data-ttu-id="dc05d-120">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="dc05d-120">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

