---
title: 'Lync Server 2013: Kerberos 認証の設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42f2c781b01aaa1ac00793f97067f24233c1e8db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="52dc8-102">Lync Server 2013 での Kerberos 認証のセットアップ</span><span class="sxs-lookup"><span data-stu-id="52dc8-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52dc8-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="52dc8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="52dc8-104">Lync Server 2013 は、Web サービスの NTLM および Kerberos 認証をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="52dc8-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="52dc8-105">Office Communications Server 2007 および Office Communications Server 2007 R2 Web サービスアプリケーションプールを実行するためのユーザーアカウントとして、既定の RTCComponentService および RTCService を使用して、サービスプリンシパル名 (SPN) をユーザーに割り当てることができます。アカウントを選択し、認証プリンシパルとして機能します。</span><span class="sxs-lookup"><span data-stu-id="52dc8-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="52dc8-106">Lync Server は NetworkService を使用して Web サービスを実行し、NetworkService に Spn を割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="52dc8-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="52dc8-107">Active Directory オブジェクトに Spn を保持する必要がないという問題を解決するために、Lync Server コントロールパネルでこの目的のためにコンピューターアカウントオブジェクトを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="52dc8-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="52dc8-108">コンピューターアカウントオブジェクトは、Spn を保持することができ、パスワードの有効期限の対象にはなりません。これは、以前のバージョンでユーザーアカウントを使用する場合の問題でした。</span><span class="sxs-lookup"><span data-stu-id="52dc8-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="52dc8-109">Windows PowerShell コマンドレットを使用して、Kerberos 認証を提供するようにコンピューターオブジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="52dc8-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="52dc8-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="52dc8-110">In This Section</span></span>

  - [<span data-ttu-id="52dc8-111">Lync Server 2013 で Kerberos 認証を有効にするための前提条件</span><span class="sxs-lookup"><span data-stu-id="52dc8-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="52dc8-112">Lync Server 2013 で Kerberos 認証アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="52dc8-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="52dc8-113">Lync Server 2013 のサイトへの Kerberos 認証アカウントの割り当て</span><span class="sxs-lookup"><span data-stu-id="52dc8-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="52dc8-114">Lync Server 2013 での Kerberos 認証アカウントパスワードの設定</span><span class="sxs-lookup"><span data-stu-id="52dc8-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="52dc8-115">Lync Server 2013 の他のサイトへの Kerberos 認証の追加</span><span class="sxs-lookup"><span data-stu-id="52dc8-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="52dc8-116">Lync Server 2013 で、サイトから Kerberos 認証を削除する</span><span class="sxs-lookup"><span data-stu-id="52dc8-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="52dc8-117">Lync Server 2013 での Kerberos 認証の状態と割り当てのテストおよびレポート</span><span class="sxs-lookup"><span data-stu-id="52dc8-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

