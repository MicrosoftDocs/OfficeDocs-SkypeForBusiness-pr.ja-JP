---
title: 'Lync Server 2013: アドレス帳管理の Test-CsAddressBookWebQuery'
description: 'Lync Server 2013: アドレス帳管理用に Test-CsAddressBookWebQuery します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7448733ed1477d36b887648154d66c96f9e6d0b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547443"
---
# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="e5718-103">Lync Server 2013 でのアドレス帳管理の Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="e5718-103">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5718-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e5718-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e5718-105">このコマンドレットを実行できるユーザー: 既定では、次のグループのメンバーが、Test-CsAddressBookWebQuery コマンドレットを実行することを承認されています。 RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="e5718-105">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="e5718-106">このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5718-106">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="e5718-107">Test-CsAddressBookService 代理トランザクションと同様に、Test-CsAddressBookWebQuery は、アドレス帳 Web クエリに対してクエリを実行して、正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5718-107">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly.</span></span> <span data-ttu-id="e5718-108">コマンドレットは、Web チケット認証に接続し、-UserCredential で指定された資格情報を提示します。</span><span class="sxs-lookup"><span data-stu-id="e5718-108">The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential.</span></span> <span data-ttu-id="e5718-109">認証された場合、コマンドレットは– TargetSipAddress 情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="e5718-109">If authenticated, the cmdlet then present the –TargetSipAddress information.</span></span> <span data-ttu-id="e5718-110">このコマンドレットは、連絡先に関する情報を取得できた場合に成功を報告します。</span><span class="sxs-lookup"><span data-stu-id="e5718-110">The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="e5718-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e5718-111">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="e5718-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5718-112">See Also</span></span>


[<span data-ttu-id="e5718-113">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="e5718-113">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

