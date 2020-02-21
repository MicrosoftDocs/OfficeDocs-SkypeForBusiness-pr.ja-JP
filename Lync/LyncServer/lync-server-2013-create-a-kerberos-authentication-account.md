---
title: 'Lync Server 2013: Kerberos 認証アカウントの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b41a19a46a23d24a680b3987f7d5eca01daab89
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="5a63d-102">Lync Server 2013 で Kerberos 認証アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="5a63d-102">Create a Kerberos authentication account in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a63d-103">_**トピックの最終更新日:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="5a63d-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="5a63d-104">この手順を適切に完了するには、少なくとも Domain Admins グループのメンバーとしてサーバーまたはドメインにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a63d-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="5a63d-105">各サイトに Kerberos 認証アカウントを作成したり、単一の Kerberos 認証アカウントを作成してすべてのサイトで使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a63d-105">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="5a63d-106">Windows PowerShell コマンドレットを使用して、各サイトに割り当てられたアカウントの識別を含む、アカウントの作成と管理を行います。</span><span class="sxs-lookup"><span data-stu-id="5a63d-106">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="5a63d-107">トポロジビルダーおよび Lync Server 2013 コントロールパネルに Kerberos 認証アカウントが表示されません。</span><span class="sxs-lookup"><span data-stu-id="5a63d-107">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="5a63d-108">1 つ以上のユーザー アカウントを作成して Kerberos 認証用に使用するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a63d-108">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="5a63d-109">Kerberos アカウントを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a63d-109">To create a Kerberos account</span></span>

1.  <span data-ttu-id="5a63d-110">Domain Admins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5a63d-110">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="5a63d-111">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a63d-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5a63d-112">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a63d-112">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="5a63d-113">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a63d-113">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="5a63d-114">コンピューター オブジェクトが作成されていることを確認します。それには、[Active Directory ユーザーとコンピューター] を開いて、[**ユーザー**] コンテナーを展開し、ユーザー アカウントのコンピューター オブジェクトがコンテナー内にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a63d-114">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

