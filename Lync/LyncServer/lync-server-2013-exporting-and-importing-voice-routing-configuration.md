---
title: 'Lync Server 2013: 音声ルーティング構成のエクスポートとインポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exporting and importing voice routing configuration
ms:assetid: c9b78622-5725-43b0-9ee1-5b82b1e1c8eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398836(v=OCS.15)
ms:contentKeyID: 48185398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cb02759cb4fa7cf9c979ef06b594f78a6b253c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="86969-102">Lync Server 2013 での音声ルーティング構成のエクスポートとインポート</span><span class="sxs-lookup"><span data-stu-id="86969-102">Exporting and importing voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86969-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="86969-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="86969-104">音声ルーティング構成を公開せずに保存する場合は、次の手順に従って、Lync Server コントロールパネルの構成のエクスポートとインポートのコマンドを使用して、ボイスルーティング構成のスナップショットを保存して取得します。</span><span class="sxs-lookup"><span data-stu-id="86969-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="86969-105">ボイスルーティング構成ファイル (vcfg) をインポートするときに、その間もサーバー上の音声ルーティング構成に変更が加えられた場合、Lync Server コントロールパネルの**ボイスルーティング**グループのページに、音声ルーティングのコミットしていない変更。</span><span class="sxs-lookup"><span data-stu-id="86969-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="86969-106">こうした未確定の変更は、調整が必要な 2 つの構成間の相違です。</span><span class="sxs-lookup"><span data-stu-id="86969-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="86969-107">[<STRONG>ボイスルーティング</STRONG>] グループ内の任意のページの設定に対してコミットされていない変更を加えた場合、変更はエクスポートされた音声構成ファイル (vcfg) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="86969-107">If you have made any uncommitted changes to the settings on any page within the <STRONG>Voice Routing</STRONG> group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="86969-108">これにより、複数の Lync Server コントロールパネルセッション中に、変更を公開する前に、ボイスルーティング構成の変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="86969-108">This enables you to make voice routing configuration changes during multiple Lync Server Control Panel sessions before you publish the changes.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="86969-109">このセクション中</span><span class="sxs-lookup"><span data-stu-id="86969-109">In This Section</span></span>

  - [<span data-ttu-id="86969-110">ボイスルート構成ファイルを Lync Server 2013 でエクスポートする</span><span class="sxs-lookup"><span data-stu-id="86969-110">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [<span data-ttu-id="86969-111">Lync Server 2013 でのボイス ルート構成ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="86969-111">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="86969-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="86969-112">Related Sections</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

