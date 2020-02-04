---
title: 'Lync Server 2013: アナウンスメントアプリケーションの展開プロセス'
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
ms.openlocfilehash: dcb56f197a32403d1207cf0a15d47e0459fc41bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="4a8d3-102">Lync Server 2013 のアナウンスメントアプリケーションの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="4a8d3-102">Deployment process for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a8d3-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4a8d3-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4a8d3-104">このセクションでは、アナウンスメントアプリケーションの展開に関連する手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="4a8d3-104">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="4a8d3-105">お知らせを構成する前に、エンタープライズボイスを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8d3-105">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="4a8d3-106">[エンタープライズ Voip] を展開すると、アナウンスメントアプリケーションで必要なコンポーネントがインストールされて有効になります。</span><span class="sxs-lookup"><span data-stu-id="4a8d3-106">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="4a8d3-107">アナウンスの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="4a8d3-107">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a8d3-108">フェーズ</span><span class="sxs-lookup"><span data-stu-id="4a8d3-108">Phase</span></span></th>
<th><span data-ttu-id="4a8d3-109">手順</span><span class="sxs-lookup"><span data-stu-id="4a8d3-109">Steps</span></span></th>
<th><span data-ttu-id="4a8d3-110">役割</span><span class="sxs-lookup"><span data-stu-id="4a8d3-110">Roles</span></span></th>
<th><span data-ttu-id="4a8d3-111">「展開」のドキュメント</span><span class="sxs-lookup"><span data-stu-id="4a8d3-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a8d3-112">アナウンス設定の構成</span><span class="sxs-lookup"><span data-stu-id="4a8d3-112">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4a8d3-113">オーディオ ファイルをレコーディングして読み込むか、音声合成 (TTS) を使用して、アナウンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a8d3-113">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="4a8d3-114">割り当てられていない番号の表で、割り当てられていない番号の範囲を構成して、適切なアナウンスに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="4a8d3-114">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4a8d3-115">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="4a8d3-115">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="4a8d3-116">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="4a8d3-116">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="4a8d3-117">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4a8d3-117">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="4a8d3-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4a8d3-118">CsAdministrator</span></span></p>
<p><span data-ttu-id="4a8d3-119">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="4a8d3-119">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4a8d3-120"><a href="lync-server-2013-create-an-announcement.md">Lync Server 2013 でお知らせを作成する</a></span><span class="sxs-lookup"><span data-stu-id="4a8d3-120"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="4a8d3-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Lync Server 2013 での割り当てられていない番号の表の構成</a></span><span class="sxs-lookup"><span data-stu-id="4a8d3-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a8d3-122">アナウンスの展開の確認</span><span class="sxs-lookup"><span data-stu-id="4a8d3-122">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="4a8d3-123">アナウンスを聞いてテストし、構成が予想どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="4a8d3-123">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="4a8d3-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">省略Lync Server 2013 でのアナウンスメントの展開を確認する</a></span><span class="sxs-lookup"><span data-stu-id="4a8d3-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

