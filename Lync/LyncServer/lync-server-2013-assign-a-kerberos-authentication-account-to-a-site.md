---
title: 'Lync Server 2013: サイトへの Kerberos 認証アカウントの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c706f9fdd8932456a9f1617e55dc9231dbd6a84
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="ecc30-102">Lync Server 2013 での、サイトへの Kerberos 認証アカウントの割り当て</span><span class="sxs-lookup"><span data-stu-id="ecc30-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecc30-103">_**最終更新日:** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="ecc30-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="ecc30-104">この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecc30-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="ecc30-105">Kerberos アカウントを作成したら、それをサイトに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecc30-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="ecc30-106">これは、Active Directory サイトではなく、Lync Server 2013 サイトです。</span><span class="sxs-lookup"><span data-stu-id="ecc30-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="ecc30-107">展開ごとに複数の Kerberos 認証アカウントを作成することはできますが、1つのサイトに割り当てることができるアカウントは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="ecc30-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="ecc30-108">以前に作成した Kerberos 認証アカウントをサイトに割り当てるには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="ecc30-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="ecc30-109">Kerberos アカウントの作成の詳細については、「 [Lync Server 2013 で kerberos 認証アカウントを作成](lync-server-2013-create-a-kerberos-authentication-account.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecc30-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="ecc30-110">サイトに Kerberos 認証アカウントを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="ecc30-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="ecc30-111">RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ecc30-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="ecc30-112">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecc30-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ecc30-113">コマンドラインで、次の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ecc30-113">From the command line, run the following two commands:</span></span>
    
       ```
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```
        Enable-CsTopology
       ```
    
    <span data-ttu-id="ecc30-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ecc30-114">For example:</span></span>
    
       ```
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="ecc30-115">UserAccount パラメーターを指定するには、Domain\User 形式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecc30-115">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="ecc30-116">ユーザー @ ドメイン拡張子形式は、Kerberos 認証のために作成されたコンピューターオブジェクトを参照する場合はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ecc30-116">The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="ecc30-117">**オプション**: [Lync Server 2013 で WEB サービスの URL を変更](lync-server-2013-change-the-web-services-url.md)すると、WEB サイトの上書き FQDN (完全修飾ドメイン名) が設定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ecc30-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="ecc30-118">その場合は、この FQDN の SPN も追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecc30-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="ecc30-119">たとえば、FQDN が .local の場合は、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="ecc30-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
        setspn -S http/webservices.contoso.local kerbauth

5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ecc30-120">アカウントの追加やアカウントの削除など、Kerberos 認証を変更した後は、Lync Server 管理シェルのコマンドプロンプトから、 <STRONG>Enable-CsTopology</STRONG>方法を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecc30-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

