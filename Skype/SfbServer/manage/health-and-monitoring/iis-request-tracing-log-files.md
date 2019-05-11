---
title: Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: '概要: は、レガシ クライアントのサーバー 2015 のビジネスをサポートするため、Skype では、モビリティ サービス (Mcx) について説明します。'
ms.openlocfilehash: cbb064cf868a557c5f30871df8f7ee4b60242679
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926621"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="fb0b8-103">Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視</span><span class="sxs-lookup"><span data-stu-id="fb0b8-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fb0b8-104">**の概要:** ビジネス サーバー 2015 のレガシ クライアントをサポートするため、Skype では、モビリティ サービス (Mcx) について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb0b8-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="fb0b8-105">このトピックは、Lync 2010 Lync Mobile クライアントをサポートする展開のみに適用され、Mobility Service (Mcx) を対象としています。</span><span class="sxs-lookup"><span data-stu-id="fb0b8-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="fb0b8-106">従来のモバイル クライアント用の MCX (移動サービス) サポートがビジネス サーバー 2019 の Skype で利用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="fb0b8-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="fb0b8-107">ビジネスのモバイル クライアントのすべての現在 Skype は、インスタント メッセージング (IM)、プレゼンス、および取引先担当者をサポートするために既にユニファイド コミュニケーション Web API (UCWA) を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb0b8-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="fb0b8-108">MCX を使用する従来のクライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb0b8-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="fb0b8-109">Skype のインターネット インフォメーション サービス (IIS) の要求のトレースを有効にビジネス サーバー移動サービス (Mcx) のときに生成されるログ ファイルは最大 3 ギガバイトの空き容量が 1 日を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fb0b8-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="fb0b8-110">IIS トレース ログは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="fb0b8-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="fb0b8-111">ディスクの空き領域が不足実行されないことになっていることを確認するのにはフロント エンド サーバーを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb0b8-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="fb0b8-112">既定では、IIS はログ ファイルを %SystemDrive%\inetpub\logs\LogFiles に格納します。</span><span class="sxs-lookup"><span data-stu-id="fb0b8-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="fb0b8-113">サーバー全体で IIS 要求トレースをオフにするには、コマンド ラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fb0b8-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="fb0b8-114">詳細については、 **httpLogging**コマンドは、[コマンドのリファレンス](https://go.microsoft.com/fwlink/p/?linkId=234927)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb0b8-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

