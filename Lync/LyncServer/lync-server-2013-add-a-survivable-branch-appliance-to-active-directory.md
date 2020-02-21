---
title: 'Lync Server 2013: 存続可能 Branch Appliance を Active Directory に追加する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25d8efb03b4d67b6409f93b6a99d2314cb703952
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="7873c-102">Lync Server 2013 で存続可能 Branch Appliance を Active Directory に追加する</span><span class="sxs-lookup"><span data-stu-id="7873c-102">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7873c-103">_**トピックの最終更新日:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="7873c-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="7873c-104">存続可能ブランチアプライアンスを展開することを計画している場合は、存続可能 Branch Appliance を Active Directory ドメインサービスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7873c-104">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="7873c-105">中央サイトでこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7873c-105">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7873c-106">この手順は、存続可能ブランチアプライアンスを展開している場合にのみ実行してください。</span><span class="sxs-lookup"><span data-stu-id="7873c-106">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="7873c-107">存続可能ブランチサーバーを展開している場合は、この操作を実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="7873c-107">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="7873c-108">存続可能ブランチ アプライアンスを Active Directory ドメイン サービスに追加するには</span><span class="sxs-lookup"><span data-stu-id="7873c-108">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="7873c-109">Enterprise Admins グループのメンバーとしてメンバー サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7873c-109">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="7873c-110">[**スタート**]、[**管理ツール**]、[**Active Directory ユーザーとコンピューター**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="7873c-110">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="7873c-111">[**操作**] メニューの [**新規**] をクリックし、[**コンピューター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7873c-111">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="7873c-112">[**新しいオブジェクト-コンピューター** ] ダイアログボックスで、存続可能 Branch Appliance のコンピューターオブジェクトの名前 (たとえば、BranchOffice1) を入力し、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7873c-112">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="7873c-113">[**ユーザーまたはグループの選択**] ダイアログ ボックスで、RTCUniversalSBATechnicians グループを追加して [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7873c-113">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7873c-114">ブランチ サイトの RTCUniversalSBATechnicians グループのメンバーが、後でこのデバイスをドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="7873c-114">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="7873c-115">[ **OK]** をクリックして、存続可能 Branch Appliance コンピューターオブジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="7873c-115">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="7873c-116">[**スタート**]、[**管理ツール**]、[**ADSI Edit**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="7873c-116">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="7873c-117">[**ADSI Edit**] で、前のステップで作成したコンピューター オブジェクトを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7873c-117">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="7873c-118">属性リストで **servicePrincipalName** をクリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7873c-118">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="7873c-119">[**追加する値**] フィールドに「HOST/\<SBA FQDN\> 」 \<と入力\>します。 SBA fqdn は、存続可能 Branch Appliance の完全修飾ドメイン名 (fqdn) です。</span><span class="sxs-lookup"><span data-stu-id="7873c-119">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="7873c-120">たとえば、「 **HOST/BranchOffice1**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="7873c-120">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="7873c-121">[**OK**] をクリックして **servicePrincipalName** 属性の設定を保存し、[**OK**] をクリックしてコンピューター オブジェクトのプロパティを保存します。</span><span class="sxs-lookup"><span data-stu-id="7873c-121">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="7873c-122">[**Active Directory ユーザーとコンピューター**] で [**ユーザー**] を右クリックし、[**新規作成**] をクリックして [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7873c-122">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="7873c-123">ウィザードに情報を入力して、存続可能 Branch Appliance 技術者のドメインユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="7873c-123">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="7873c-124">[**Active Directory ユーザーとコンピューター**] で [**ユーザー**] をクリックし、ユーザー オブジェクトを右クリックして [**グループに追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7873c-124">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="7873c-125">[**選択するオブジェクト名を入力してください**] に **RTCUniversalSBATechnicians** と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7873c-125">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="7873c-126">ブランチ サイト技術者ごとに、ステップ 12 ～ 15 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7873c-126">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="7873c-127">**次のステップ**: [Lync Server 2013 でのトポロジへのブランチサイトの追加](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="7873c-127">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

