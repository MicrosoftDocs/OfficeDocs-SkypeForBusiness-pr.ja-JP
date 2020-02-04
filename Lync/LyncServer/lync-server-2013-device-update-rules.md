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
ms.openlocfilehash: 4912497f1c8481d44b02a0213e01a0e8908ebfa2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="cb281-102">Lync Server 2013 のデバイス更新ルール</span><span class="sxs-lookup"><span data-stu-id="cb281-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb281-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="cb281-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="cb281-104">Microsoft は定期的に、Lync Phone Edition 用の新しいデバイスファームウェア更新プログラムセットをリリースします。</span><span class="sxs-lookup"><span data-stu-id="cb281-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="cb281-105">*デバイス更新ルール*は、Lync Phone Edition を実行している電話やその他のデバイスなどのファームウェア更新プログラムをハードウェアデバイスに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="cb281-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="cb281-106">最新のデバイス更新ルールのセットを取得するには、Microsoft web サイトの [ヘルプとサポート] ページに移動して、"Phone Edition" を検索します。</span><span class="sxs-lookup"><span data-stu-id="cb281-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="cb281-107">更新プログラムパッケージをダウンロードし、更新プログラムをアップロードするコンピューター上のフォルダーにファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="cb281-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="cb281-108">ファイルを抽出した後、展開されたデバイス更新ルールをインポートします。CAB ファイル ("UCUpdates .cab" という名前が付いています)。</span><span class="sxs-lookup"><span data-stu-id="cb281-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="cb281-109">次に、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットを使用して、組織のデバイスのこれらのルールを表示し、管理します。</span><span class="sxs-lookup"><span data-stu-id="cb281-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="cb281-110">次のトピックでは、デバイス更新ルールをインポート、表示、管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cb281-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cb281-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="cb281-111">In This Section</span></span>

  - [<span data-ttu-id="cb281-112">Lync Server 2013 でのデバイス更新ルールに関する情報を確認する</span><span class="sxs-lookup"><span data-stu-id="cb281-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="cb281-113">Lync Server 2013 でデバイス更新ルールをインポートする</span><span class="sxs-lookup"><span data-stu-id="cb281-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="cb281-114">Lync Server 2013 でデバイス更新ルールを承認する</span><span class="sxs-lookup"><span data-stu-id="cb281-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="cb281-115">Lync Server 2013 でデバイス更新ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="cb281-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="cb281-116">Lync Server 2013 でのデバイス更新ルールのリセット</span><span class="sxs-lookup"><span data-stu-id="cb281-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="cb281-117">Lync Server 2013 でデバイス更新ルールを復元する</span><span class="sxs-lookup"><span data-stu-id="cb281-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

