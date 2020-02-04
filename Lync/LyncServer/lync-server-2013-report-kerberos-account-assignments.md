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
ms.openlocfilehash: f4c5a6c118596acd406c3741c4dd2ee780fd381b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="bc35c-102">Lync Server 2013 での Kerberos アカウント割り当てのレポート</span><span class="sxs-lookup"><span data-stu-id="bc35c-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc35c-103">_**最終更新日:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="bc35c-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="bc35c-104">この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc35c-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="bc35c-105">**CsKerberosAccountAssignment**コマンドレットを使用して、Kerberos 認証アカウントの割り当てに関する情報を照会し、展開内の現在の課題に関する情報を報告することができます。</span><span class="sxs-lookup"><span data-stu-id="bc35c-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="bc35c-106">サイトの Kerberos 認証アカウントの割り当てを照会するには</span><span class="sxs-lookup"><span data-stu-id="bc35c-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="bc35c-107">RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bc35c-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="bc35c-108">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc35c-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bc35c-109">コマンドラインで、次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc35c-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="bc35c-110">組織内のすべての Kerberos 認証アカウントの割り当てを照会し、それぞれの割り当て情報を返すには、パラメーターを指定せずにコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc35c-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="bc35c-111">展開ですべての Kerberos 認証アカウントの割り当てを照会し、それぞれのサイト割り当て情報を返すには、Identity パラメーターを指定してコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc35c-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="bc35c-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bc35c-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="bc35c-113">1つのサイトですべての Kerberos 認証アカウントの割り当てを照会し、それぞれの割り当て情報を返すには、Filter パラメーターを指定してコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc35c-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="bc35c-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bc35c-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bc35c-115">\* SiteName を Filter パラメーターとして指定すると、指定したサイト名を含むすべてのサイトに関する情報 (サイト識別子に Redmond という文字列が含まれるすべてのサイトなど) が返されます。</span><span class="sxs-lookup"><span data-stu-id="bc35c-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

