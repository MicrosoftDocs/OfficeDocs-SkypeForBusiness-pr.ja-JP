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
description: '概要: 従来のクライアントに対する Skype for Business Server 2015 の Mobility Service (Mcx) のサポートについて説明します。'
ms.openlocfilehash: 5fb9e66efa468e8755fe369c3ce4f2a4b8979e57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823507"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="9b8fa-103">Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視</span><span class="sxs-lookup"><span data-stu-id="9b8fa-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9b8fa-104">**概要:** 従来のクライアントに対する Skype for Business Server 2015 の Mobility Service (Mcx) のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="9b8fa-105">このトピックは、Lync 2010 Lync Mobile クライアントのみをサポートする展開に適用され、Mobility Service (Mcx) を対象としています。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="9b8fa-106">従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="9b8fa-107">現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="9b8fa-108">MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="9b8fa-109">Skype for Business Server Mobility Service (Mcx) のインターネット インフォメーション サービス (IIS) 要求トレースを有効にすると、生成されるログ ファイルが 1 日あたり最大 3 GB のディスク領域を消費する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="9b8fa-110">IIS トレース ログは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="9b8fa-111">フロントエンド サーバーを監視して、ディスク領域が使い切れなことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="9b8fa-112">既定では、IIS はログ ファイルを %SystemDrive%\inetpub\logs\LogFiles に格納します。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="9b8fa-113">サーバー全体で IIS 要求トレースをオフにするには、コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="9b8fa-114">**httpLogging コマンドの詳細については、** コマンド リファレンス [を参照してください](https://go.microsoft.com/fwlink/p/?linkId=234927)。</span><span class="sxs-lookup"><span data-stu-id="9b8fa-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

