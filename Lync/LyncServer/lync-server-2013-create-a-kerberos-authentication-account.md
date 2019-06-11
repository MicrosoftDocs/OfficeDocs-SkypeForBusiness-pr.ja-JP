---
title: 'Lync Server 2013: Kerberos 認証アカウントの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ab4f93d4204f7ed1f2b22d27ddb51328f8330c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="bfc93-102">Lync Server 2013 での Kerberos 認証アカウントの作成</span><span class="sxs-lookup"><span data-stu-id="bfc93-102">Create a Kerberos authentication account in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfc93-103">_**最終更新日:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="bfc93-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="bfc93-104">この手順を正常に完了するには、ドメイン管理者グループのメンバーとしてサーバーまたはドメインに最小でログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfc93-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="bfc93-105">各サイトに対して Kerberos 認証アカウントを作成することも、単一の Kerberos 認証アカウントを作成してすべてのサイトで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bfc93-105">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="bfc93-106">各サイトに割り当てられているアカウントの識別など、アカウントの作成と管理には、Windows PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfc93-106">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="bfc93-107">トポロジビルダーと Lync Server 2013 コントロールパネルには、Kerberos 認証アカウントが表示されません。</span><span class="sxs-lookup"><span data-stu-id="bfc93-107">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="bfc93-108">Kerberos 認証に使用する1つ以上のユーザーアカウントを作成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="bfc93-108">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="bfc93-109">Kerberos アカウントを作成するには</span><span class="sxs-lookup"><span data-stu-id="bfc93-109">To create a Kerberos account</span></span>

1.  <span data-ttu-id="bfc93-110">Domain Admins グループのメンバーとして、Lync Server 2013 を実行しているドメインのコンピューターにログオンするか、管理ツールがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bfc93-110">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="bfc93-111">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfc93-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bfc93-112">コマンドラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bfc93-112">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="bfc93-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bfc93-113">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="bfc93-114">Active Directory ユーザーとコンピューターを開き、[**ユーザー** ] コンテナーを展開し、ユーザーアカウントのコンピューターオブジェクトがコンテナー内にあることを確認して、コンピューターオブジェクトが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bfc93-114">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

