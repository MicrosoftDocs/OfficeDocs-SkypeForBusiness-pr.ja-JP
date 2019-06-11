---
title: 'Lync Server 2013: バックアップの場所を設定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up a backup location
ms:assetid: 006732eb-3d44-414d-8010-227a855caa93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202158(v=OCS.15)
ms:contentKeyID: 51541440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6d8f91af650e68348a35e9f485f5ca5f54093fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="307d5-102">Lync Server 2013 のバックアップ場所の設定</span><span class="sxs-lookup"><span data-stu-id="307d5-102">Setting up a backup location for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="307d5-103">_**最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="307d5-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="307d5-104">Lync Server の最初のバックアップを取る前に、バックアップを保存して維持するために必要なハードウェアとソフトウェアをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="307d5-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="307d5-105">必要に応じてメディアとコンテンツへのアクセスを取得し、バックアップする各サーバーとバックアップメディアの間にネットワーク接続を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="307d5-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="307d5-106">使用するメディアと場所は、バックアップと復元の戦略で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="307d5-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="307d5-107">定期的なバックアップに使用する場所はローカルまたはリモートのどちらでもかまいませんが、セキュリティで保護されている必要があります。また、バックアップと復元の両方でアクセス可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="307d5-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="307d5-108">実際の場所を使用して、プライマリサイトの致命的なイベントから保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="307d5-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="307d5-109">個々のコンポーネントをセットアップしてテストしたら、各サーバーからバックアップのアクセシビリティを確認します。</span><span class="sxs-lookup"><span data-stu-id="307d5-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

