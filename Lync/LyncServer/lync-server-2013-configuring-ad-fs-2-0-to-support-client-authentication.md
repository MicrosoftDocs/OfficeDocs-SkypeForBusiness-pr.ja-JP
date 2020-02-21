---
title: 'Lync Server 2013: クライアント認証をサポートするように AD FS 2.0 を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c48e474c511fd8d2e4b3e84bea0d74fcfeb650ac
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="37079-102">Lync Server 2013 でクライアント認証をサポートするように AD FS 2.0 を構成する</span><span class="sxs-lookup"><span data-stu-id="37079-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37079-103">_**トピックの最終更新日:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="37079-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="37079-104">AD FS 2.0 がスマートカードを使用した認証をサポートするように構成できる認証の種類には、次の2つがあります。</span><span class="sxs-lookup"><span data-stu-id="37079-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="37079-105">フォームベース認証 (FBA)</span><span class="sxs-lookup"><span data-stu-id="37079-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="37079-106">トランスポート層セキュリティクライアント認証</span><span class="sxs-lookup"><span data-stu-id="37079-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="37079-107">フォームベース認証を使用すると、ユーザーのユーザー名またはパスワードを使用するか、スマートカードと PIN を使用して認証を行う web ページを開発できます。</span><span class="sxs-lookup"><span data-stu-id="37079-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="37079-108">このトピックでは、AD FS 2.0 を使用してトランスポート層セキュリティクライアント認証を実装する方法に焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="37079-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="37079-109">AD FS 2.0 認証の種類の詳細については、「AD FS 2.0: で[https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384)ローカル認証の種類を変更する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37079-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="37079-110">**クライアント認証をサポートするように AD FS 2.0 を構成するには**</span><span class="sxs-lookup"><span data-stu-id="37079-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="37079-111">ドメイン管理者アカウントを使用して、AD FS 2.0 コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="37079-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="37079-112">Windows エクスプローラーを起動します。</span><span class="sxs-lookup"><span data-stu-id="37079-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="37079-113">C: inetpub\\\\adfs\\ls を参照します。</span><span class="sxs-lookup"><span data-stu-id="37079-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="37079-114">既存の web.config ファイルのバックアップコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="37079-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="37079-115">メモ帳を使用して既存の web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="37079-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="37079-116">メニューバーから [**編集**] を選択し、[**検索**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="37079-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="37079-117">\*\* \<Localauthenticationtypes\>\*\* を検索します。</span><span class="sxs-lookup"><span data-stu-id="37079-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="37079-118">一覧には、1行に1つずつ、4つの認証の種類があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="37079-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="37079-119">TLSClient 認証の種類を含む行をセクションの一覧の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="37079-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="37079-120">Web.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="37079-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="37079-121">昇格された特権を使用してコマンドプロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="37079-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="37079-122">次のコマンドを実行して IIS を再起動します。</span><span class="sxs-lookup"><span data-stu-id="37079-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

