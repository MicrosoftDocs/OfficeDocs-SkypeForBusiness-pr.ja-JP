---
title: Lync Server 2013 クライアントを展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac6dce30e356ed3161f985f32d8f26dc0e34ac6d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a><span data-ttu-id="3c1b5-102">Lync Server 2013 クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="3c1b5-102">Deploy Lync Server 2013 clients</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c1b5-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3c1b5-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3c1b5-104">ユーザーを Lync Server 2013 に移行した後、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c1b5-104">After you migrate users to Lync Server 2013, do the following:</span></span>

1.  <span data-ttu-id="3c1b5-105">新しい Lync Server 2013 サーバーでクライアントバージョンフィルターを使用して、最新の更新プログラムがインストールされているクライアントのみがサインインできるようにします。</span><span class="sxs-lookup"><span data-stu-id="3c1b5-105">Use the Client Version Filter on the new Lync Server 2013 server to only allow clients with the most current updates installed to sign in.</span></span>

2.  <span data-ttu-id="3c1b5-106">必要に応じて、クライアントのブートストラップに必要なグループ ポリシー設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="3c1b5-106">If necessary, configure the Group Policy settings that are required for client bootstrapping.</span></span> <span data-ttu-id="3c1b5-107">詳細については、「展開」のドキュメントの「 [Lync Server 2013 でのクライアントブートストラップポリシーの構成](lync-server-2013-configuring-client-bootstrapping-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c1b5-107">For details, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="3c1b5-108">これらの設定の構成は、既存のクライアント ブートストラップ ポリシーの変更または新しいクライアント ブートストラップ ポリシーの作成を行う場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="3c1b5-108">Configuration of these settings is only necessary if you want to change existing client bootstrapping policies or if you want to set new client bootstrapping policies.</span></span> <span data-ttu-id="3c1b5-109">クライアント ブートストラップ ポリシーを構成する予定がない場合や、従来のクライアント ブートストラップ ポリシーをそのまま有効にしておく場合、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3c1b5-109">If you do not plan to configure client bootstrapping policies, or you want legacy client bootstrapping policies to remain in effect, no action is necessary.</span></span>

3.  <span data-ttu-id="3c1b5-110">Lync Server 2013 コントロールパネル、Lync Server 2013 管理シェル、またはその両方を使用して、特定のユーザーまたはユーザーグループに対して他のユーザーおよびクライアントポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3c1b5-110">Configure other user and client policies for specific users or groups of users by using Lync Server 2013 Control Panel, Lync Server 2013 Management Shell, or both.</span></span> <span data-ttu-id="3c1b5-111">詳細については、「計画」のドキュメントの「 [Lync 2013 の新しい設定と変更された設定](lync-server-2013-new-and-changed-settings-for-lync-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c1b5-111">For details, see [New and changed settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in the Planning documentation.</span></span>

4.  <span data-ttu-id="3c1b5-112">最新バージョンの Lync Server 2013 クライアントを最新の累積的な更新プログラムと共に展開します。</span><span class="sxs-lookup"><span data-stu-id="3c1b5-112">Deploy the latest version of Lync Server 2013 clients along with the latest cumulative updates.</span></span> <span data-ttu-id="3c1b5-113">詳細については、「展開」のドキュメントの「 [Lync Server 2013 でのクライアントとデバイスの展開](lync-server-2013-deploying-clients-and-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c1b5-113">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

5.  <span data-ttu-id="3c1b5-114">オプション組織で Lync Server 2013 の拡張プレゼンスプライバシーモードが必要な場合は、移行の完了後に、以前のクライアントバージョンがサインインできないようにするためのクライアントバージョンポリシールールを定義します。</span><span class="sxs-lookup"><span data-stu-id="3c1b5-114">(Optional) If your organization requires Lync Server 2013 enhanced presence privacy mode, after migration is complete, define a Client Version Policy Rule to prevent earlier client versions from signing in.</span></span> <span data-ttu-id="3c1b5-115">その後、拡張プレゼンスのプライバシー モードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3c1b5-115">Then, enable enhanced presence privacy mode.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3c1b5-116">Lync 2013 enhanced プレゼンスプライバシーモードを有効にしないでください。特定のサーバープールのすべてのユーザーには、最新のクライアントバージョンがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="3c1b5-116">Do not enable Lync 2013 enhanced presence privacy mode until every user on a given server pool has the most current client versions installed.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

