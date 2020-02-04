---
title: Kerberos 認証のテストおよびレポート機能の準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8763203827afd3d14638b68474c4f9bd9d6d0cfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="83538-102">Lync Server 2013 における Kerberos 認証のテストおよびレポート機能の準備</span><span class="sxs-lookup"><span data-stu-id="83538-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83538-103">_**最終更新日:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="83538-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="83538-104">この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83538-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="83538-105">**CsKerberosAccountAssignment** Windows PowerShell コマンドレットを使用して、Kerberos 認証のサイト割り当ての機能の準備をテストして報告することができます。</span><span class="sxs-lookup"><span data-stu-id="83538-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="83538-106">このコマンドは、必須の Identity パラメーターで指定されたサイトを照会します。</span><span class="sxs-lookup"><span data-stu-id="83538-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="83538-107">省略可能なレポートパラメーターを指定すると、コマンドレットは、コマンド\\が実行されているコンピューター上の C: ログに HTML レポートを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="83538-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="83538-108">オプションの Verbose パラメーターは、画面にアクティビティ情報をレポートします。</span><span class="sxs-lookup"><span data-stu-id="83538-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="83538-109">サイトの Kerberos 認証の機能の準備をテストして報告するには</span><span class="sxs-lookup"><span data-stu-id="83538-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="83538-110">RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="83538-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="83538-111">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="83538-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="83538-112">コマンドラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="83538-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="83538-113">例:</span><span class="sxs-lookup"><span data-stu-id="83538-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

