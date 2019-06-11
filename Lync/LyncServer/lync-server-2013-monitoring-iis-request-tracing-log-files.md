---
title: 'Lync Server 2013: IIS 要求のトレースログファイルを監視する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1257e350dd7695bf132959d6b4cde4843192e41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a><span data-ttu-id="3c865-102">Lync Server 2013 で IIS 要求トレースのログファイルを監視する</span><span class="sxs-lookup"><span data-stu-id="3c865-102">Monitoring IIS request tracing log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c865-103">_**最終更新日:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="3c865-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

<span data-ttu-id="3c865-104">Lync Server Mobility Service (Mcx) のインターネットインフォメーションサービス (IIS) 要求のトレースを有効にすると、生成されたログファイルは1日に最大 3 gb のディスク領域を消費する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c865-104">When you enable Internet Information Services (IIS) request tracing for the Lync Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="3c865-105">IIS トレースログは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="3c865-105">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="3c865-106">フロントエンドサーバーを監視して、ディスク領域が不足していないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c865-106">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span>

<span data-ttu-id="3c865-107">既定では、IIS は、ログファイルを% SystemDrive\\%\\inetpub\\logs ログログに保存します。</span><span class="sxs-lookup"><span data-stu-id="3c865-107">By default, IIS stores the log files at %SystemDrive%\\inetpub\\logs\\LogFiles.</span></span>

<span data-ttu-id="3c865-108">サーバー全体で IIS 要求トレースをオフにするには、コマンド ラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3c865-108">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

<span data-ttu-id="3c865-109">**HttpLogging**コマンドの詳細については[http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927)、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c865-109">For details about the **httpLogging** command, see [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

