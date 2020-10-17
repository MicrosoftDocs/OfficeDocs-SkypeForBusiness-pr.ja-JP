---
title: 'Lync Server 2013: デバイス更新ルール'
description: 'Lync Server 2013: デバイス更新ルール。'
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
ms.openlocfilehash: bd6d34c290f4a08f67143294fcc5dd18e1acf9d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565963"
---
# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="ee0e0-103">Lync Server 2013 のデバイス更新ルール</span><span class="sxs-lookup"><span data-stu-id="ee0e0-103">Device Update rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee0e0-104">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ee0e0-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ee0e0-105">Microsoft では、Lync Phone Edition 用のデバイスファームウェア更新プログラムの新しいセットを定期的にリリースしています。</span><span class="sxs-lookup"><span data-stu-id="ee0e0-105">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="ee0e0-106">*デバイス更新ルール* は、ファームウェアの更新プログラムをハードウェアデバイス (電話機および Lync Phone Edition を実行している他のデバイス) に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="ee0e0-106">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="ee0e0-107">最新のデバイス更新ルールセットを取得するには、Microsoft web サイトの [ヘルプとサポート] ページに移動し、「Phone Edition」を検索します。</span><span class="sxs-lookup"><span data-stu-id="ee0e0-107">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="ee0e0-108">更新プログラムパッケージをダウンロードし、更新プログラムをアップロードするコンピューター上のフォルダーにファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="ee0e0-108">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="ee0e0-109">ファイルが抽出されたら、抽出されたで見つかったデバイス更新ルールをインポートします。CAB ファイル (名前 UCUpdates.cab) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ee0e0-109">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="ee0e0-110">次に、Lync Server コントロールパネルまたは Windows PowerShell コマンドレットを使用して、組織のデバイスに対するこれらのルールを表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="ee0e0-110">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="ee0e0-111">次のトピックでは、デバイス更新ルールをインポート、表示、および管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee0e0-111">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ee0e0-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ee0e0-112">In This Section</span></span>

  - [<span data-ttu-id="ee0e0-113">Lync Server 2013 でのデバイス更新ルールに関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="ee0e0-113">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="ee0e0-114">Lync Server 2013 でのデバイス更新ルールのインポート</span><span class="sxs-lookup"><span data-stu-id="ee0e0-114">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="ee0e0-115">Lync Server 2013 でのデバイス更新ルールの承認</span><span class="sxs-lookup"><span data-stu-id="ee0e0-115">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="ee0e0-116">Lync Server 2013 のデバイス更新ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="ee0e0-116">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="ee0e0-117">Lync Server 2013 でのデバイス更新ルールのリセット</span><span class="sxs-lookup"><span data-stu-id="ee0e0-117">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="ee0e0-118">Lync Server 2013 でのデバイス更新ルールの復元</span><span class="sxs-lookup"><span data-stu-id="ee0e0-118">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

