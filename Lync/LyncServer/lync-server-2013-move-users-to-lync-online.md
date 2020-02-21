---
title: 'Lync Server 2013: Lync Online へのユーザーの移動'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f490a50ade6c10d37a478729c46a5545970afb1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="95b67-102">Lync Server 2013 でユーザーを Lync Online に移動する</span><span class="sxs-lookup"><span data-stu-id="95b67-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95b67-103">_**トピックの最終更新日:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="95b67-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="95b67-104">ユーザーの Lync Online への移行を開始する前に、移動するアカウントに関連付けられているユーザーデータをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="95b67-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="95b67-105">ユーザーアカウントを使用して、一部のユーザーデータが移動されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="95b67-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="95b67-106">詳細については、「 [Lync Server 2013: data」の「バックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95b67-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="95b67-107">ユーザー設定を Lync Online に移行する</span><span class="sxs-lookup"><span data-stu-id="95b67-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="95b67-108">ユーザー設定は、ユーザー アカウントと共に移動されます。</span><span class="sxs-lookup"><span data-stu-id="95b67-108">User settings are moved with the user account.</span></span> <span data-ttu-id="95b67-109">オンプレミスの設定の中には、ユーザーアカウントを使用して移動しないものがあります。</span><span class="sxs-lookup"><span data-stu-id="95b67-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="95b67-110">パイロットユーザーを Lync Online に移行する</span><span class="sxs-lookup"><span data-stu-id="95b67-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="95b67-111">Lync Online へのユーザーの移動を開始する前に、いくつかのパイロットユーザーを移動して、環境が正しく構成されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="95b67-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="95b67-112">その後、追加のユーザーの移動を試みる前に、Lync の機能とサービスが期待どおりに機能することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="95b67-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="95b67-113">オンプレミスのユーザーを Lync Online テナントに移動するには、Microsoft Office 365 テナントの管理者の資格情報を使用して、Lync Server 管理シェルで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="95b67-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="95b67-114">"Username@contoso.com" を、移動するユーザーの情報に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="95b67-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="95b67-115">**HostedMigrationOverrideUrl**パラメーターに指定する url の形式は、次の形式で、Hosted Migration service が実行されているプールへの url である必要\<があり\>ます。 Https://pool FQDN/hostedmigration/hostedmigrationservice.svc</span><span class="sxs-lookup"><span data-stu-id="95b67-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="95b67-116">Office 365 テナントアカウントの Lync Online コントロールパネルの URL を表示することによって、ホストされた移行サービスへの URL を確認できます。</span><span class="sxs-lookup"><span data-stu-id="95b67-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="95b67-117">**Office 365 テナントのホスト型移行サービスの URL を確認するには**</span><span class="sxs-lookup"><span data-stu-id="95b67-117">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="95b67-118">Office 365 テナントに管理者としてログインします。</span><span class="sxs-lookup"><span data-stu-id="95b67-118">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="95b67-119">**Lync 管理センター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="95b67-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="95b67-120">**Lync 管理センター**が表示されたら、アドレスバーの URL を選択して、 **lync.com**までコピーします。</span><span class="sxs-lookup"><span data-stu-id="95b67-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="95b67-121">URL の例は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="95b67-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="95b67-122">URL 内の**webdir**を**管理者**に置き換えます。結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="95b67-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="95b67-123">次の文字列を URL: **/HostedMigration/hostedmigrationservice.svc**に追加します。</span><span class="sxs-lookup"><span data-stu-id="95b67-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="95b67-124">生成される URL は**HostedMigrationOverrideUrl**の値で、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="95b67-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="95b67-125">Lync Online へのユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="95b67-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="95b67-126">-Filter パラメーターを指定して RegistrarPool[コマンドレット](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)を使用して、ユーザーアカウントに割り当てられた特定のプロパティを持つユーザーを選択することで、複数のユーザーを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="95b67-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="95b67-127">その後、次の例に示すように、返されたユーザーを[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)コマンドレットにパイプ処理できます。</span><span class="sxs-lookup"><span data-stu-id="95b67-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="95b67-128">また、次の例に示すように、-OU パラメーターを使用して、指定した OU 内のすべてのユーザーを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="95b67-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="95b67-129">Lync Online のユーザー設定と機能を確認する</span><span class="sxs-lookup"><span data-stu-id="95b67-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="95b67-130">ユーザーの移動が正常に完了したことは、次の方法で確認できます。</span><span class="sxs-lookup"><span data-stu-id="95b67-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="95b67-p107">Lync Online コントロール パネルでユーザーの状態を表示します。社内ユーザーとオンライン ユーザーでは視覚的なインジケーターが異なります。</span><span class="sxs-lookup"><span data-stu-id="95b67-p107">View the status of the user in the Lync Online Control Panel. The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="95b67-133">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="95b67-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

