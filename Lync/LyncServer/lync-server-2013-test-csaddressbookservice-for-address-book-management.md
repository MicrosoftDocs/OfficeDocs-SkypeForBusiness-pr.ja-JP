---
title: 'Lync Server 2013: テスト-CsAddressBookService for Address Book の管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test-CsAddressBookService for Address Book management
ms:assetid: b88cea74-41fd-4c0e-9284-7135bff27a27
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429720(v=OCS.15)
ms:contentKeyID: 48185206
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 120a61ff03957a25cb7e6e0d09b8d3bccb11343c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="5676f-102">Lync Server 2013 でのアドレス帳管理用のテスト-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="5676f-102">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5676f-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5676f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5676f-104">このコマンドレットを実行できるユーザー: 既定では、次のグループのメンバーには、RTCUniversalServerAdmins のテストを実行する権限が与えられます。</span><span class="sxs-lookup"><span data-stu-id="5676f-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookService cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="5676f-105">このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) ロールのリストを返すには (自分自身で作成したカスタム RBAC ロールを含む)、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5676f-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="5676f-106">Lync Server 2013 には、特定の機能が正常に動作していることを確認するために、合成コマンドを開始する多数のコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5676f-106">Lync Server 2013 contains a number of cmdlets that initiate synthetic commands to confirm that a specific function or feature is working properly.</span></span> <span data-ttu-id="5676f-107">テスト-CsAddressBookService は、定義されたユーザーが、アドレス帳 Web サービスからローカルファイルに接続して要求できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5676f-107">Test-CsAddressBookService confirms that a defined user can connect and request the local files from the Address Book Web service.</span></span>

<span data-ttu-id="5676f-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5676f-108">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="5676f-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="5676f-109">See Also</span></span>


[<span data-ttu-id="5676f-110">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="5676f-110">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

