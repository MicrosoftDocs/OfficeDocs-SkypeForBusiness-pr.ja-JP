---
title: 'Lync Server 2013: ドメインの準備'
description: 'Lync Server 2013: ドメインの準備。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7700bbdd10a96949f892858ae03da8de60d86a3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549983"
---
# <a name="preparing-domains-for-lync-server-2013"></a><span data-ttu-id="65867-103">Lync Server 2013 のドメインの準備</span><span class="sxs-lookup"><span data-stu-id="65867-103">Preparing domains for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65867-104">_**トピックの最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="65867-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="65867-105">「ドメインの準備」は、Lync Server 2013 用の Active Directory ドメインサービスを準備するための最後の手順です。</span><span class="sxs-lookup"><span data-stu-id="65867-105">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span> <span data-ttu-id="65867-106">ドメインの準備ステップでは、ドメイン内のユーザーをホストおよび管理するアクセス許可を与えるアクセス制御エントリ (ACE) をユニバーサル グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="65867-106">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="65867-107">ドメインの準備で、ドメイン ルートと 3 つの組み込みコンテナー (ユーザー、コンピューター、およびドメイン コントローラー) に対する ACE が作成されます。</span><span class="sxs-lookup"><span data-stu-id="65867-107">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="65867-108">Lync Server を展開しているドメイン内の任意のコンピューターで、ドメインの準備を実行できます。</span><span class="sxs-lookup"><span data-stu-id="65867-108">You can run domain preparation on any computer in the domain where you are deploying Lync Server.</span></span> <span data-ttu-id="65867-109">Lync Server またはユーザーをホストするすべてのドメインを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65867-109">You must prepare every domain that will host Lync Server or users.</span></span>

<span data-ttu-id="65867-110">組織において、アクセス許可の継承が無効になっているか、認証ユーザーのアクセス許可が無効になっている場合は、ドメインの準備で追加のステップを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65867-110">If permissions inheritance is disabled or authenticated user permissions are disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="65867-111">詳細については、「 [Lync Server 2013 のロックダウンされた Active Directory ドメインサービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65867-111">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

<span data-ttu-id="65867-112">3 つの組み込みコンテナー (Users、Computers、および Domain Controllers) ではなく、組織単位 (OU) を使用している場合は、Authenticated Users グループに OU の読み取りアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65867-112">If your organization uses organizational units (OU) instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the OUs for the Authenticated Users group.</span></span> <span data-ttu-id="65867-113">ドメインの準備には、コンテナーの読み取りアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="65867-113">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="65867-114">Authenticated Users グループに OU の読み取りアクセス許可が付与されていない場合は、次のコード例に示すように、**Grant-CsOuPermission** コマンドレットを実行して各 OU の読み取りアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="65867-114">If the Authenticated Users group does not have read access to the OU, run the **Grant-CsOuPermission** cmdlet as illustrated in the following code examples to grant read permissions for each OU.</span></span>

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

<span data-ttu-id="65867-115">**Grant-CsOuPermission**コマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="65867-115">For details about the **Grant-CsOuPermission** cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div class="">


> [!TIP]  
> <span data-ttu-id="65867-116">ドメインルートと、Users、Computers、Domain Controllers の各コンテナーに作成された Ace の詳細については、「 <A href="lync-server-2013-changes-made-by-domain-preparation.md">Lync Server 2013 のドメインの準備で行われた変更</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65867-116">For details about the ACEs created on the domain root and in the Users, Computers, and Domain Controllers containers, see <A href="lync-server-2013-changes-made-by-domain-preparation.md">Changes made by domain preparation in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="65867-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="65867-117">In This Section</span></span>

  - [<span data-ttu-id="65867-118">Lync Server 2013 のドメインの準備を実行する</span><span class="sxs-lookup"><span data-stu-id="65867-118">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)

  - [<span data-ttu-id="65867-119">Lync Server 2013 のコマンドレットを使用してドメインの準備を元に戻す</span><span class="sxs-lookup"><span data-stu-id="65867-119">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

