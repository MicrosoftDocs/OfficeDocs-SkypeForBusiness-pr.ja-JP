---
title: 'Lync Server 2013: 割り当てられていない番号のアナウンスの構成'
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
ms.openlocfilehash: c352e7a4f062e6a9a1aab0bf52289c20102cc7fe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517554"
---
# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="11d4c-102">Lync Server 2013 で割り当てられていない番号のアナウンスを構成する</span><span class="sxs-lookup"><span data-stu-id="11d4c-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11d4c-103">_**トピックの最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="11d4c-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="11d4c-104">アナウンスメントアプリケーションは、割り当てられていない内線番号への呼び出しに対して行われる処理を構成できるエンタープライズ Voip 機能です (組織に対して有効になっているが、個人または電話には割り当てられません)。</span><span class="sxs-lookup"><span data-stu-id="11d4c-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="11d4c-105">たとえば、割り当てられていない番号に通話があった場合にメッセージを再生したり、別の通話先に転送したり、その両方を行ったりするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="11d4c-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="11d4c-106">アナウンスアプリケーションは、エンタープライズ Voip を展開するときにフロントエンドサーバーまたは Standard Edition サーバー上の応答グループアプリケーションの機能としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="11d4c-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="11d4c-107">オーディオ ファイルをアップロードするか音声合成 (TTS) を構成して、割り当てられていない番号の表を構成し、アナウンスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11d4c-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="11d4c-108">このセクションでは、Lync Server アナウンスの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="11d4c-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="11d4c-109">お知らせに関連する計画セクション、およびエンタープライズ Voip を使用した Enterprise Edition サーバーまたは Standard Edition サーバーを既に読んでいることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="11d4c-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="11d4c-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="11d4c-110">In This Section</span></span>

  - [<span data-ttu-id="11d4c-111">Lync Server 2013 でのアナウンスの構成の前提条件と役割</span><span class="sxs-lookup"><span data-stu-id="11d4c-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="11d4c-112">Lync Server 2013 のアナウンスアプリケーションの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="11d4c-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="11d4c-113">Lync Server 2013 でアナウンスを作成する</span><span class="sxs-lookup"><span data-stu-id="11d4c-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="11d4c-114">Lync Server 2013 で割り当てられていない番号の表を構成する</span><span class="sxs-lookup"><span data-stu-id="11d4c-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="11d4c-115">オプションLync Server 2013 でのアナウンスの展開の確認</span><span class="sxs-lookup"><span data-stu-id="11d4c-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="11d4c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="11d4c-116">See Also</span></span>


[<span data-ttu-id="11d4c-117">Lync Server 2013 での通話管理機能の計画</span><span class="sxs-lookup"><span data-stu-id="11d4c-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

