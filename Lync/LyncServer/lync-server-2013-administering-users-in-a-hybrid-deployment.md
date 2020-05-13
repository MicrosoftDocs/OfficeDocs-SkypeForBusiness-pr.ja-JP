---
title: 'Lync Server 2013: ハイブリッド展開でのユーザーの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 906018941b00d8ef2cbb5e37aef8d1245ad93f00
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="cd514-102">ハイブリッド Lync Server 2013 展開でユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="cd514-102">Administering users in a hybrid Lync Server 2013 deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd514-103">_**トピックの最終更新日:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="cd514-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="cd514-104">Microsoft 365 管理センターで使用可能なユーザー管理機能を使用して、Lync Online に移行したユーザーのユーザー設定とポリシーを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="cd514-104">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="cd514-105">管理タスクを実行するには、テナント管理者アカウントを使用してサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd514-105">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="cd514-106">ユーザーを社内に戻す</span><span class="sxs-lookup"><span data-stu-id="cd514-106">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="cd514-107">このセクションは、Lync オンプレミスに対して作成および有効化された後、オンプレミス展開から Lync Online に移動したユーザーに対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="cd514-107">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="cd514-108">Lync Online で作成されたユーザーを移動する必要があり、オンプレミス展開で Lync が有効になっていない場合は、「lync <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">online から Lync Server 2013 の lync オンプレミスへのユーザーの移動</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd514-108">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="cd514-109">次のコマンドレットを実行して、ユーザーを Lync Online から Lync オンプレミスに戻します。</span><span class="sxs-lookup"><span data-stu-id="cd514-109">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="cd514-110">**HostedMigrationOverrideUrl**パラメーターに指定する url の形式は、次の形式で、Hosted Migration service が実行されているプールへの url である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd514-110">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="cd514-111">Https:// \< プールの FQDN \> /hostedmigration/hostedmigrationservice.svc</span><span class="sxs-lookup"><span data-stu-id="cd514-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="cd514-112">ホストされている移行サービスへの URL を確認するには、Microsoft 365 または Office 365 組織アカウントの Lync Online コントロールパネルの URL を表示します。</span><span class="sxs-lookup"><span data-stu-id="cd514-112">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>

<span data-ttu-id="cd514-113">**Microsoft 365 または Office 365 組織のホスト型移行サービスの URL を決定するには**</span><span class="sxs-lookup"><span data-stu-id="cd514-113">**To determine the Hosted Migration Service URL for your Microsoft 365 or Office 365 organization**</span></span>

1.  <span data-ttu-id="cd514-114">組織に管理者としてログインします。</span><span class="sxs-lookup"><span data-stu-id="cd514-114">Log in to your organization as an administrator.</span></span>

2.  <span data-ttu-id="cd514-115">**Lync 管理センター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="cd514-115">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="cd514-116">**Lync 管理センター**が表示されたら、アドレスバーの URL を選択して、 **lync.com**までコピーします。</span><span class="sxs-lookup"><span data-stu-id="cd514-116">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="cd514-117">URL の例は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cd514-117">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="cd514-118">URL 内の**webdir**を**管理者**に置き換えます。結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cd514-118">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="cd514-119">次の文字列を URL: **/HostedMigration/hostedmigrationservice.svc**に追加します。</span><span class="sxs-lookup"><span data-stu-id="cd514-119">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="cd514-120">生成される URL は**HostedMigrationOverrideUrl**の値で、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cd514-120">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

