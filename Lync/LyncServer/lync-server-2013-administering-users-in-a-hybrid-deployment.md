---
title: 'Lync Server 2013: ハイブリッド展開でユーザーを管理する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dd4f53eaa611d130291b1a42c798a8d5589968c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="f3054-102">ハイブリッド Lync Server 2013 展開でユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="f3054-102">Administering users in a hybrid Lync Server 2013 deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3054-103">_**最終更新日:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="f3054-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="f3054-104">Microsoft Office 365 Online ポータルで利用可能なユーザー管理機能を使って、Lync Online に移行したユーザーのユーザー設定とポリシーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f3054-104">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft Office 365 online portal.</span></span> <span data-ttu-id="f3054-105">管理タスクを実行するには、テナント管理者アカウントを使用してサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3054-105">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="f3054-106">ユーザーをオンプレミスに戻す</span><span class="sxs-lookup"><span data-stu-id="f3054-106">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="f3054-107">このセクションは、Lync をオンプレミスで作成して有効にし、オンプレミスの展開から Lync Online に移行したユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f3054-107">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="f3054-108">Lync Online で作成されたユーザーを移動する場合 (オンプレミスの展開で Lync に対して有効にしていない場合) は、「lync <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Online のユーザーを Lync Server 2013 で社内の lync に移動</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3054-108">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="f3054-109">Lync Online からオンプレミスの Lync にユーザーを戻すには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f3054-109">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```
        $cred=Get-Credential
       ```
    
       ```
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="f3054-110">**HostedMigrationOverrideUrl** パラメーターの URL には、ホスティング型移行サービスが実行されているプールへの URL を次の形式で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3054-110">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="f3054-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="f3054-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="f3054-112">ホスティング型移行サービスへの URL は、ご使用の Office 365 テナント アカウント用の Lync Online コントロール パネルの URL を表示することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="f3054-112">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="f3054-113">**Office 365 テナントのホスティング型移行サービスの URL を確認するには**</span><span class="sxs-lookup"><span data-stu-id="f3054-113">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="f3054-114">管理者として Office 365 テナントにログインします。</span><span class="sxs-lookup"><span data-stu-id="f3054-114">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="f3054-115">**Lync 管理センター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="f3054-115">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="f3054-116">**Lync 管理センター**が表示されたら、アドレスバーの URL を選択して**lync.com**にコピーします。</span><span class="sxs-lookup"><span data-stu-id="f3054-116">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="f3054-117">URL は、次のような書式です。</span><span class="sxs-lookup"><span data-stu-id="f3054-117">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="f3054-118">URL の **webdir** を **admin** に置き換えると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f3054-118">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="f3054-119">URL に以下の文字列を付加します。**/HostedMigration/hostedmigrationservice.svc**</span><span class="sxs-lookup"><span data-stu-id="f3054-119">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="f3054-120">以上の手順によって、**HostedMigrationOverrideUrl** の値を持った URL は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f3054-120">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

