---
title: 'Lync Server 2013: セットアップ アクセス許可の付与'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 751ec9ba024780344596bfc0513c15f7e9eafec7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="ab269-102">Lync Server 2013 でのセットアップ アクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="ab269-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab269-103">_**最終更新日:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="ab269-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="ab269-104">WriteSPN アクセス許可コマンド\*\*\*\* レットを使用して、指定した Active Directory 組織単位 (OU) の RTCUniversalServerAdmins グループに読み取り、書き込み、readspn、およびのアクセス許可を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="ab269-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="ab269-105">その後、その OU の RTCUniversalServerAdmins グループのメンバーは、ドメイン管理者グループのメンバーにならずに、指定したドメインで Lync Server 2013 を実行しているサーバーをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ab269-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="ab269-106">Cssetuppermission コマンドレットを使用して、設定したアクセス許可を確認します。これには、**グラント Setuppermission**コマンドレットを使用します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ab269-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="ab269-107">無効にした場合は、 **Revoke setuppermissions**コマンドレットを使用して、**付与**したアクセス許可を削除できます。</span><span class="sxs-lookup"><span data-stu-id="ab269-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="ab269-108">セットアップのアクセス許可を付与するには</span><span class="sxs-lookup"><span data-stu-id="ab269-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="ab269-109">セットアップのアクセス許可を付与するドメインの、Lync Server 2013 を実行しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ab269-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="ab269-110">OU が別の子ドメインにある場合は、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab269-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="ab269-111">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab269-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ab269-112">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab269-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="ab269-113">指定したドメインの既定の名前付けコンテキスト (たとえば、CN = computers) を基準として、ComputerOu パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ab269-113">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="ab269-114">または、このパラメーターを完全な OU 識別名 (DN) として指定することもできます (たとえば、"CN = computers, DC = Contoso, DC = com")。</span><span class="sxs-lookup"><span data-stu-id="ab269-114">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="ab269-115">後者の場合、指定したドメインと一貫性のある OU DN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab269-115">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="ab269-116">Domain パラメーターを指定しない場合、既定値はローカルドメインです。</span><span class="sxs-lookup"><span data-stu-id="ab269-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="ab269-117">セットアップのアクセス許可を確認するには</span><span class="sxs-lookup"><span data-stu-id="ab269-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="ab269-118">アクセス許可を**付与**したドメイン内の Lync Server 2013 を実行しているコンピューターにログオンします。このコマンドレットを使用して、付与したセットアップのアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="ab269-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="ab269-119">OU が別の子ドメインにある場合は、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab269-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="ab269-120">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab269-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ab269-121">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab269-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="ab269-122">指定したドメインの既定の名前付けコンテキスト (たとえば、CN = computers) を基準として、ComputerOu パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ab269-122">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="ab269-123">または、このパラメーターを完全な OU 識別名 (DN) として指定することもできます (たとえば、"CN = computers, DC = Contoso, DC = com")。</span><span class="sxs-lookup"><span data-stu-id="ab269-123">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="ab269-124">後者の場合、指定したドメインと一貫性のある OU DN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab269-124">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="ab269-125">Domain パラメーターを指定しない場合、既定値はローカルドメインです。</span><span class="sxs-lookup"><span data-stu-id="ab269-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="ab269-126">セットアップのアクセス許可を取り消すには</span><span class="sxs-lookup"><span data-stu-id="ab269-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="ab269-127">**グラント Setuppermission**コマンドレットによって付与されたセットアップのアクセス許可を取り消すドメインで、Lync Server 2013 を実行しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ab269-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="ab269-128">OU が別の子ドメインにある場合は、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab269-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="ab269-129">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab269-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ab269-130">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab269-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="ab269-131">指定したドメインの既定の名前付けコンテキスト (たとえば、CN = computers) を基準として、ComputerOu パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ab269-131">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="ab269-132">または、このパラメーターを完全な OU 識別名 (DN) として指定することもできます (たとえば、"CN = computers, DC = Contoso, DC = com")。</span><span class="sxs-lookup"><span data-stu-id="ab269-132">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="ab269-133">後者の場合、指定したドメインと一貫性のある OU DN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab269-133">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="ab269-134">Domain パラメーターを指定しない場合、既定値はローカルドメインです。</span><span class="sxs-lookup"><span data-stu-id="ab269-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

