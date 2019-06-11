---
title: 'Lync Server 2013: ボイスルーティング構成ファイルをエクスポートする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d61bb4dfda9aa91191515f60b0a26b2665f31421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="f2984-102">ボイスルート構成ファイルを Lync Server 2013 でエクスポートする</span><span class="sxs-lookup"><span data-stu-id="f2984-102">Export a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2984-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f2984-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f2984-104">音声ルーティング構成を公開せずに保存する場合は、次の手順に従って、Lync Server コントロールパネルの構成のエクスポートとインポートのコマンドを使用して、ボイスルーティング構成のスナップショットを保存して取得します。</span><span class="sxs-lookup"><span data-stu-id="f2984-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="f2984-105">ボイスルーティング構成ファイル (vcfg) をインポートするときに、その間もサーバー上の音声ルーティング構成に変更が加えられた場合、Lync Server コントロールパネルの**ボイスルーティング**グループのページに、音声ルーティングのコミットしていない変更。</span><span class="sxs-lookup"><span data-stu-id="f2984-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="f2984-106">こうした未確定の変更は、調整が必要な 2 つの構成間の相違です。</span><span class="sxs-lookup"><span data-stu-id="f2984-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="f2984-107">グループ内の任意のページの設定にコミットされていない変更を加えた場合、変更はエクスポートされた音声構成ファイル (vcfg) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="f2984-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="f2984-108">これにより、変更を公開する前に、複数のセッション中にボイスルーティング構成の変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f2984-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="f2984-109">音声ルーティング構成をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="f2984-109">To export a voice routing configuration</span></span>

1.  <span data-ttu-id="f2984-110">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f2984-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f2984-111">詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2984-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f2984-112">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f2984-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f2984-113">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2984-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f2984-114">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2984-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="f2984-115">[**アクション**] メニューの [**構成のエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2984-115">On the **Actions** menu, click **Export configuration**.</span></span>

5.  <span data-ttu-id="f2984-116">場所とファイル名を指定し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2984-116">Specify a location and file name, and then click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2984-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2984-117">See Also</span></span>


[<span data-ttu-id="f2984-118">Lync Server 2013 でのボイス ルート構成ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="f2984-118">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

