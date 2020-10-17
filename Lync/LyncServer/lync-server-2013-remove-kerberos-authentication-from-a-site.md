---
title: 'Lync Server 2013: サイトからの Kerberos 認証の削除'
description: 'Lync Server 2013: サイトから Kerberos 認証を削除します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a3d9100d07d37e98800cfce106bc75fcfaeaa59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553533"
---
# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="61fdd-103">Lync Server 2013 で、サイトから Kerberos 認証を削除する</span><span class="sxs-lookup"><span data-stu-id="61fdd-103">In Lync Server 2013 remove Kerberos authentication from a site</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61fdd-104">_**トピックの最終更新日:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="61fdd-104">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="61fdd-105">この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="61fdd-105">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="61fdd-106">サイトから Kerberos 認証を削除する必要がある場合、またはサイトを廃止する必要がある場合は、 **get-cskerberosaccountassignment** コマンドレットを使用して、サイトから kerberos 認証アカウントの割り当てを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61fdd-106">If you need to remove Kerberos authentication from a site or retire a site, you must remove the Kerberos authentication account assignment from the site by using the **Remove-CsKerberosAccountAssignment** cmdlet.</span></span> <span data-ttu-id="61fdd-107">Kerberos 認証アカウントの割り当てを削除するには、次の手順を使用します。これにより、サイト内のすべてのコンピューターから割り当てが削除されます。</span><span class="sxs-lookup"><span data-stu-id="61fdd-107">Use the following procedure to remove the Kerberos authentication account assignment, which removes the assignment from all computers in the site.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="61fdd-108">Kerberos が有効なアカウントを完全に削除する場合は、割り当てを削除した後、Active directory のユーザーとコンピューターを使用して Active Directory ドメインサービスから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61fdd-108">If you are permanently retiring the Kerberos-enabled account, you should use Active Directory Users and Computers to delete it from Active Directory Domain Services after you have removed the assignment.</span></span> <span data-ttu-id="61fdd-109">オブジェクトを後で使用する場合、Active Directory オブジェクトを保持しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="61fdd-109">If you plan to use the object in the future, you might want to keep the Active Directory object.</span></span>



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="61fdd-110">サイトから Kerberos 認証を削除するには</span><span class="sxs-lookup"><span data-stu-id="61fdd-110">To remove Kerberos authentication from a site</span></span>

1.  <span data-ttu-id="61fdd-111">RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="61fdd-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="61fdd-112">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="61fdd-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="61fdd-113">コマンド ラインで次の 2 つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="61fdd-113">From the command line, run the following two commands:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="61fdd-114">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="61fdd-114">For example:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="61fdd-115">アカウントの追加、アカウントの削除など、Kerberos 認証に変更を加えた後、Lync Server 管理シェルコマンドプロンプトから <STRONG>Enable-CsTopology</STRONG> 設定を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61fdd-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

