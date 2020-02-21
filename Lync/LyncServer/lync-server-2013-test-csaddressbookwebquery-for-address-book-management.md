---
title: 'Lync Server 2013: アドレス帳管理用のテスト-CsAddressBookWebQuery'
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
ms.openlocfilehash: f5f03ead82f4ec5ebcb09c3bbfa1bba6206b8333
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="3f389-102">Lync Server 2013 でのアドレス帳管理用のテスト-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="3f389-102">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f389-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3f389-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3f389-104">このコマンドレットを実行できるユーザー: 既定では、次のグループのメンバーが、RTCUniversalServerAdmins コマンドレットの実行を承認されています。</span><span class="sxs-lookup"><span data-stu-id="3f389-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="3f389-105">このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3f389-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="3f389-106">Test-CsAddressBookWebQuery と同様に、Test-CsAddressBookWebQuery は、アドレス帳 Web クエリに対してクエリを実行して、正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3f389-106">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly.</span></span> <span data-ttu-id="3f389-107">コマンドレットは、Web チケット認証に接続し、-UserCredential で指定された資格情報を提示します。</span><span class="sxs-lookup"><span data-stu-id="3f389-107">The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential.</span></span> <span data-ttu-id="3f389-108">認証された場合、コマンドレットは– TargetSipAddress 情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="3f389-108">If authenticated, the cmdlet then present the –TargetSipAddress information.</span></span> <span data-ttu-id="3f389-109">このコマンドレットは、連絡先に関する情報を取得できた場合に成功を報告します。</span><span class="sxs-lookup"><span data-stu-id="3f389-109">The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="3f389-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3f389-110">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="3f389-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f389-111">See Also</span></span>


[<span data-ttu-id="3f389-112">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="3f389-112">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

