---
title: 'Lync Server 2013: 割り当てられていない番号用のアナウンスの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring announcements for unassigned numbers
ms:assetid: 45633dd3-78de-4934-867e-33969fc25368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425944(v=OCS.15)
ms:contentKeyID: 48184035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52d7e8ad1aa4fcfe3db9aabee61e317810707194
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="61551-102">Lync Server 2013 での、割り当てられていない番号用のアナウンスの構成</span><span class="sxs-lookup"><span data-stu-id="61551-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61551-103">_**最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="61551-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="61551-104">アナウンスメントアプリケーションは、割り当てられていない拡張子 (組織に対して有効であり、ユーザーまたは電話に割り当てられていない拡張機能) への呼び出しを構成できるエンタープライズ Voip 機能です。</span><span class="sxs-lookup"><span data-stu-id="61551-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="61551-105">たとえば、割り当てられていない番号に通話があった場合にメッセージを再生したり、別の通話先に転送したり、その両方を行ったりするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="61551-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="61551-106">お知らせアプリケーションは、エンタープライズボイスの展開時に、フロントエンドサーバーまたは Standard Edition サーバー上の応答グループアプリケーションの機能としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="61551-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="61551-107">オーディオ ファイルをアップロードするか音声合成 (TTS) を構成して、割り当てられていない番号の表を構成し、アナウンスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61551-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="61551-108">このセクションでは、Lync Server のお知らせを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="61551-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="61551-109">ここでは、お知らせに関連する計画セクションを既に読んでいて、enterprise Edition サーバーまたはエンタープライズ Voip サーバーを展開していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="61551-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="61551-110">このセクション中</span><span class="sxs-lookup"><span data-stu-id="61551-110">In This Section</span></span>

  - [<span data-ttu-id="61551-111">Lync Server 2013 のアナウンスの構成の前提条件と役割</span><span class="sxs-lookup"><span data-stu-id="61551-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="61551-112">Lync Server 2013 のアナウンスメントアプリケーションの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="61551-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="61551-113">Lync Server 2013 でお知らせを作成する</span><span class="sxs-lookup"><span data-stu-id="61551-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="61551-114">Lync Server 2013 での割り当てられていない番号の表の構成</span><span class="sxs-lookup"><span data-stu-id="61551-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="61551-115">省略Lync Server 2013 でのアナウンスメントの展開を確認する</span><span class="sxs-lookup"><span data-stu-id="61551-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="61551-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="61551-116">See Also</span></span>


[<span data-ttu-id="61551-117">Lync Server 2013 の通話管理機能の計画</span><span class="sxs-lookup"><span data-stu-id="61551-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

