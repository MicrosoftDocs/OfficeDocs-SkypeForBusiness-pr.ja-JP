---
title: 'Lync Server 2013: セットアップのアクセス許可の付与'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 014af4f0e03a8d49e3d08c68cff169283bd007bd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="d9a29-102">Lync Server 2013 でのセットアップのアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="d9a29-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9a29-103">_**トピックの最終更新日:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="d9a29-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="d9a29-104">**Grant-CsSetupPermission** コマンドレットを使用して、Read、Write、ReadSPN、および WriteSPN のアクセス許可を特定の Active Directory 組織単位 (OU) の RTCUniversalServerAdmins グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="d9a29-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="d9a29-105">その OU の RTCUniversalServerAdmins グループのメンバーは、Domain Admins グループのメンバーではなく、指定されたドメイン内の Lync Server 2013 を実行しているサーバーをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="d9a29-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="d9a29-106">**Grant-CsSetupPermission** コマンドレットを使用して設定したアクセス許可は、**Test-CsSetupPermission** コマンドレットを使用して確認できます。</span><span class="sxs-lookup"><span data-stu-id="d9a29-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="d9a29-107">**Grant-CsSetupPermission** コマンドレットを使用して付与したアクセス許可は、**Revoke-CsSetupPermission** コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="d9a29-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="d9a29-108">セットアップのアクセス許可を付与するには</span><span class="sxs-lookup"><span data-stu-id="d9a29-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="d9a29-109">セットアップのアクセス許可を付与するドメインで、Lync Server 2013 を実行しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d9a29-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="d9a29-110">OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9a29-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="d9a29-111">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9a29-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d9a29-112">実行</span><span class="sxs-lookup"><span data-stu-id="d9a29-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="d9a29-p103">指定したドメインの既定の名前付けコンテキストに相対的な ComputerOu パラメーターを指定できます (CN=computer など)。または、このパラメーターに完全な OU 識別名 (DN) を指定することもできます ("CN=computers,DC=Contoso,DC=com" など)。後者の場合、指定するドメインに一致する OU DN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a29-p103">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="d9a29-116">Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="d9a29-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="d9a29-117">セットアップのアクセス許可を確認するには</span><span class="sxs-lookup"><span data-stu-id="d9a29-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="d9a29-118">**Grant-CsSetupPermission**コマンドレットを使用して付与したセットアップのアクセス許可を確認するドメイン内の、Lync Server 2013 を実行しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d9a29-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="d9a29-119">OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9a29-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="d9a29-120">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9a29-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d9a29-121">実行</span><span class="sxs-lookup"><span data-stu-id="d9a29-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="d9a29-p105">指定したドメインの既定の名前付けコンテキストに相対的な ComputerOu パラメーターを指定できます (CN=computer など)。または、このパラメーターに完全な OU 識別名 (DN) を指定することもできます ("CN=computers,DC=Contoso,DC=com" など)。後者の場合、指定するドメインに一致する OU DN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a29-p105">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="d9a29-125">Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="d9a29-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="d9a29-126">セットアップのアクセス許可を無効にするには</span><span class="sxs-lookup"><span data-stu-id="d9a29-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="d9a29-127">**グラント-CsSetupPermission**コマンドレットによって付与されたセットアップのアクセス許可を取り消すドメインで、Lync Server 2013 を実行しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d9a29-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="d9a29-128">OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9a29-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="d9a29-129">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9a29-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d9a29-130">実行</span><span class="sxs-lookup"><span data-stu-id="d9a29-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="d9a29-p107">指定したドメインの既定の名前付けコンテキストに相対的な ComputerOu パラメーターを指定できます (CN=computer など)。または、このパラメーターに完全な OU 識別名 (DN) を指定することもできます ("CN=computers,DC=Contoso,DC=com" など)。後者の場合、指定するドメインに一致する OU DN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a29-p107">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="d9a29-134">Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="d9a29-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

