---
title: 'Lync Server 2013: 共通領域電話の連絡先オブジェクトを削除する'
description: 'Lync Server 2013: 共通領域電話の連絡先オブジェクトを削除します。'
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
ms.openlocfilehash: e918f7a46269f70577f28b2c3e55297959430721
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566603"
---
# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="8b101-103">Lync Server 2013 で共通領域電話の連絡先オブジェクトを削除する</span><span class="sxs-lookup"><span data-stu-id="8b101-103">Delete a common area phone Contact object in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b101-104">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="8b101-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="8b101-105">共通領域電話に関連付けられた連絡先オブジェクトを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="8b101-105">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="8b101-106">たとえば、従業員 lounge から電話を削除した場合、その電話に連絡先オブジェクトが関連付けられている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8b101-106">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="8b101-107">**Move-cscommonareaphone**コマンドレットを使用すると、共通領域電話のアカウントを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="8b101-107">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="8b101-108">このコマンドレットを実行すると、 **move-cscommonareaphone**によって返される共通領域電話の一覧から電話が削除されます。</span><span class="sxs-lookup"><span data-stu-id="8b101-108">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="8b101-109">さらに、その電話に関連付けられている連絡先オブジェクトが Active Directory ドメインサービスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="8b101-109">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="8b101-110">**Move-cscommonareaphone**を使用して、1つの共通領域電話または、表示名、国番号、市外局番などの共通要素を持つすべての共通領域電話を削除します。</span><span class="sxs-lookup"><span data-stu-id="8b101-110">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="8b101-111">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="8b101-111">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8b101-112">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b101-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="8b101-113">指定された共通領域電話の削除</span><span class="sxs-lookup"><span data-stu-id="8b101-113">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="8b101-114">次のコマンドは、SIP アドレス sip:mainlobby@litwareinc.com を使用して共通領域電話を削除します。</span><span class="sxs-lookup"><span data-stu-id="8b101-114">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="8b101-115">表示名に基づいて共通領域電話を削除する</span><span class="sxs-lookup"><span data-stu-id="8b101-115">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="8b101-116">このコマンドは、表示名に文字列値 "ビルディング 14" が含まれているすべての共通領域電話を削除します。</span><span class="sxs-lookup"><span data-stu-id="8b101-116">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="8b101-117">国およびエリアコードに基づいて共通領域電話を削除する</span><span class="sxs-lookup"><span data-stu-id="8b101-117">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="8b101-118">このコマンドは、米国 (国コード 1) と市外局番425の共通領域電話をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="8b101-118">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="8b101-119">詳細については、 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b101-119">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8b101-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b101-120">See Also</span></span>


[<span data-ttu-id="8b101-121">Move-cscommonareaphone</span><span class="sxs-lookup"><span data-stu-id="8b101-121">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

