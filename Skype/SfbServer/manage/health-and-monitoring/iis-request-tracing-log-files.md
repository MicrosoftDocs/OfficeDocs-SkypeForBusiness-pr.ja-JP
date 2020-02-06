---
title: Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: '概要: Skype for Business Server 2015 のモバイルサービス (Mcx) とレガシクライアントのサポートについて説明します。'
ms.openlocfilehash: 982e5842499e5cb2f6ff21ff884d1baa45075627
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817927"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="b4b41-103">Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視</span><span class="sxs-lookup"><span data-stu-id="b4b41-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b4b41-104">**概要:** レガシクライアント向けの Skype for Business Server 2015 サポートのモバイルサービス (Mcx) について説明します。</span><span class="sxs-lookup"><span data-stu-id="b4b41-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="b4b41-105">このトピックは、Lync 2010 Lync Mobile クライアントをサポートする展開のみに適用され、Mobility Service (Mcx) を対象としています。</span><span class="sxs-lookup"><span data-stu-id="b4b41-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="b4b41-106">Skype for Business Server 2019 では、従来のモバイルクライアントに対する MCX (モバイルサービス) のサポートは利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b4b41-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="b4b41-107">現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="b4b41-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="b4b41-108">MCX を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4b41-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="b4b41-109">Skype for Business Server Mobility Service (Mcx) のインターネットインフォメーションサービス (IIS) 要求トレースを有効にすると、生成されるログファイルは1日に最大 3 gb のディスク領域を消費する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b4b41-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="b4b41-110">IIS トレースログは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="b4b41-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="b4b41-111">フロントエンドサーバーを監視して、ディスク領域が不足していないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4b41-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="b4b41-112">既定では、IIS はログ ファイルを %SystemDrive%\inetpub\logs\LogFiles に格納します。</span><span class="sxs-lookup"><span data-stu-id="b4b41-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="b4b41-113">サーバー全体で IIS 要求トレースをオフにするには、コマンド ラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b4b41-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="b4b41-114">**HttpLogging**コマンドの詳細については、[コマンドリファレンス](https://go.microsoft.com/fwlink/p/?linkId=234927)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4b41-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

