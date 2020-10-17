---
title: Kerberos 認証のテストおよびレポート機能の準備
description: Kerberos 認証のテストおよびレポート機能の準備。
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
ms.openlocfilehash: 5d32591a8cced7dce2e0bb78cc26189dce1900a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554063"
---
# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="86da9-103">Lync Server 2013 での Kerberos 認証のテストおよびレポート機能の準備</span><span class="sxs-lookup"><span data-stu-id="86da9-103">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86da9-104">_**トピックの最終更新日:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="86da9-104">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="86da9-105">この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="86da9-105">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="86da9-106">**Get-cskerberosaccountassignment**   Windows PowerShell コマンドレットを使用して、Kerberos 認証のサイト割り当ての機能の準備状況をテストおよび報告できます。</span><span class="sxs-lookup"><span data-stu-id="86da9-106">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="86da9-107">このコマンドは、必須の Identity パラメーターで指定されているサイトを照会します。</span><span class="sxs-lookup"><span data-stu-id="86da9-107">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="86da9-108">オプションの Report パラメーターを指定すると、コマンドレットは、 \\ コマンドが実行されているコンピューター上の C: ログに HTML レポートを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="86da9-108">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="86da9-109">オプションの Verbose パラメーターを指定すると、アクティビティ情報が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="86da9-109">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="86da9-110">サイトで Kerberos 認証を使用する機能的な準備ができていることをテストおよび報告するには</span><span class="sxs-lookup"><span data-stu-id="86da9-110">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="86da9-111">RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="86da9-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="86da9-112">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="86da9-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="86da9-113">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="86da9-113">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="86da9-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="86da9-114">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

