---
title: 'Lync Server 2013: Active Directory への存続可能ブランチ アプライアンスの追加'
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
ms.openlocfilehash: 8712dcb5b68522a8b770aac63c5a37a1a70a669a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="59398-102">Lync Server 2013 での、Active Directory への存続可能ブランチ アプライアンスの追加</span><span class="sxs-lookup"><span data-stu-id="59398-102">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59398-103">_**最終更新日:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="59398-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="59398-104">Survivable Branch Appliance の展開を計画している場合は、Survivable Branch Appliance を Active Directory ドメインサービスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59398-104">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="59398-105">セントラルサイトでこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="59398-105">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="59398-106">この手順は、Survivable Branch Appliance を展開している場合にのみ実行してください。</span><span class="sxs-lookup"><span data-stu-id="59398-106">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="59398-107">Survivable ブランチサーバーを展開する場合は、この操作を行わないでください。</span><span class="sxs-lookup"><span data-stu-id="59398-107">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="59398-108">Active Directory ドメインサービスに Survivable Branch アプライアンスを追加するには</span><span class="sxs-lookup"><span data-stu-id="59398-108">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="59398-109">Enterprise Admins グループのメンバーとしてメンバーサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="59398-109">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="59398-110">[**スタート**] をクリックし、[**管理ツール**] をクリックして、[ **Active Directory ユーザーとコンピューター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59398-110">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="59398-111">[**操作**] メニューの [**新規作成**] をクリックし、[**コンピューター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59398-111">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="59398-112">[**新しいオブジェクト-コンピューター** ] ダイアログボックスで、Survivable Branch アプライアンスのコンピューターオブジェクトの名前 (たとえば BranchOffice1) を入力し、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59398-112">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="59398-113">**[ユーザーまたはグループの選択**] ダイアログボックスで、RTCUniversalSBATechnicians グループを追加し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59398-113">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59398-114">ブランチサイトの RTCUniversalSBATechnicians グループのメンバーは、このデバイスを後でドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="59398-114">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="59398-115">[ **OK** ] をクリックして、Survivable Branch Appliance コンピューターオブジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="59398-115">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="59398-116">[**スタート**] をクリックし、[**管理ツール**] をクリックして、[ **ADSI の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59398-116">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="59398-117">**ADSI edit**で、前の手順で作成したコンピューターオブジェクトを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59398-117">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="59398-118">[属性] の一覧で、[ **servicePrincipalName**] をクリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59398-118">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="59398-119">[**追加する値**] フィールドに、「HOST\</SBA\> fqdn \<」と\>入力します。 SBA fqdn は Survivable Branch Appliance の完全修飾ドメイン名 (FQDN) です。</span><span class="sxs-lookup"><span data-stu-id="59398-119">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="59398-120">たとえば、「 **HOST/BranchOffice1**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="59398-120">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="59398-121">[ **Ok** ] をクリックして**servicePrincipalName**属性の設定を保存してから、[ **ok** ] をクリックして、コンピューターオブジェクトのプロパティを保存します。</span><span class="sxs-lookup"><span data-stu-id="59398-121">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="59398-122">**Active Directory ユーザーとコンピューター**で、[**ユーザー**] を右クリックし、[**新規作成**] をクリックして、[**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59398-122">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="59398-123">ウィザードに情報を入力して、Survivable Branch Appliance テクニシャンのドメインユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="59398-123">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="59398-124">[ **Active Directory ユーザーとコンピューター**] で [**ユーザー**] をクリックし、ユーザーオブジェクトを右クリックして、[**グループに追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59398-124">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="59398-125">**[選択するオブジェクト名を入力**してください] に「 **RTCUniversalSBATechnicians**」と入力して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59398-125">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="59398-126">ブランチサイトの技術ごとに、手順12-15 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="59398-126">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="59398-127">**次のステップ**: [Lync Server 2013 でトポロジにブランチサイトを追加する](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="59398-127">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

