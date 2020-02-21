---
title: 'Lync Server 2013: Update-csaddressbook のアドレス帳管理用の更新プログラム'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 745e636cc4bac682beaf2ea308cd465c3d194df7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="77610-102">Update-csaddressbook Lync Server 2013 でのアドレス帳管理のための更新プログラム</span><span class="sxs-lookup"><span data-stu-id="77610-102">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77610-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="77610-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="77610-p101">このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが、Update-CsAddressBook コマンドレットをローカルで実行することを承認されています。 RTCUniversalUserAdmins、RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="77610-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="77610-p102">Update-CsAddressBook コマンドレットは、Office Communications Server の **abserver.exe –syncNow** コマンドの代わりに使用されます。 このコマンドレットの目的は、スケジュールされた時間を待機することなくすぐに同期を開始することです。 最初の例のコマンドは、組織のすべてのアドレス帳を更新します。 2 番目のコマンドは、定義されたサーバーに関連付けられたアドレス帳だけを更新します。</span><span class="sxs-lookup"><span data-stu-id="77610-p102">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server. The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time. The first example command updates all Address Books in the organization. The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77610-110">Lync Server 2013 の Lync Server ユーザーレプリケーターは、Active Directory から変更を取得し、構成された間隔に基づいて Lync Server ユーザーデータベースを更新します。</span><span class="sxs-lookup"><span data-stu-id="77610-110">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="77610-111">Lync Server ユーザーレプリケーターでは、管理者が Update-csaddressbook を実行しなくても、変更内容が RTCab データベースに迅速に伝達されます。</span><span class="sxs-lookup"><span data-stu-id="77610-111">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="77610-112">アドレス帳ファイルのダウンロードが有効になっている場合にのみ、管理者は Update-csaddressbook を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77610-112">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="77610-113">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="77610-113">For example:</span></span>

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="77610-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="77610-114">See Also</span></span>


[<span data-ttu-id="77610-115">Update-csaddressbook</span><span class="sxs-lookup"><span data-stu-id="77610-115">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

