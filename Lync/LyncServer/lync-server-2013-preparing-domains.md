---
title: 'Lync Server 2013: ドメインの準備'
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
ms.openlocfilehash: 20a6897ae45964f3f179e951916dfb6bf7180641
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a><span data-ttu-id="857d4-102">Lync Server 2013 のドメインの準備</span><span class="sxs-lookup"><span data-stu-id="857d4-102">Preparing domains for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="857d4-103">_**最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="857d4-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="857d4-104">ドメインの準備は、Lync Server 2013 用の Active Directory ドメインサービスの準備での最終的な手順です。</span><span class="sxs-lookup"><span data-stu-id="857d4-104">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span> <span data-ttu-id="857d4-105">ドメインの準備ステップでは、ドメイン内のユーザーをホストおよび管理するアクセス許可を与えるアクセス制御エントリ (ACE) をユニバーサル グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="857d4-105">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="857d4-106">ドメインの準備で、ドメイン ルートと 3 つの組み込みコンテナー (ユーザー、コンピューター、およびドメイン コントローラー) に対する ACE が作成されます。</span><span class="sxs-lookup"><span data-stu-id="857d4-106">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="857d4-107">ドメインの準備は、Lync Server を展開しているドメイン内の任意のコンピューターで実行できます。</span><span class="sxs-lookup"><span data-stu-id="857d4-107">You can run domain preparation on any computer in the domain where you are deploying Lync Server.</span></span> <span data-ttu-id="857d4-108">Lync サーバーまたはユーザーをホストするすべてのドメインを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="857d4-108">You must prepare every domain that will host Lync Server or users.</span></span>

<span data-ttu-id="857d4-109">権限の継承が無効になっているか、認証されたユーザー権限が組織で無効になっている場合は、ドメインの準備中に追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="857d4-109">If permissions inheritance is disabled or authenticated user permissions are disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="857d4-110">詳細については、「 [Lync Server 2013 のロックダウン Active Directory ドメインサービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="857d4-110">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

<span data-ttu-id="857d4-111">組織で、3つの組み込みコンテナー (ユーザー、コンピューター、ドメインコントローラー) ではなく組織単位 (OU) を使用している場合は、認証されたユーザーグループの Ou への読み取りアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="857d4-111">If your organization uses organizational units (OU) instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the OUs for the Authenticated Users group.</span></span> <span data-ttu-id="857d4-112">ドメインの準備には、コンテナーへの読み取りアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="857d4-112">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="857d4-113">認証されたユーザーグループが OU への読み取りアクセス権を持っていない場合は、次のコード例に示すように**Grant Grant Oupermission**コマンドレットを実行して、各 ou の読み取りアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="857d4-113">If the Authenticated Users group does not have read access to the OU, run the **Grant-CsOuPermission** cmdlet as illustrated in the following code examples to grant read permissions for each OU.</span></span>

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

<span data-ttu-id="857d4-114">**Grant-CsOuPermission**コマンドレットの詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="857d4-114">For details about the **Grant-CsOuPermission** cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div class="">


> [!TIP]  
> <span data-ttu-id="857d4-115">ドメインルートで作成された Ace と、[ユーザー]、[コンピューター]、[ドメインコントローラー] の各コンテナーについて詳しくは、「 <A href="lync-server-2013-changes-made-by-domain-preparation.md">Lync Server 2013 でのドメインの準備によって行われた変更</A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="857d4-115">For details about the ACEs created on the domain root and in the Users, Computers, and Domain Controllers containers, see <A href="lync-server-2013-changes-made-by-domain-preparation.md">Changes made by domain preparation in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="857d4-116">このセクション中</span><span class="sxs-lookup"><span data-stu-id="857d4-116">In This Section</span></span>

  - [<span data-ttu-id="857d4-117">Lync Server 2013 のドメイン準備手続き</span><span class="sxs-lookup"><span data-stu-id="857d4-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)

  - [<span data-ttu-id="857d4-118">Lync Server 2013 のコマンドレットの使用によるドメインの準備の無効化</span><span class="sxs-lookup"><span data-stu-id="857d4-118">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

