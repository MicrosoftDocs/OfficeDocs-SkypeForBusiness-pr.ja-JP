---
title: Lync Server 2010 用のレジストラー設定の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 弾力性の設定を編集し、次のプロパティを構成します。
ms.openlocfilehash: d02462b03b7255860695e373af276a69d92956e0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910250"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="9bc4c-103">Lync Server 2010 用のレジストラー設定の展開</span><span class="sxs-lookup"><span data-stu-id="9bc4c-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="9bc4c-104">**弾力性**の設定を編集し、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9bc4c-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="9bc4c-105">**関連バックアップ レジストラー プール**をリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="9bc4c-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="9bc4c-106">必要に応じて、**自動フェイル オーバーおよびフェイル バック音声**のチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="9bc4c-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="9bc4c-107">**音声障害検出の間隔 (秒)** と**音声のフェイル バックの間隔 (秒)** を構成します。</span><span class="sxs-lookup"><span data-stu-id="9bc4c-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="9bc4c-108">既定では、間隔は、音声障害を検出するための 120 秒ボイスのフェイル バックの 240 秒です。</span><span class="sxs-lookup"><span data-stu-id="9bc4c-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="9bc4c-109">復元が期待どおりに動作するためには、フェイル オーバーとフェイル バックの間隔を定義する秒数を慎重にテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bc4c-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="9bc4c-110">間隔を低に設定する (つまりより小さい 120 秒) や、フェイル オーバーとフェイル バックの設定が非常に密接に実際のフェールオーバーおよびフェールバックが期待どおりに動作していません。</span><span class="sxs-lookup"><span data-stu-id="9bc4c-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="9bc4c-111">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="9bc4c-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="9bc4c-112">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9bc4c-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="9bc4c-113">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="9bc4c-113">**Help** Displays this help screen.</span></span>
  

