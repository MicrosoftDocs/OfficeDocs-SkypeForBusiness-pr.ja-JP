---
title: 'Lync Server 2013: サイトからの Kerberos 認証の削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f030083bc49822f1d41e297388f6ca7dbf66d397
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="841a3-102">Lync Server 2013 でのサイトからの Kerberos 認証の削除</span><span class="sxs-lookup"><span data-stu-id="841a3-102">In Lync Server 2013 remove Kerberos authentication from a site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="841a3-103">_**最終更新日:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="841a3-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="841a3-104">この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="841a3-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="841a3-105">サイトからの Kerberos 認証を削除する必要がある場合、またはサイトを削除する必要がある場合は、 **CsKerberosAccountAssignment**コマンドレットを使用して、サイトから kerberos 認証アカウントの割り当てを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="841a3-105">If you need to remove Kerberos authentication from a site or retire a site, you must remove the Kerberos authentication account assignment from the site by using the **Remove-CsKerberosAccountAssignment** cmdlet.</span></span> <span data-ttu-id="841a3-106">次の手順を使用して、Kerberos 認証アカウントの割り当てを削除します。これにより、サイト内のすべてのコンピューターから課題が削除されます。</span><span class="sxs-lookup"><span data-stu-id="841a3-106">Use the following procedure to remove the Kerberos authentication account assignment, which removes the assignment from all computers in the site.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="841a3-107">Kerberos 対応のアカウントを完全に無効にする場合は、割り当てを削除した後で Active Directory ユーザーとコンピューターを使用して Active Directory ドメインサービスから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="841a3-107">If you are permanently retiring the Kerberos-enabled account, you should use Active Directory Users and Computers to delete it from Active Directory Domain Services after you have removed the assignment.</span></span> <span data-ttu-id="841a3-108">今後このオブジェクトを使う予定がある場合は、Active Directory オブジェクトを保持しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="841a3-108">If you plan to use the object in the future, you might want to keep the Active Directory object.</span></span>



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="841a3-109">サイトから Kerberos 認証を削除するには</span><span class="sxs-lookup"><span data-stu-id="841a3-109">To remove Kerberos authentication from a site</span></span>

1.  <span data-ttu-id="841a3-110">RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="841a3-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="841a3-111">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="841a3-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="841a3-112">コマンドラインで、次の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="841a3-112">From the command line, run the following two commands:</span></span>
    
       ```
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```
        Enable-CsTopology
       ```
    
    <span data-ttu-id="841a3-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="841a3-113">For example:</span></span>
    
       ```
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="841a3-114">アカウントの追加やアカウントの削除など、Kerberos 認証を変更した後は、Lync Server 管理シェルのコマンドプロンプトから、 <STRONG>Enable-CsTopology</STRONG>方法を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="841a3-114">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

