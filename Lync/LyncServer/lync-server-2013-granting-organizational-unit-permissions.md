---
title: 'Lync Server 2013: 組織単位アクセス許可の付与'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85c43cb727b83b06d6427e2bf3b6027d78dc025e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="82bb4-102">Lync Server 2013 での組織単位アクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="82bb4-102">Granting organizational unit permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82bb4-103">_**トピックの最終更新日:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="82bb4-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="82bb4-104">**付与-CsOuPermission**コマンドレットを使用して、フォレストの準備によって作成された RTC ユニバーサルグループのメンバーが Domain Admins グループのメンバーでない場合にアクセスできるように、指定された組織単位 (ou) 内のオブジェクトにアクセス許可を付与できます。</span><span class="sxs-lookup"><span data-stu-id="82bb4-104">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="82bb4-105">指定された OU に追加されるアクセス許可は、ドメインの準備中に、[有効にする] **-CsAdDomain**コマンドレットによってコンピューターとユーザーコンテナーに追加されるアクセス許可と同じです。</span><span class="sxs-lookup"><span data-stu-id="82bb4-105">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="82bb4-106">Permissions **-CsOuPermission**コマンドレットを使用して、設定したアクセス許可を確認するには、 **Test-csoupermission**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="82bb4-106">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="82bb4-107">**Revoke-CsOuPermission**コマンドレットを使用して、 **Grant-csoupermission**コマンドレットを使用して付与したアクセス許可を削除できます。</span><span class="sxs-lookup"><span data-stu-id="82bb4-107">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="82bb4-108">OU アクセス許可を付与するには</span><span class="sxs-lookup"><span data-stu-id="82bb4-108">To grant OU permissions</span></span>

1.  <span data-ttu-id="82bb4-109">OU アクセス許可を付与するドメインで、Lync Server 2013 を実行しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="82bb4-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="82bb4-110">OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="82bb4-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="82bb4-111">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="82bb4-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="82bb4-112">実行</span><span class="sxs-lookup"><span data-stu-id="82bb4-112">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="82bb4-113">Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="82bb4-113">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="82bb4-114">OU アクセス許可を確認するには</span><span class="sxs-lookup"><span data-stu-id="82bb4-114">To verify OU permissions</span></span>

1.  <span data-ttu-id="82bb4-115">**グラント-CsOuPermission**コマンドレットを使用して付与した OU アクセス許可を確認するドメイン内の、Lync Server 2013 を実行しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="82bb4-115">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="82bb4-116">OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="82bb4-116">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="82bb4-117">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="82bb4-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="82bb4-118">実行</span><span class="sxs-lookup"><span data-stu-id="82bb4-118">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="82bb4-119">Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="82bb4-119">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="82bb4-120">OU アクセス許可を無効にするには</span><span class="sxs-lookup"><span data-stu-id="82bb4-120">To revoke OU permissions</span></span>

1.  <span data-ttu-id="82bb4-121">**グラント-CsOuPermission**コマンドレットによって付与された OU アクセス許可を取り消すドメインで、Lync Server 2013 を実行しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="82bb4-121">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="82bb4-122">OU が別の子ドメインに存在する場合、Domain Admins グループまたは Enterprise Admins グループのメンバーであるアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="82bb4-122">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="82bb4-123">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="82bb4-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="82bb4-124">実行</span><span class="sxs-lookup"><span data-stu-id="82bb4-124">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="82bb4-125">Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="82bb4-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

