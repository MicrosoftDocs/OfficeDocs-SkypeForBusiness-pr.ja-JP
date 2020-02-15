---
title: 'Lync Server 2013: IIS を保護する'
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
ms.openlocfilehash: 612945a8ad69cffa8401cb64367d8b860d556a19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="654fb-102">Lync Server 2013 での IIS の保護</span><span class="sxs-lookup"><span data-stu-id="654fb-102">Protecting IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="654fb-103">_**トピックの最終更新日:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="654fb-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="654fb-104">Microsoft Office Communications Server 2007 および Microsoft Office Communications Server 2007 R2 では、インターネットインフォメーションサービス (IIS) は標準のユーザーアカウントで実行されました。</span><span class="sxs-lookup"><span data-stu-id="654fb-104">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="654fb-105">これにより、問題が発生する可能性がありました。パスワードが期限切れになると、Web サービスが失われる可能性があります。これは、診断が困難な問題です。</span><span class="sxs-lookup"><span data-stu-id="654fb-105">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="654fb-106">有効期限が切れたパスワードの問題を回避するために、Microsoft Lync Server 2013 では、IIS を実行しているサイト内のすべてのコンピューターの認証プリンシパルとして機能するコンピューターアカウント (実際に存在しないコンピューターの場合) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="654fb-106">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="654fb-107">これらのアカウントは Kerberos 認証プロトコルを使用するため、アカウントは Kerberos アカウントと呼ばれ、新しい認証プロセスは Kerberos web 認証と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="654fb-107">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="654fb-108">これにより、1つのアカウントを使用してすべての IIS サーバーを管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="654fb-108">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="654fb-109">この認証プリンシパルでサーバーを実行するには、最初に New-CsKerberosAccount コマンドレットを使用してコンピューター アカウントを作成し、次にこのアカウントを 1 つ以上のサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="654fb-109">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="654fb-110">割り当てが行われた後、Enable-CsTopology コマンドレットを実行することによって、アカウントと Lync Server 2013 サイト間の関連付けが有効になります。</span><span class="sxs-lookup"><span data-stu-id="654fb-110">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="654fb-111">特に重要なのは、これによって必要なサービス プリンシパル名 (SPN) が Active Directory ドメイン サービス (AD DS) 内に作成されることです。</span><span class="sxs-lookup"><span data-stu-id="654fb-111">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="654fb-112">SPN は、クライアント アプリケーションが特定のサービスを見つけるために利用されます。</span><span class="sxs-lookup"><span data-stu-id="654fb-112">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="654fb-113">詳細については、「操作」のドキュメントの「[New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654fb-113">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="654fb-114">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="654fb-114">Best Practices</span></span>

<span data-ttu-id="654fb-p103">IIS のセキュリティを強化するために、IIS 用の Kerberos アカウントを実装することをお勧めします。Kerberos アカウントを実装しない場合、IIS は標準のユーザー アカウントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="654fb-p103">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS. If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

