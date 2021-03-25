---
title: Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: '概要: 従来のクライアントに対する Skype for Business Server 2015 サポートのモビリティ サービス (Mcx) について説明します。'
ms.openlocfilehash: 7d0d15b4c3db3d768117d73ed610b38c7a819196
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118636"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="fee77-103">Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視</span><span class="sxs-lookup"><span data-stu-id="fee77-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fee77-104">**概要:** 従来のクライアントに対する Skype for Business Server 2015 サポートのモビリティ サービス (Mcx) について説明します。</span><span class="sxs-lookup"><span data-stu-id="fee77-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="fee77-105">このトピックは、Lync 2010 Lync Mobile クライアントのみをサポートする展開に適用され、モビリティ サービス (Mcx) を対象としています。</span><span class="sxs-lookup"><span data-stu-id="fee77-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="fee77-106">従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="fee77-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="fee77-107">現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fee77-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="fee77-108">MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fee77-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="fee77-109">Skype for Business Server Mobility Service (Mcx) のインターネット インフォメーション サービス (IIS) 要求トレースを有効にすると、生成されるログ ファイルは 1 日に最大 3 ギガバイトのディスク領域を消費できます。</span><span class="sxs-lookup"><span data-stu-id="fee77-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="fee77-110">IIS トレース ログは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="fee77-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="fee77-111">フロント エンド サーバーを監視して、ディスク領域が使い切れなか確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fee77-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="fee77-112">既定では、IIS はログ ファイルを %SystemDrive%\inetpub\logs\LogFiles に格納します。</span><span class="sxs-lookup"><span data-stu-id="fee77-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="fee77-113">サーバー全体で IIS 要求トレースをオフにするには、コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fee77-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="fee77-114">**httpLogging** コマンドの詳細については、コマンド リファレンス [を参照してください](/previous-versions/iis/settings-schema/aa347466(v=vs.90))。</span><span class="sxs-lookup"><span data-stu-id="fee77-114">For details about the **httpLogging** command, see [the command reference](/previous-versions/iis/settings-schema/aa347466(v=vs.90)).</span></span>
