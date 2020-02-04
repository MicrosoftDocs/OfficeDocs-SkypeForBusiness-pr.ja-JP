---
title: 'Lync Server 2013: IIS の保護'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03d0f3e736284970bf22fe813093e0e54accd29e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="b4749-102">Lync Server 2013 での IIS の保護</span><span class="sxs-lookup"><span data-stu-id="b4749-102">Protecting IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4749-103">_**最終更新日:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="b4749-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="b4749-104">Microsoft Office Communications Server 2007 および Microsoft Office Communications Server 2007 R2 で、インターネットインフォメーションサービス (IIS) は標準ユーザーアカウントで実行されました。</span><span class="sxs-lookup"><span data-stu-id="b4749-104">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="b4749-105">この問題の原因となっている可能性があります。パスワードの有効期限が切れた場合、Web サービスが失われることがあります。これは、診断が困難な問題です。</span><span class="sxs-lookup"><span data-stu-id="b4749-105">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="b4749-106">有効期限が切れたパスワードの問題を回避するために、Microsoft Lync Server 2013 では、IIS を実行しているサイトのすべてのコンピューターの認証プリンシパルとして機能するコンピューターアカウント (実際に存在しないコンピューターの場合) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b4749-106">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="b4749-107">これらのアカウントは Kerberos 認証プロトコルを使用するため、アカウントは Kerberos アカウントと呼ばれ、新しい認証プロセスが Kerberos Web 認証として認識されます。</span><span class="sxs-lookup"><span data-stu-id="b4749-107">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="b4749-108">このため、1 つのアカウントを使用してすべての IIS サーバーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="b4749-108">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="b4749-109">この認証プリンシパルでサーバーを実行するには、まず、新しい-Csker":" アカウントコマンドレットを使用してコンピューターアカウントを作成する必要があります。このアカウントは、1つ以上のサイトに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b4749-109">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="b4749-110">割り当てが行われた後、Enable-CsTopology コマンドレットを実行することで、アカウントと Lync Server 2013 サイト間の関連付けが有効になります。</span><span class="sxs-lookup"><span data-stu-id="b4749-110">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="b4749-111">この操作を行うと、Active Directory ドメインサービス (AD DS) に必要なサービスプリンシパル名 (SPN) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b4749-111">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="b4749-112">SPN は、クライアント アプリケーションが特定のサービスを検出するためのものです。</span><span class="sxs-lookup"><span data-stu-id="b4749-112">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="b4749-113">詳細については、操作のドキュメントに記載されている「[新](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount)機能」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4749-113">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="b4749-114">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="b4749-114">Best Practices</span></span>

<span data-ttu-id="b4749-115">IIS のセキュリティを強化するために、IIS 用の Kerberos アカウントを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b4749-115">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS.</span></span> <span data-ttu-id="b4749-116">Kerberos アカウントを実装しない場合、IIS は標準のユーザーアカウントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="b4749-116">If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

