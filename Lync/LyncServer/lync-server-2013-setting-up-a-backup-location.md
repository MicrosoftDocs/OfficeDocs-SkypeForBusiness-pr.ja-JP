---
title: 'Lync Server 2013: バックアップの場所の設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up a backup location
ms:assetid: 006732eb-3d44-414d-8010-227a855caa93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202158(v=OCS.15)
ms:contentKeyID: 51541440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fe9ddd835d569aca129d53de2a44e2a00b39794
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="a8a38-102">Lync Server 2013 のバックアップ場所のセットアップ</span><span class="sxs-lookup"><span data-stu-id="a8a38-102">Setting up a backup location for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8a38-103">_**トピックの最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="a8a38-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="a8a38-104">Lync Server の最初のバックアップを開始する前に、バックアップを保存および管理するために必要なハードウェアとソフトウェアをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="a8a38-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="a8a38-105">必要に応じて、メディアおよびコンテンツにアクセスできるようにし、バックアップ対象の各サーバーとバックアップ メディアの間のネットワーク接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="a8a38-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="a8a38-106">バックアップと復元の戦略では、使用するメディアと場所を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8a38-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="a8a38-107">通常のバックアップに使用する場所はローカルまたはリモートの場合がありますが、安全である必要があり、バックアップと復元の両方でアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8a38-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="a8a38-108">プライマリサイトで致命的なイベントから保護するには、リモートの場所を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a8a38-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="a8a38-109">個別のコンポーネントを設定してテストした後、各サーバーからバックアップにアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a8a38-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

