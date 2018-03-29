---
title: Skype for Business Server 2015 での常設チャット サービスの監視、開始、および停止
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: '概要: 開始、停止、およびビジネス サーバー 2015 の Skype で永続的なチャット サービスを監視する方法を説明します。'
ms.openlocfilehash: 47cd6daeca664f7775455818a5690232e92d4c36
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="8a009-103">Skype for Business Server 2015 での常設チャット サービスの監視、開始、および停止</span><span class="sxs-lookup"><span data-stu-id="8a009-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8a009-104">**の概要:**開始、停止、およびビジネス サーバー 2015 の Skype で永続的なチャット サービスを監視する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="8a009-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8a009-105">永続的なチャット サービスと永続的なチャットのコンプライアンス ・ サービス ビジネス サーバー トポロジの Skype の一部であることができるため監視、停止、および次のコマンドレットを使用して起動。</span><span class="sxs-lookup"><span data-stu-id="8a009-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8a009-106">get CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="8a009-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="8a009-107">詳細 Windows サービスとして実行されているビジネス サーバー 2015 コンポーネントについて、Skype に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8a009-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="8a009-108">開始 CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="8a009-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="8a009-109">サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="8a009-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="8a009-110">stop CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="8a009-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="8a009-111">サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="8a009-111">Stops the service.</span></span>  <br/> |
   
<span data-ttu-id="8a009-112">コマンドレットを使用する方法の詳細については、 [Skype ビジネス サーバー 2015 管理シェルに](../management-shell.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a009-112">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

