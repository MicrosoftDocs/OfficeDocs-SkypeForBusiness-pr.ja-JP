---
title: 'Lync Server 2013: アナウンスアプリケーションの展開プロセス'
description: 'Lync Server 2013: アナウンスアプリケーションの展開プロセス。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 559977c32f63fae312164b5b0c36698fa13afb09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550993"
---
# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="4aba5-103">Lync Server 2013 のアナウンスアプリケーションの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="4aba5-103">Deployment process for the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4aba5-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4aba5-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4aba5-105">このセクションでは、アナウンスメントアプリケーションの展開に必要な手順の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="4aba5-105">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="4aba5-106">アナウンスを構成する前に、エンタープライズ Voip を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4aba5-106">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="4aba5-107">[] エンタープライズ Voip を展開すると、アナウンスメントアプリケーションに必要なコンポーネントがインストールされ、有効になります。</span><span class="sxs-lookup"><span data-stu-id="4aba5-107">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="4aba5-108">アナウンスの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="4aba5-108">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4aba5-109">フェーズ</span><span class="sxs-lookup"><span data-stu-id="4aba5-109">Phase</span></span></th>
<th><span data-ttu-id="4aba5-110">手順</span><span class="sxs-lookup"><span data-stu-id="4aba5-110">Steps</span></span></th>
<th><span data-ttu-id="4aba5-111">ロール</span><span class="sxs-lookup"><span data-stu-id="4aba5-111">Roles</span></span></th>
<th><span data-ttu-id="4aba5-112">展開のドキュメント</span><span class="sxs-lookup"><span data-stu-id="4aba5-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4aba5-113">アナウンス設定を構成する</span><span class="sxs-lookup"><span data-stu-id="4aba5-113">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4aba5-114">音声ファイルを録音およびアップロードするか、音声合成 (TTS) を使用してアナウンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="4aba5-114">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="4aba5-115">割り当てられていない番号の範囲を構成し、適切なアナウンスに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="4aba5-115">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4aba5-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="4aba5-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="4aba5-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="4aba5-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="4aba5-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4aba5-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="4aba5-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4aba5-119">CsAdministrator</span></span></p>
<p><span data-ttu-id="4aba5-120">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="4aba5-120">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4aba5-121"><a href="lync-server-2013-create-an-announcement.md">Lync Server 2013 でアナウンスを作成する</a></span><span class="sxs-lookup"><span data-stu-id="4aba5-121"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="4aba5-122"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Lync Server 2013 で割り当てられていない番号の表を構成する</a></span><span class="sxs-lookup"><span data-stu-id="4aba5-122"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aba5-123">アナウンスの展開の確認</span><span class="sxs-lookup"><span data-stu-id="4aba5-123">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="4aba5-124">アナウンスを聞いてテストし、構成が予想どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="4aba5-124">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="4aba5-125"><a href="lync-server-2013-optional-verify-announcement-deployment.md">オプションLync Server 2013 でのアナウンスの展開の確認</a></span><span class="sxs-lookup"><span data-stu-id="4aba5-125"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

