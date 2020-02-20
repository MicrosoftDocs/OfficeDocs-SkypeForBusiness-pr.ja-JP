---
title: 'Lync Server 2013: 音声ビデオ (A/V) エッジサーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62f31721b21e8738dcd57dfb203d7fd306c38c94
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="37a78-102">Lync Server 2013 の音声ビデオ (A/V) エッジサーバー</span><span class="sxs-lookup"><span data-stu-id="37a78-102">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37a78-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="37a78-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="37a78-p101">音声ビデオ エッジ サービスを使用すると、内部ユーザー (組織のネットワークにログオンしているユーザー) は外部ユーザー (組織のネットワークにログオンしていないユーザー) とオーディオおよびビデオを共有できるようになります。音声およびビデオに加え、音声ビデオ エッジ サービスはデスクトップ共有やファイル送信などもサポートします。</span><span class="sxs-lookup"><span data-stu-id="37a78-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="37a78-p102">音声ビデオ エッジ サービスは主に音声ビデオ エッジ構成を使用して管理されます。これらの設定を使用すると、ポートごとおよびユーザーごとに割り当てる最大帯域幅を管理したり、認証トークンを更新する前に使用できる時間の長さを指定したりすることができます。音声ビデオ エッジ構成設定は、サイトまたは個々の音声ビデオ エッジ サーバーに適用できます。優先する設定のコレクションを判断するときは、以下のガイドを使用します。</span><span class="sxs-lookup"><span data-stu-id="37a78-p102">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed. A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers. When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="37a78-109">サービス スコープで (つまり個々のサーバーで) 構成した設定は最優先されます。</span><span class="sxs-lookup"><span data-stu-id="37a78-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="37a78-p103">サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。ただし、サービス スコープ設定はサイトスコープ設定を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="37a78-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="37a78-112">グローバル スコープで構成した設定は、個々のサーバーで構成されたサービス設定がなく、サーバーが配置されているサイトのサイト設定がない場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="37a78-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="37a78-113">音声ビデオエッジサービスは、Lync Server PowerShell と Get-csavedgeconfiguration コマンドレットを使用してのみ管理できます。</span><span class="sxs-lookup"><span data-stu-id="37a78-113">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="37a78-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="37a78-114">In This Section</span></span>

  - [<span data-ttu-id="37a78-115">Lync Server 2013 での音声ビデオエッジサーバーの構成情報の取得</span><span class="sxs-lookup"><span data-stu-id="37a78-115">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="37a78-116">Lync Server 2013 での音声ビデオエッジサーバー構成設定のコレクションの作成または変更</span><span class="sxs-lookup"><span data-stu-id="37a78-116">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="37a78-117">Lync Server 2013 の音声ビデオエッジサーバー構成設定の既存コレクションの削除</span><span class="sxs-lookup"><span data-stu-id="37a78-117">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

