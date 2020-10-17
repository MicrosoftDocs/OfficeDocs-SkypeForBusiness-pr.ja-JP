---
title: 'Lync Server 2013: 音声ルーティング構成のエクスポートとインポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting and importing voice routing configuration
ms:assetid: c9b78622-5725-43b0-9ee1-5b82b1e1c8eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398836(v=OCS.15)
ms:contentKeyID: 48185398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73e79d973d4befc4eb0ecfd496aa9fd442174e56
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531024"
---
# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="63d63-102">Lync Server 2013 での音声ルーティング構成のエクスポートとインポート</span><span class="sxs-lookup"><span data-stu-id="63d63-102">Exporting and importing voice routing configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63d63-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="63d63-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="63d63-104">音声ルーティング構成を公開せずに保存する場合は、次の手順に従って、Lync Server コントロールパネルの [構成のエクスポート] および [インポート] コマンドを使用して、音声ルーティング構成のスナップショットを保存および取得します。</span><span class="sxs-lookup"><span data-stu-id="63d63-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="63d63-105">音声ルーティング構成ファイル (vcfg) をインポートするときに、その間にサーバー上の音声ルーティング構成に変更が加えられた場合、Lync Server コントロールパネルの [ **音声ルーティング** ] グループのページには、音声ルーティングにコミットされていない変更があることが示されます。</span><span class="sxs-lookup"><span data-stu-id="63d63-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="63d63-106">これらの未確定の変更は、調整が必要な 2 つの構成間の相違です。</span><span class="sxs-lookup"><span data-stu-id="63d63-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="63d63-107">[<STRONG>音声ルーティング</STRONG>] グループ内のいずれかのページで、設定に対して未確定の変更を行った場合、これらの変更はエクスポートされた音声構成ファイル (.vcfg) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="63d63-107">If you have made any uncommitted changes to the settings on any page within the <STRONG>Voice Routing</STRONG> group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="63d63-108">これにより、変更を公開する前に、複数の Lync Server コントロールパネルセッション中に音声ルーティング構成を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="63d63-108">This enables you to make voice routing configuration changes during multiple Lync Server Control Panel sessions before you publish the changes.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="63d63-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="63d63-109">In This Section</span></span>

  - [<span data-ttu-id="63d63-110">Lync Server 2013 での音声ルート構成ファイルのエクスポート</span><span class="sxs-lookup"><span data-stu-id="63d63-110">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [<span data-ttu-id="63d63-111">Lync Server 2013 でのボイスルート構成ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="63d63-111">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="63d63-112">関連情報</span><span class="sxs-lookup"><span data-stu-id="63d63-112">Related Sections</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

