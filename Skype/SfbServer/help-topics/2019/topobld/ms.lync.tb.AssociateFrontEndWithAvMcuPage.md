---
title: フロントエンドと AV MCU の関連付け
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithAvMcuPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 314e3b0b-9ca7-423b-9c8e-80eb6013d36f
ROBOTS: NOINDEX, NOFOLLOW
description: 音声ビデオ会議を使用すると、ユーザー間でリアルタイムの音声通信およびビデオ通信を実現できます (電話会議用のハンドセット、ビデオ会議用の Web カメラなど、適切なクライアント デバイスを使用している場合)。 展開で会議をサポートしており、Web 会議と音声ビデオ会議の両方を有効にしている場合、音声ビデオ会議サーバーのフロントエンド サーバーとの併置や、1 つ以上のスタンドアロンの音声ビデオ会議サーバー (音声ビデオ会議プール) の展開ができます。 スタンドアロンの音声ビデオ会議サーバーを展開するオプションを選択した場合は、トポロジ ビルダーで定義する必要があります。
ms.openlocfilehash: 24aec4c97b1d9a0f30ef8e775d04b93d7de4fec2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811427"
---
# <a name="associate-front-end-with-av-mcu"></a><span data-ttu-id="b53eb-105">フロント エンドと AV MCU の関連付け</span><span class="sxs-lookup"><span data-stu-id="b53eb-105">Associate Front End With AV MCU</span></span>
 
<span data-ttu-id="b53eb-106">音声ビデオ会議を使用すると、ユーザー間でリアルタイムの音声通信およびビデオ通信を実現できます (電話会議用のハンドセット、ビデオ会議用の Web カメラなど、適切なクライアント デバイスを使用している場合)。</span><span class="sxs-lookup"><span data-stu-id="b53eb-106">A/V Conferencing enables real-time audio and video communications between your users (that is, if they have appropriate client devices, such as headsets for audio conferences, and webcams for video conferences).</span></span> <span data-ttu-id="b53eb-107">展開で会議をサポートしており、Web 会議と音声ビデオ会議の両方を有効にしている場合、音声ビデオ会議サーバーのフロントエンド サーバーとの併置や、1 つ以上のスタンドアロンの音声ビデオ会議サーバー (音声ビデオ会議プール) の展開ができます。</span><span class="sxs-lookup"><span data-stu-id="b53eb-107">If your deployment supports conferencing and you enable both web conferencing and A/V Conferencing, you can collocate the A/V Conferencing Server with the Front End Server), or you can deploy one or more stand-alone A/V Conferencing Servers (A/V Conferencing pool).</span></span> <span data-ttu-id="b53eb-108">スタンドアロンの音声ビデオ会議サーバーを展開するオプションを選択した場合は、トポロジ ビルダーで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b53eb-108">If you choose the option to deploy a stand-alone A/V Conferencing Server, you must define it in Topology Builder.</span></span>
  
<span data-ttu-id="b53eb-109">1 つのサイトのすべてのプールと複数の中央サイトのプールは、利用状況が音声ビデオ会議サーバーの容量を超えない場合に、同じ音声ビデオ会議サーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b53eb-109">All pools at a site and the pools of multiple central sites can use the same A/V Conferencing Server, if usage does not exceed the capacity of the A/V Conferencing Server.</span></span> 
  

