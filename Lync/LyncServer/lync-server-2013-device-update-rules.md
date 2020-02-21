---
title: 'Lync Server 2013: デバイス更新ルール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update rules
ms:assetid: a2f7e293-3342-4566-9605-410cb95f3b3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994062(v=OCS.15)
ms:contentKeyID: 51803973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1ec593c264a1630274e83e8a7de1d193b8e5cbf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="12667-102">Lync Server 2013 のデバイス更新ルール</span><span class="sxs-lookup"><span data-stu-id="12667-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12667-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="12667-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="12667-104">Microsoft では、Lync Phone Edition 用のデバイスファームウェア更新プログラムの新しいセットを定期的にリリースしています。</span><span class="sxs-lookup"><span data-stu-id="12667-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="12667-105">*デバイス更新ルール*は、ファームウェアの更新プログラムをハードウェアデバイス (電話機および Lync Phone Edition を実行している他のデバイス) に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="12667-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="12667-106">最新のデバイス更新ルールセットを取得するには、Microsoft web サイトの [ヘルプとサポート] ページに移動し、「Phone Edition」を検索します。</span><span class="sxs-lookup"><span data-stu-id="12667-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="12667-107">更新プログラムパッケージをダウンロードし、更新プログラムをアップロードするコンピューター上のフォルダーにファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="12667-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="12667-108">ファイルが抽出されたら、抽出されたで見つかったデバイス更新ルールをインポートします。CAB ファイル (名前は UCUpdates. .cab)。</span><span class="sxs-lookup"><span data-stu-id="12667-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="12667-109">次に、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットを使用して、組織のデバイスに対するこれらのルールを表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="12667-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="12667-110">次のトピックでは、デバイス更新ルールをインポート、表示、および管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="12667-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="12667-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="12667-111">In This Section</span></span>

  - [<span data-ttu-id="12667-112">Lync Server 2013 でのデバイス更新ルールに関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="12667-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="12667-113">Lync Server 2013 でのデバイス更新ルールのインポート</span><span class="sxs-lookup"><span data-stu-id="12667-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="12667-114">Lync Server 2013 でのデバイス更新ルールの承認</span><span class="sxs-lookup"><span data-stu-id="12667-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="12667-115">Lync Server 2013 のデバイス更新ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="12667-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="12667-116">Lync Server 2013 でのデバイス更新ルールのリセット</span><span class="sxs-lookup"><span data-stu-id="12667-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="12667-117">Lync Server 2013 でのデバイス更新ルールの復元</span><span class="sxs-lookup"><span data-stu-id="12667-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

