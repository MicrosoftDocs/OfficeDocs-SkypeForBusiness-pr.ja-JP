---
title: 'Lync Server 2013: 音声ルート構成ファイルのインポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import a voice route configuration file
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48184049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35c955ade3383d79a9a69b101b23e2f5327ccb58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="0ab50-102">Lync Server 2013 でのボイスルート構成ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="0ab50-102">Import a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ab50-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0ab50-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0ab50-104">音声ルーティング構成を公開せずに保存する場合は、次の手順に従って、Lync Server コントロールパネルの [構成のエクスポート] および [インポート] コマンドを使用して、音声ルーティング構成のスナップショットを保存および取得します。</span><span class="sxs-lookup"><span data-stu-id="0ab50-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="0ab50-105">音声ルーティング構成ファイル (vcfg) をインポートするときに、その間にサーバー上の音声ルーティング構成に変更が加えられた場合、Lync Server コントロールパネルの [**音声ルーティング**] グループのページには、音声ルーティングにコミットされていない変更があることが示されます。</span><span class="sxs-lookup"><span data-stu-id="0ab50-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="0ab50-106">これらの未確定の変更は、調整が必要な 2 つの構成間の相違です。</span><span class="sxs-lookup"><span data-stu-id="0ab50-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="0ab50-107">グループ内の任意のページの設定に対して変更をコミットしていない場合、変更はエクスポートされた音声構成ファイル (vcfg) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="0ab50-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="0ab50-108">これにより、変更を公開する前に、複数のセッションで音声ルーティング構成の変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0ab50-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="0ab50-109">音声ルーティング構成をインポートするには</span><span class="sxs-lookup"><span data-stu-id="0ab50-109">To import a voice routing configuration</span></span>

1.  <span data-ttu-id="0ab50-110">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0ab50-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="0ab50-111">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab50-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="0ab50-112">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0ab50-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0ab50-113">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab50-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0ab50-114">左側のナビゲーション バーで [**音声ルーティング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ab50-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="0ab50-115">[**操作**] メニューの [**構成のインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ab50-115">On the **Actions** menu, click **Import configuration**.</span></span>

5.  <span data-ttu-id="0ab50-116">インポートする構成ファイルを検索し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ab50-116">Find the configuration file you want to import and then click **Open**.</span></span>

6.  <span data-ttu-id="0ab50-117">[**確定**] をクリックし、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ab50-117">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0ab50-118">音声構成ファイルをインポートする場合は、必ず [<STRONG>すべて確定</STRONG>] コマンドを実行して構成変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ab50-118">Whenever you import a voice configuration file, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="0ab50-119">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab50-119">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0ab50-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ab50-120">See Also</span></span>


[<span data-ttu-id="0ab50-121">Lync Server 2013 での音声ルート構成ファイルのエクスポート</span><span class="sxs-lookup"><span data-stu-id="0ab50-121">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)  
[<span data-ttu-id="0ab50-122">Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する</span><span class="sxs-lookup"><span data-stu-id="0ab50-122">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

