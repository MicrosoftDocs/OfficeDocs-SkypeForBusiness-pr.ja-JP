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
ms.openlocfilehash: 8c644dd613b3186b314e8fc78b42197709286200
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="effac-102">Lync Server 2013 での Kerberos 認証の設定</span><span class="sxs-lookup"><span data-stu-id="effac-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="effac-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="effac-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="effac-104">Lync Server 2013 は、Web サービスの NTLM 認証と Kerberos 認証をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="effac-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="effac-105">Office Communications Server 2007 および Office Communications Server 2007 R2 では、サービスプリンシパル名 (SPN) をユーザーに割り当てることができるように、Web サービスのアプリケーションプールを実行するためのユーザーアカウントとして、既定の RTCComponentService と RTCService を使用しましたアカウントを選び、認証プリンシパルとして機能します。</span><span class="sxs-lookup"><span data-stu-id="effac-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="effac-106">Lync Server は NetworkService を使って Web サービスを実行します。 NetworkService には、Spn を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="effac-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="effac-107">Active Directory オブジェクトに Spn を保持する必要がないという問題を解決するために、Lync Server コントロールパネルでは、この目的でコンピューターアカウントオブジェクトを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="effac-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="effac-108">コンピューターアカウントオブジェクトは、Spn を保持することができ、パスワードの有効期限は適用されません。これは、以前のバージョンでのユーザーアカウントの使用に関する問題です。</span><span class="sxs-lookup"><span data-stu-id="effac-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="effac-109">Kerberos 認証を提供するようにコンピューターオブジェクトを構成するには、Windows PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="effac-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="effac-110">このセクション中</span><span class="sxs-lookup"><span data-stu-id="effac-110">In This Section</span></span>

  - [<span data-ttu-id="effac-111">Lync Server 2013 で Kerberos 認証を有効にするための前提条件</span><span class="sxs-lookup"><span data-stu-id="effac-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="effac-112">Lync Server 2013 での Kerberos 認証アカウントの作成</span><span class="sxs-lookup"><span data-stu-id="effac-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="effac-113">Lync Server 2013 での、サイトへの Kerberos 認証アカウントの割り当て</span><span class="sxs-lookup"><span data-stu-id="effac-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="effac-114">Lync Server 2013 での Kerberos 認証アカウント パスワードの設定</span><span class="sxs-lookup"><span data-stu-id="effac-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="effac-115">Lync Server 2013 での他のサイトへの Kerberos 認証の追加</span><span class="sxs-lookup"><span data-stu-id="effac-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="effac-116">Lync Server 2013 でのサイトからの Kerberos 認証の削除</span><span class="sxs-lookup"><span data-stu-id="effac-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="effac-117">Lync Server 2013 での Kerberos 認証の状態と割り当てについてのテストおよびレポート</span><span class="sxs-lookup"><span data-stu-id="effac-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

