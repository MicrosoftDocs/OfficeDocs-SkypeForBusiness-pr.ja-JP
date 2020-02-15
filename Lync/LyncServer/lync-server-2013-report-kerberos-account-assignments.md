---
title: 'Lync Server 2013: Kerberos アカウント割り当てのレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c742e6e7e5cedc773e0275700a738afd26a6777d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="63fce-102">Lync Server 2013 での Kerberos アカウント割り当てのレポート</span><span class="sxs-lookup"><span data-stu-id="63fce-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63fce-103">_**トピックの最終更新日:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="63fce-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="63fce-104">この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63fce-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="63fce-105">**Get-CsKerberosAccountAssignment** コマンドレットを使用して、Kerberos 認証アカウントの割り当てに関する情報を照会したり、展開の現在の割り当てに関する情報をレポートしたりできます。</span><span class="sxs-lookup"><span data-stu-id="63fce-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="63fce-106">サイトの Kerberos 認証アカウントの割り当てを照会するには</span><span class="sxs-lookup"><span data-stu-id="63fce-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="63fce-107">RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="63fce-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="63fce-108">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="63fce-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="63fce-109">コマンド ラインで、次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="63fce-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="63fce-110">組織の Kerberos 認証アカウントの割り当てをすべて照会し、それぞれの割り当て情報を戻すには、パラメーターを指定せずにコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="63fce-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="63fce-111">展開の Kerberos 認証アカウントの割り当てをすべて照会し、それぞれのサイト割り当て情報を戻すには、Identity パラメーターを指定してコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="63fce-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="63fce-112">例:</span><span class="sxs-lookup"><span data-stu-id="63fce-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="63fce-113">1 つのサイトの Kerberos 認証アカウントの割り当てをすべて照会し、それぞれの割り当て情報を戻すには、Filter パラメーターを指定してコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="63fce-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="63fce-114">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="63fce-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="63fce-115">Filter パラメーターに \*SiteName を指定すると、指定したサイト名がサイト ID に含まれるすべてのサイトの情報が戻されます (サイト ID に Redmond という文字列が含まれるすべてのサイトなど)。</span><span class="sxs-lookup"><span data-stu-id="63fce-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

