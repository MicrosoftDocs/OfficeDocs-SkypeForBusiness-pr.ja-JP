---
title: Lync Server 2010 用のレジストラー設定の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 回復性の設定を編集し、次のプロパティを構成します。
ms.openlocfilehash: 5ed1311e73ea035b7672ba75bab337c9212e8816
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282239"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="85a71-103">Lync Server 2010 用のレジストラー設定の展開</span><span class="sxs-lookup"><span data-stu-id="85a71-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="85a71-104">**回復性**の設定を編集し、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="85a71-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="85a71-105">一覧から [**関連付けられているバックアップレジストラープール**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="85a71-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="85a71-106">必要に応じて、[**自動フェールオーバーと音声のフェールバック**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="85a71-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="85a71-107">**ボイスエラー検出間隔 (sec)** と**ボイスバックの間隔 (秒)** を構成します。</span><span class="sxs-lookup"><span data-stu-id="85a71-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="85a71-108">既定では、音声の障害検出と240秒のボイスバックの間隔は120秒です。</span><span class="sxs-lookup"><span data-stu-id="85a71-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="85a71-109">フェールオーバーとフェールバックの間隔に対して定義した秒数は、回復性が期待どおりに動作することを確認するために慎重にテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85a71-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="85a71-110">間隔を低 (つまり、120秒未満) に設定した場合、またはフェールオーバーとフェールバックがあまりにも設定されていない場合は、実際のフェールオーバーが予期したとおりに機能しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="85a71-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="85a71-111">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="85a71-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="85a71-112">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="85a71-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="85a71-113">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="85a71-113">**Help** Displays this help screen.</span></span>
  

