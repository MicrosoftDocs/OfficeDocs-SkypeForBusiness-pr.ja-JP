---
title: フロントエンドと AV MCU の関連付け
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithAvMcuPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 314e3b0b-9ca7-423b-9c8e-80eb6013d36f
description: A/V 会議を使用すると、ユーザー間の音声およびビデオのリアルタイム通信が可能になります (つまり、電話会議のヘッドセットやビデオ会議用の web カメラなど、適切なクライアントデバイスがある場合)。 展開で会議がサポートされていて、web 会議と A/V の両方の会議を有効にしている場合は、1つ以上のスタンドアロン A/V 会議サーバー (A/V 会議プール) を展開することができます。 スタンドアロンの A/V 会議サーバーを展開するためのオプションを選択した場合、トポロジビルダーで定義する必要があります。
ms.openlocfilehash: 81adb2e51cf026d189315abb45aebaf53bd38670
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820409"
---
# <a name="associate-front-end-with-av-mcu"></a><span data-ttu-id="6f74e-105">フロントエンドと AV MCU の関連付け</span><span class="sxs-lookup"><span data-stu-id="6f74e-105">Associate Front End With AV MCU</span></span>
 
<span data-ttu-id="6f74e-106">A/V 会議を使用すると、ユーザー間の音声およびビデオのリアルタイム通信が可能になります (つまり、電話会議のヘッドセットやビデオ会議用の web カメラなど、適切なクライアントデバイスがある場合)。</span><span class="sxs-lookup"><span data-stu-id="6f74e-106">A/V Conferencing enables real-time audio and video communications between your users (that is, if they have appropriate client devices, such as headsets for audio conferences, and webcams for video conferences).</span></span> <span data-ttu-id="6f74e-107">展開で会議がサポートされていて、web 会議と A/V の両方の会議を有効にしている場合は、1つ以上のスタンドアロン A/V 会議サーバー (A/V 会議プール) を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="6f74e-107">If your deployment supports conferencing and you enable both web conferencing and A/V Conferencing, you can collocate the A/V Conferencing Server with the Front End Server), or you can deploy one or more stand-alone A/V Conferencing Servers (A/V Conferencing pool).</span></span> <span data-ttu-id="6f74e-108">スタンドアロンの A/V 会議サーバーを展開するためのオプションを選択した場合、トポロジビルダーで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f74e-108">If you choose the option to deploy a stand-alone A/V Conferencing Server, you must define it in Topology Builder.</span></span>
  
<span data-ttu-id="6f74e-109">1つのサイトのすべてのプールと複数のセントラルサイトのプールは、使用頻度が A/V 会議サーバーの容量を超えていない場合は、同じ A/V 会議サーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6f74e-109">All pools at a site and the pools of multiple central sites can use the same A/V Conferencing Server, if usage does not exceed the capacity of the A/V Conferencing Server.</span></span> 
  

