---
title: 'Lync Server 2013: 音声ルート構成ファイルのエクスポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca000e2ba0c1802d8ec97a2a9c2f361f2c0a1b68
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528384"
---
# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="2ff13-102">Lync Server 2013 での音声ルート構成ファイルのエクスポート</span><span class="sxs-lookup"><span data-stu-id="2ff13-102">Export a voice route configuration file in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ff13-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2ff13-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2ff13-104">音声ルーティング構成を公開せずに保存する場合は、次の手順に従って、Lync Server コントロールパネルの [構成のエクスポート] および [インポート] コマンドを使用して、音声ルーティング構成のスナップショットを保存および取得します。</span><span class="sxs-lookup"><span data-stu-id="2ff13-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="2ff13-105">音声ルーティング構成ファイル (vcfg) をインポートするときに、その間にサーバー上の音声ルーティング構成に変更が加えられた場合、Lync Server コントロールパネルの [ **音声ルーティング** ] グループのページには、音声ルーティングにコミットされていない変更があることが示されます。</span><span class="sxs-lookup"><span data-stu-id="2ff13-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="2ff13-106">これらの未確定の変更は、調整が必要な 2 つの構成間の相違です。</span><span class="sxs-lookup"><span data-stu-id="2ff13-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="2ff13-107">グループ内の任意のページの設定に対して変更をコミットしていない場合、変更はエクスポートされた音声構成ファイル (vcfg) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="2ff13-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="2ff13-108">これにより、変更を公開する前に、複数のセッションで音声ルーティング構成の変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2ff13-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="2ff13-109">音声ルーティング構成をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="2ff13-109">To export a voice routing configuration</span></span>

1.  <span data-ttu-id="2ff13-110">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2ff13-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="2ff13-111">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ff13-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="2ff13-112">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2ff13-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2ff13-113">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ff13-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2ff13-114">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ff13-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="2ff13-115">[**アクション**] メニューの [**構成のエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ff13-115">On the **Actions** menu, click **Export configuration**.</span></span>

5.  <span data-ttu-id="2ff13-116">場所とファイル名を指定し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ff13-116">Specify a location and file name, and then click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2ff13-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ff13-117">See Also</span></span>


[<span data-ttu-id="2ff13-118">Lync Server 2013 でのボイスルート構成ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="2ff13-118">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

