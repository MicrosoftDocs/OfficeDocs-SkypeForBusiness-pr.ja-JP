---
title: 'Lync Server 2013: 更新-アドレス帳管理のための CsAddressBook'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7e10f9d52d9e4090601330cad44d5da03e69540
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="db674-102">Lync Server 2013 でのアドレス帳管理の更新プログラム-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="db674-102">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db674-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="db674-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="db674-104">このコマンドレットを実行できるユーザー: 既定では、次のグループのメンバーは、RTCUniversalUserAdmins、RTCUniversalServerAdmins のように CsAddressBook コマンドレットをローカルで実行することを許可されています。</span><span class="sxs-lookup"><span data-stu-id="db674-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="db674-105">このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) ロールのリストを返すには (自分自身で作成したカスタム RBAC ロールを含む)、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="db674-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="db674-106">CsAddressBook コマンドレットを実行すると、Office Communications Server からの**abserver .exe – syncNow**コマンドが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="db674-106">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server.</span></span> <span data-ttu-id="db674-107">このコマンドレットの目的は、スケジュールされた時間を待つのではなく、直ちに同期を開始することです。</span><span class="sxs-lookup"><span data-stu-id="db674-107">The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time.</span></span> <span data-ttu-id="db674-108">最初の例のコマンドは、組織内のすべてのアドレス帳を更新します。</span><span class="sxs-lookup"><span data-stu-id="db674-108">The first example command updates all Address Books in the organization.</span></span> <span data-ttu-id="db674-109">もう1つは、定義されたサーバーに関連付けられているアドレス帳のみを更新します。</span><span class="sxs-lookup"><span data-stu-id="db674-109">The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db674-110">Lync server 2013 では、Lync Server ユーザーレプリケーターは Active Directory から変更を受け取り、構成された間隔に基づいて Lync Server ユーザーデータベースを更新します。</span><span class="sxs-lookup"><span data-stu-id="db674-110">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="db674-111">Lync Server ユーザーレプリケーターでは、管理者が更新プログラムを実行しなくても、変更内容が RTCab データベースにすばやく反映されます CSAddressBook。</span><span class="sxs-lookup"><span data-stu-id="db674-111">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="db674-112">CSAddressBook を実行するには、アドレス帳ファイルのダウンロードが有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="db674-112">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="db674-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="db674-113">For example:</span></span>

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="db674-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="db674-114">See Also</span></span>


[<span data-ttu-id="db674-115">更新-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="db674-115">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

