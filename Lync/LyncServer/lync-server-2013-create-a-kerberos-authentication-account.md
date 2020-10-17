---
title: 'Lync Server 2013: Kerberos 認証アカウントの作成'
description: 'Lync Server 2013: Kerberos 認証アカウントを作成します。'
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
ms.openlocfilehash: b2f8e87a8ffcc95af4a44e516ac4e1f4d635d737
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542133"
---
# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="0fb5d-103">Lync Server 2013 で Kerberos 認証アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="0fb5d-103">Create a Kerberos authentication account in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fb5d-104">_**トピックの最終更新日:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="0fb5d-104">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="0fb5d-105">この手順を適切に完了するには、少なくとも Domain Admins グループのメンバーとしてサーバーまたはドメインにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fb5d-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="0fb5d-106">各サイトに Kerberos 認証アカウントを作成したり、単一の Kerberos 認証アカウントを作成してすべてのサイトで使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0fb5d-106">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="0fb5d-107">Windows PowerShell コマンドレットを使用して、各サイトに割り当てられたアカウントの識別を含む、アカウントの作成と管理を行います。</span><span class="sxs-lookup"><span data-stu-id="0fb5d-107">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="0fb5d-108">トポロジビルダーおよび Lync Server 2013 コントロールパネルに Kerberos 認証アカウントが表示されません。</span><span class="sxs-lookup"><span data-stu-id="0fb5d-108">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="0fb5d-109">1 つ以上のユーザー アカウントを作成して Kerberos 認証用に使用するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0fb5d-109">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="0fb5d-110">Kerberos アカウントを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0fb5d-110">To create a Kerberos account</span></span>

1.  <span data-ttu-id="0fb5d-111">Domain Admins グループのメンバーとして、Lync Server 2013 を実行しているドメイン内のコンピューター、または管理ツールがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0fb5d-111">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="0fb5d-112">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fb5d-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0fb5d-113">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0fb5d-113">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="0fb5d-114">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="0fb5d-114">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="0fb5d-115">コンピューター オブジェクトが作成されていることを確認します。それには、[Active Directory ユーザーとコンピューター] を開いて、[**ユーザー**] コンテナーを展開し、ユーザー アカウントのコンピューター オブジェクトがコンテナー内にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0fb5d-115">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

