---
title: Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: '概要: は、レガシ クライアントのサーバー 2015 のビジネスをサポートするため、Skype では、モビリティ サービス (Mcx) について説明します。'
ms.openlocfilehash: 51913162603203333cd201c64ed21770825bdaf7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="cbc21-103">Skype for Business Server 2015 での IIS 要求トレース ログ ファイルの監視</span><span class="sxs-lookup"><span data-stu-id="cbc21-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cbc21-104">**の概要:**ビジネス サーバー 2015 のレガシ クライアントをサポートするため、Skype では、モビリティ サービス (Mcx) について説明します。</span><span class="sxs-lookup"><span data-stu-id="cbc21-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="cbc21-105">このトピックは、Lync 2010 Lync Mobile クライアントをサポートする展開のみに適用され、Mobility Service (Mcx) を対象としています。</span><span class="sxs-lookup"><span data-stu-id="cbc21-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>
  
<span data-ttu-id="cbc21-106">Skype のインターネット インフォメーション サービス (IIS) の要求のトレースを有効にビジネス サーバー移動サービス (Mcx) のときに生成されるログ ファイルは最大 3 ギガバイトの空き容量が 1 日を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cbc21-106">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="cbc21-107">IIS トレース ログは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="cbc21-107">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="cbc21-108">ディスクの空き領域が不足実行されないことになっていることを確認するのにはフロント エンド サーバーを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbc21-108">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="cbc21-109">既定では、IIS はログ ファイルを %SystemDrive%\inetpub\logs\LogFiles に格納します。</span><span class="sxs-lookup"><span data-stu-id="cbc21-109">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="cbc21-110">サーバー全体で IIS 要求トレースをオフにするには、コマンド ラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="cbc21-110">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="cbc21-111">詳細については、 **httpLogging**コマンドは、[コマンドのリファレンス](https://go.microsoft.com/fwlink/p/?linkId=234927)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbc21-111">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

