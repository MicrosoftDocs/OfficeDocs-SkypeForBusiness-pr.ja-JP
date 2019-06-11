---
title: 'Lync Server 2013: 音声/ビデオ (A/V) エッジサーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9738dbb11ce731ac832a5529d2013f3f9b2907
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="43014-102">Lync Server 2013 の音声/ビデオ (A/V) エッジサーバー</span><span class="sxs-lookup"><span data-stu-id="43014-102">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43014-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="43014-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="43014-104">A/V Edge サービスは、内部ユーザー (組織のネットワークにログオンしているユーザー) が、外部ユーザー (組織のネットワークにログオンしていないユーザー) とオーディオやビデオを共有できるようにするための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="43014-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="43014-105">オーディオとビデオに加えて、A/V Edge サービスでは、デスクトップ共有やファイル転送などの機能もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="43014-105">In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="43014-106">A/V Edge サービスは、主に、A/V Edge 構成を使って管理されます。これらの設定では、1つのポートとユーザーごとに割り当てることができる帯域幅の最大量を管理できます。また、そのトークンが更新されるまでに認証トークンを使うことができる時間の長さを指定します。</span><span class="sxs-lookup"><span data-stu-id="43014-106">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed.</span></span> <span data-ttu-id="43014-107">A/V Edge の構成設定は、サイトまたは個々の A/V エッジサーバーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="43014-107">A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers.</span></span> <span data-ttu-id="43014-108">優先される設定のコレクションを決定する際には、次のガイドを使用します。</span><span class="sxs-lookup"><span data-stu-id="43014-108">When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="43014-109">サービスの範囲 (つまり個々のサーバー) で構成された設定は、すべてのユーザーに対して優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="43014-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="43014-110">サイトのスコープで構成された設定は、グローバルスコープで構成されている設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="43014-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="43014-111">ただし、サービスの範囲設定は、サイトの範囲設定にも優先されます。</span><span class="sxs-lookup"><span data-stu-id="43014-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="43014-112">グローバルスコープの設定は、個々のサーバーで構成されているサービス設定がなく、そのサーバーが配置されているサイトのサイト設定がない場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="43014-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="43014-113">A/V Edge サービスを管理するには、Lync Server PowerShell と CsAVEdgeConfiguration コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43014-113">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="43014-114">このセクション中</span><span class="sxs-lookup"><span data-stu-id="43014-114">In This Section</span></span>

  - [<span data-ttu-id="43014-115">Lync Server 2013 で A/V Edge サーバーの構成情報を返す</span><span class="sxs-lookup"><span data-stu-id="43014-115">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="43014-116">Lync Server 2013 での A/V Edge サーバー構成設定のコレクションを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="43014-116">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="43014-117">Lync Server 2013 での既存の A/V エッジサーバー構成の設定を削除する</span><span class="sxs-lookup"><span data-stu-id="43014-117">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

