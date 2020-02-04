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
ms.openlocfilehash: ffc6ee3831968c34bcdb501fcdf543626546e2c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a><span data-ttu-id="18deb-102">Lync Server 2013 クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="18deb-102">Deploy Lync Server 2013 clients</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18deb-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="18deb-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="18deb-104">ユーザーを Lync Server 2013 に移行した後で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="18deb-104">After you migrate users to Lync Server 2013, do the following:</span></span>

1.  <span data-ttu-id="18deb-105">新しい Lync Server 2013 サーバーでクライアントバージョンフィルターを使用して、最新の更新プログラムがインストールされているクライアントのみがサインインに参加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="18deb-105">Use the Client Version Filter on the new Lync Server 2013 server to only allow clients with the most current updates installed to sign in.</span></span>

2.  <span data-ttu-id="18deb-106">必要に応じて、クライアントブートストラップに必要なグループポリシー設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="18deb-106">If necessary, configure the Group Policy settings that are required for client bootstrapping.</span></span> <span data-ttu-id="18deb-107">詳細については、展開ドキュメントの「 [Lync Server 2013 でのクライアントブートストラップポリシーの構成](lync-server-2013-configuring-client-bootstrapping-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18deb-107">For details, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="18deb-108">これらの設定を構成する必要があるのは、既存のクライアントブートストラップポリシーを変更する場合、または新しいクライアントブートストラップポリシーを設定する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="18deb-108">Configuration of these settings is only necessary if you want to change existing client bootstrapping policies or if you want to set new client bootstrapping policies.</span></span> <span data-ttu-id="18deb-109">クライアントブートストラップポリシーの構成を計画していない場合、またはレガシクライアントブートストラップポリシーを引き続き有効にする必要がある場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="18deb-109">If you do not plan to configure client bootstrapping policies, or you want legacy client bootstrapping policies to remain in effect, no action is necessary.</span></span>

3.  <span data-ttu-id="18deb-110">Lync Server 2013 コントロールパネル、Lync Server 2013 管理シェル、またはその両方を使用して、特定のユーザーまたはユーザーグループの他のユーザーとクライアントのポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="18deb-110">Configure other user and client policies for specific users or groups of users by using Lync Server 2013 Control Panel, Lync Server 2013 Management Shell, or both.</span></span> <span data-ttu-id="18deb-111">詳細については、計画ドキュメントの「 [Lync 2013 の新しい設定と変更された設定](lync-server-2013-new-and-changed-settings-for-lync-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18deb-111">For details, see [New and changed settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in the Planning documentation.</span></span>

4.  <span data-ttu-id="18deb-112">最新バージョンの Lync Server 2013 クライアントと最新の累積更新プログラムを展開します。</span><span class="sxs-lookup"><span data-stu-id="18deb-112">Deploy the latest version of Lync Server 2013 clients along with the latest cumulative updates.</span></span> <span data-ttu-id="18deb-113">詳細については、展開ドキュメントの「 [Lync Server 2013 でのクライアントとデバイスの展開](lync-server-2013-deploying-clients-and-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18deb-113">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

5.  <span data-ttu-id="18deb-114">省略組織で Lync Server 2013 強化されたプレゼンスプライバシーモードが必要な場合は、移行が完了した後で、以前のバージョンのクライアントでサインインできないように、クライアントのバージョンポリシールールを定義します。</span><span class="sxs-lookup"><span data-stu-id="18deb-114">(Optional) If your organization requires Lync Server 2013 enhanced presence privacy mode, after migration is complete, define a Client Version Policy Rule to prevent earlier client versions from signing in.</span></span> <span data-ttu-id="18deb-115">次に、拡張プレゼンスプライバシーモードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="18deb-115">Then, enable enhanced presence privacy mode.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="18deb-116">特定のサーバープールのすべてのユーザーが最新のクライアントバージョンをインストールしているまで、Lync 2013 拡張プレゼンスプライバシーモードを有効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="18deb-116">Do not enable Lync 2013 enhanced presence privacy mode until every user on a given server pool has the most current client versions installed.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

