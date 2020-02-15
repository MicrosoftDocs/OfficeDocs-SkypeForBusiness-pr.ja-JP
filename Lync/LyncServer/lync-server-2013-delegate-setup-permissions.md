---
title: 'Lync Server 2013: セットアップのアクセス許可の委任'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 394200b21d3720f288fc89780c6ff193bd278cec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="36f9f-102">Lync Server 2013 でのセットアップのアクセス許可の委任</span><span class="sxs-lookup"><span data-stu-id="36f9f-102">Delegate setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36f9f-103">_**トピックの最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="36f9f-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="36f9f-104">Lync server 2013 を展開しているユーザーまたはグループに domain Admins グループのメンバーシップを付与しない場合は、RTCUniversalServerAdmins グループのメンバーが、lync server 2013 を実行しているサーバーで、 **enable-cstopology** Windows PowerShell コマンドレットを実行できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="36f9f-104">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="36f9f-105">既定では、RTCUniversalServerAdmins グループのメンバーは、このコマンドレットを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="36f9f-105">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="36f9f-106">Lync Server を実行しているサーバーで**Enable-CsTopology**を実行する**ための管理**者権限とアクセス許可を付与するには、lync server 2013 を実行しているサーバーのコンピューターオブジェクトが配置されている組織単位 (OU) を指定します。</span><span class="sxs-lookup"><span data-stu-id="36f9f-106">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="36f9f-107">Lync Server をインストールするときに実行されるドメインの準備では、RTCUniversalServerAdmins グループのメンバーが Enable-CsTopology コマンドレットを実行するためのアクセス許可が自動的に追加されることはありません。</span><span class="sxs-lookup"><span data-stu-id="36f9f-107">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="36f9f-108">つまり、既定では、トポロジを有効にするためにはドメイン管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="36f9f-108">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="36f9f-109">RTCUniversalServerAdmins グループのメンバーにトポロジを有効にする権限を付与するには、Grant-CsSetupPermissions コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36f9f-109">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="36f9f-110">さらに、Lync Server を実行しているコンピューターを格納する各 Active Directory コンテナーに対して、このコマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36f9f-110">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="36f9f-111">このコマンドレットは、RTCUniversalServerAdmins グループのみにアクセス許可を付与する点に留意してください。他のセキュリティ グループまたは個別のユーザーにアクセス許可を付与するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="36f9f-111">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36f9f-112"><STRONG>Enable-CsTopology</STRONG>は、RTCUniversalServerAdmins グループのメンバーが Lync Server 2013 のセットアップと展開を行えるようにするためのキーコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="36f9f-112"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="36f9f-113">RTCUniversalServerAdmins グループに、Enable-CsTopology を実行する権限を追加するには</span><span class="sxs-lookup"><span data-stu-id="36f9f-113">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="36f9f-114">委任されたユーザーが **Enable-CsTopology** を実行する予定のドメインの Domain Admins グループのメンバーとしてサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="36f9f-114">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="36f9f-115">Lync Server 2013 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="36f9f-115">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="36f9f-116">Lync Server 2013 管理シェルは、各フロントエンドサーバーまたは Lync Server 2013 管理ツールがインストールされているすべてのコンピューターに、自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="36f9f-116">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="36f9f-117">Lync Server 2013 管理シェルの詳細については、「操作」のドキュメントの「 [Lync server 2013 Management shell](lync-server-2013-lync-server-management-shell.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36f9f-117">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="36f9f-118">Lync Server 2013 管理シェルから、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="36f9f-118">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="36f9f-119">OU が最上位レベルでない場合は、完全ドメイン名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36f9f-119">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="36f9f-120">次の例では、OU は、contoso.com ドメインにある "Lync Servers" です。</span><span class="sxs-lookup"><span data-stu-id="36f9f-120">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

