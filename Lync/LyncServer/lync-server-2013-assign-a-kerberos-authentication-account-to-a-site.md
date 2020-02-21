---
title: 'Lync Server 2013: サイトへの Kerberos 認証アカウントの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a28efed0276fd1665746f55fdf2bdc14cef8e226
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="9aef0-102">Lync Server 2013 のサイトへの Kerberos 認証アカウントの割り当て</span><span class="sxs-lookup"><span data-stu-id="9aef0-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9aef0-103">_**トピックの最終更新日:** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="9aef0-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="9aef0-104">この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aef0-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="9aef0-105">Kerberos アカウントを作成した後、これをサイトに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aef0-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="9aef0-106">これは、Active Directory サイトではなく、Lync Server 2013 サイトです。</span><span class="sxs-lookup"><span data-stu-id="9aef0-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="9aef0-107">1 つの展開に複数の Kerberos 認証アカウントを作成できますが、サイトに割り当てられるアカウントは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="9aef0-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="9aef0-108">以前に作成した Kerberos 認証アカウントをサイトに割り当てるには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9aef0-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="9aef0-109">Kerberos アカウントの作成の詳細については、「 [Lync Server 2013 で kerberos 認証アカウントを作成する](lync-server-2013-create-a-kerberos-authentication-account.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9aef0-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="9aef0-110">Kerberos 認証アカウントをサイトに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="9aef0-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="9aef0-111">RTCUniversalServerAdmins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9aef0-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="9aef0-112">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9aef0-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9aef0-113">コマンド ラインで次の 2 つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9aef0-113">From the command line, run the following two commands:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="9aef0-114">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="9aef0-114">For example:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="9aef0-p102">UserAccount パラメーターは、ドメイン\ユーザーの形式で指定する必要があります。 ユーザー@ドメイン.拡張子の形式は、Kerberos 認証用に作成されたコンピューター オブジェクトの参照ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9aef0-p102">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="9aef0-117">**オプション**: [Lync Server 2013 での Web サービス URL の変更](lync-server-2013-change-the-web-services-url.md)に応じて、WEB サービスの上書き FQDN (完全修飾ドメイン名) を構成した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9aef0-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="9aef0-118">その場合は、この FQDN の SPN も追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aef0-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="9aef0-119">たとえば、FQDN が [イントラネット] の場合は、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="9aef0-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9aef0-120">アカウントの追加、アカウントの削除など、Kerberos 認証に変更を加えた後、Lync Server 管理シェルコマンドプロンプトから<STRONG>Enable-CsTopology</STRONG>設定を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aef0-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

