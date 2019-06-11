---
title: ダイヤルイン アクセス番号の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86db6e669fd5f52827591c25e5bb237bd9ee012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="cc994-102">ダイヤルイン アクセス番号の移行</span><span class="sxs-lookup"><span data-stu-id="cc994-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc994-103">_**最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="cc994-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="cc994-104">ダイヤルインアクセス番号を移行するには、次の2つの手順を実行する必要があります。**インポート-CsLegacyConfiguration**コマンドレットを実行し ([ポリシーと設定のインポート](import-policies-and-settings.md)では既に完了しています)、ダイヤルプランとその他のダイヤルインアクセス番号の設定を移行して、 \*\*\*\* コンタクトオブジェクトを移行するには、CsApplicationEndpoint コマンドレットを移動します。</span><span class="sxs-lookup"><span data-stu-id="cc994-104">Migrating dial-in access numbers requires two steps: running the **Import-CsLegacyConfiguration** cmdlet (completed earlier in [Import policies and settings](import-policies-and-settings.md)) to migrate dial plans and other dial-in access number settings, and running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span>

<div>

## <a name="to-migrate-dial-in-access-numbers"></a><span data-ttu-id="cc994-105">ダイヤルインアクセス番号を移行するには</span><span class="sxs-lookup"><span data-stu-id="cc994-105">To migrate dial-in access numbers</span></span>

1.  <span data-ttu-id="cc994-106">Office Communications Server 2007 R2 管理ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="cc994-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="cc994-107">コンソールツリーで、[フォレスト] ノードを右クリックし、[**プロパティ**] をクリックして、[**会議アテンダントのプロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc994-107">In the console tree, right-click the forest node, click **Properties**, and then click **Conferencing Attendant Properties**.</span></span>

3.  <span data-ttu-id="cc994-108">[**アクセス電話番号**] タブで、[**プールごとのサービス**] をクリックして、アクセス電話番号を関連付けられたプールで並べ替え、移行元のプールのすべてのアクセス番号を特定します。</span><span class="sxs-lookup"><span data-stu-id="cc994-108">On the **Access Phone Numbers** tab, click **Serviced by Pool** to sort the access phone numbers by their associated pool, and identify all the access numbers for the pool from which you are migrating.</span></span>

4.  <span data-ttu-id="cc994-109">各アクセス番号の SIP URI を確認するには、アクセス番号をダブルクリックして [**会議アテンダント番号の編集**] ダイアログボックスを開き、[ **sip uri**] を確認します。</span><span class="sxs-lookup"><span data-stu-id="cc994-109">To identify the SIP URI for each access number, double-click the access number to open the **Edit Conferencing Attendant Number** dialog box, and look under **SIP URI**.</span></span>

5.  <span data-ttu-id="cc994-110">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="cc994-110">Open the Lync Server Management Shell.</span></span>

6.  <span data-ttu-id="cc994-111">各ダイヤルインアクセス番号を Lync Server 2013 でホストされているプールに移動するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="cc994-111">To move each dial-in access number to a pool hosted on Lync Server 2013, run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  <span data-ttu-id="cc994-112">Office Communications Server 2007 R2 管理ツールの [**アクセス電話番号**] タブで、移行元の Office Communications Server 2007 R2 プールのダイヤルインアクセス番号が残っていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="cc994-112">In the Office Communications Server 2007 R2 Administrative tool, on the **Access Phone Numbers** tab, verify that no dial-in access numbers remain for the Office Communications Server 2007 R2 pool from which you are migrating.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

